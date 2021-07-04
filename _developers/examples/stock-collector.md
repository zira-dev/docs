---
title: Add readings
tags: [setup]
---

## Introduction
This example demonstrates how to develop custom data-source that collect stock price and visualize it using a Zira Channel.

#### 1. Create a Data Source

Add a Data Source with type "Custom" and select the following metrics:
-  **Open** (Type: Number, Precision: 4)
-  **High**:  (Type: Number, Precision: 4)
-  **Low**: (Type: Number, Precision: 4)
-  **Close**: (Type: Number, Precision: 4)
-  **Volume**:  (Type: Number) 

Copy the ID of the data sources you just created - you'll need it in the next step.
in order to copy the data-source id, click on the copy icon at the top-right corner of the page



#### 2. Create API Keys
- [AlphaVantage API Key](https://www.alphavantage.co/support/#api-key)
- [Zira API Key](http://localhost:4000/developers/getting-started/api-keys/)



#### 3. Write the your business logic
In this example we used Jenkins automation server to get stock data and post it to zira 
the API used in order to fetch stock data is [Alpha Vantage](https://www.alphavantage.co/#about)
 - Create 2 Jenkins “Secret Text” credentials with above API-Keys
 - Create a Jenkins Pipeline Job with the following script:

```groovy

/* Make sure to change the values of *meterId*, *alphaVantageCredId* and *ziraCredId* in the beginning of the script */

def meterId='4113' //the data source ID we created in Zira to hold Stock Data
def alphaVantageCredId = 'alphaVantage'
def ziraCredId = 'ziraApiKey'

/* You don't need to change anything below this line */

def alphaResponse

pipeline {
    
    agent any
    
    options {
        timestamps()
        disableConcurrentBuilds()
        buildDiscarder(logRotator(numToKeepStr: '30'))
    }
    
    stages {

        stage('Get Stock Data') {

            steps {
                script {
                    def stockUrl = 'https://www.alphavantage.co/query?function=TIME_SERIES_INTRADAY&symbol=AAPL&interval=5min&outputsize=compact&datatype=json'

                    //we pre-defined the AlphaVantage credential as "Secret Text" with the API Key we got from them when signing up.
                    withCredentials([string(credentialsId: alphaVantageCredId, variable: 'ALPHA_API_KEY')]) {
                        //add authenticaion
                        stockUrl += "&apikey=${ALPHA_API_KEY}"
                        
                        //call the AlphaVantage API
                        alphaResponse = httpRequest acceptType: 'APPLICATION_JSON', 
                            url: stockUrl, 
                            wrapAsMultipart: false
                    }
                    
                
                    echo "STATUS=${alphaResponse.status}"
                    echo alphaResponse.content
                }
            }
        }
        
        stage('Post to Zira') {
            steps {
                script {
                    def baseUrl = 'integ.api.zira.us'
                    def ziraUrl = "https://${baseUrl}/public/reading/named/"
                    def ziraResponse
                    def body=[]
                    
                    //convert the alphaResponse to JSON so we can parse it and build a suitable body for Zira's API
                    def alphaResponseAsJson=readJSON text: alphaResponse.content
                    
                    alphaResponseAsJson.'Time Series (5min)'.each { key, value ->
                        def element=[
                            'meterId': meterId, //the data source ID as we defined in Zira
                    	    'timestamp': key,
                    	    'values': [
                    	        "Open": value["1. open"],
                    	        "High": value["2. high"],
                    	        "Low": value["3. low"], 
                    	        "Close": value["4. close"], 
                    	        "Volume": value["5. volume"] 
                    	    ]
                        ]
                        body.add(element)
                    }
                    
                    //convert the mapped event back to json
                    String jsonBody = writeJSON returnText: true, json: body

                    withCredentials([string(credentialsId: ziraCredId, variable: 'ZIRA_API_KEY')]) {
                        
                        //calling the Add Readings By Name Zira API
                        ziraResponse = httpRequest acceptType: 'APPLICATION_JSON',
                            url: stockUrl, 
                            wrapAsMultipart: false,
                            customHeaders: [[maskValue: true, name: 'X-API-Key', value: ZIRA_API_KEY]], //authentication
                            httpMode: 'POST',  // we're POST-ing data
                            requestBody: myBodyAsJson //the body we built with all the readings
                    }
                    
                    echo "STATUS=${ziraResponse.status}"
                    echo ziraResponse.content
                }
            }
        }
        
    }
}
```