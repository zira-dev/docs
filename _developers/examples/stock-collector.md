---
title: Collecting and Visualizing Stocks
subtitle: Overview
# author: sara
tags: [setup]
---

## Introduction
This example demonstrates how to easily develop a Zira stock price collector and visualize it using a Zira Channel.

## Sign up to Zira
[Sign up is free and easy](my.zira.us)
## Create a Company and Site
The data from the AlphaVantage API is in Eastern Time, so it is important to create the site with the Eastern Time Timezone  
(Selecting "United States" as the country and "New York" as the state will limit the possible timezones to the correct ones).

## Create a Data Source
In Site Overview, go to the *Data Sources* tab
Add a Data Source with type "Form" and add/select the following metrics:
1. "Open"  
    Type: Number
    Precision: 4
2. "High":  
   Type: Number
   Precision: 4
3. "Low":  
   Type: Number
   Precision: 4
4. "Close":  
   Type: Number
   Precision: 4
5. "Volume":  
   Type: Number 

Copy the ID of the data sources you just created - you'll need it in the next step.

## Create the collector
1. Create 2 Jenkins "Secret Text" credentials
   1. AlphaVantage API Key
   2. Zira API Key
2. Create a Jenkins Pipeline Job with the following script.  
   **Make sure to change the values of *meterId*, *alphaVantageCredId* and *ziraCredId* in the beginning of the script**

```
/* ****** CHANGE HERE - BEGIN ******* */

def meterId='4113' //the data source ID we created in Zira to hold Stock Data
def alphaVantageCredId = 'AlphaVantage'
def ziraCredId = 'zira_integ_telaviv'

/* ****** CHANGE HERE - END ********* */

/* ****************************************************
*  You don't need to change anything below this line  *
* ****************************************************/

//we define it globally since we need it across stages
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
                    //this is the TIME_SERIES_INTRADAY AlphaVantage API URL to get Apple stock prices
                    def myURL = 'https://www.alphavantage.co/query?function=TIME_SERIES_INTRADAY&symbol=AAPL&interval=5min&outputsize=compact&datatype=json'

                    //we pre-defined the AlphaVantage credential as "Secret Text" with the API Key we got from them when signing up.
                    withCredentials([string(credentialsId: alphaVantageCredId, variable: 'ALPHA_API_KEY')]) {
                        //add authenticaion
                        myURL += "&apikey=${ALPHA_API_KEY}"
                        
                        //call the AlphaVantage API
                        alphaResponse = httpRequest acceptType: 'APPLICATION_JSON', 
                            url: myURL, 
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
                    def myURL = "https://${baseUrl}/public/reading/named/"
                    def ziraResponse
                    def myBody=[]
                    
                    //convert the alphaResponse to JSON so we can parse it and build a suitable body for Zira's API
                    def alphaResponseAsJson=readJSON text: alphaResponse.content
                    
                    /*
                        do the actual conversion
                        AlphaVantage Response looks like:
                        {
                          "Meta Data": {
                              "1. Information": "Intraday (5min) open, high, low, close prices and volume",
                              "2. Symbol": "AAPL",
                              "3. Last Refreshed": "2021-05-28 20:00:00",
                              "4. Interval": "5min",
                              "5. Output Size": "Compact",
                              "6. Time Zone": "US/Eastern"
                          },
                          "Time Series (5min)": {
                              "2021-05-28 20:00:00": {
                                  "1. open": "124.6400",
                                  "2. high": "124.6500",
                                  "3. low": "124.6100",
                                  "4. close": "124.6100",
                                  "5. volume": "7263"
                              },
                              ...
                          }
                        }
                        
                        While Zira's API expects something like:
                        [
                            {
                                'meterId': <meterId>, 
                        	    'timestamp': <timestamp>,
                        	    'values': ["metric1":"value1", "metric2":"value2",...]
                            },
                            ...
                        ]
                    */
                    
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
                        myBody.add(element)
                    }
                    
                    //convert the mapped event back to json
                    String myBodyAsJson = writeJSON returnText: true, json: myBody

                    //we pre-defined the zira_integ_telaviv credential as "Secret Text" with the API Key we got from Zira's Site Applications tab
                    withCredentials([string(credentialsId: ziraCredId, variable: 'ZIRA_API_KEY')]) {
                        
                        //calling the Add Readings By Name Zira API
                        ziraResponse = httpRequest acceptType: 'APPLICATION_JSON',
                            url: myURL, //API url we defined earlier
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

Run the Jenkins Job - data should appear in the Zira device you created shortly.  
You can also have it run on schedule, i.e once a day through Jenkins Job configuration.

## Create a Stocks channel
In Site Overview go to the *Channels* tab.  
Create a new channel of type "Stocks".  

## Create a Stock sub-channel
Click the ... on the channel you just created and Add Sub-channel of type Stock
Attach the Data Source you created earlier  
You should now see the stock data visualized in Zira - cool!

## Next Steps...
You can create a device per stock (symbol) you want to track. You might have to create multiple Jenkins jobs or modify the existing script to handle more than one symbol (shouldn't be too difficult :) ).  
If you intend to do so and wish to track each stock separately, create a Stock sub-channel per stock. The Parent channel will display only the "close" value of each of the data sources attached to its subsystems.