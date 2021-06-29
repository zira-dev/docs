---
title: Get Channel Analysis
subtitle: 
# author: sara
tags: [api]
videos: 
    - title: Generate API-Key
      url: https://youtu.be/_OhSTyVSCSM
    - title: Using Postman for API testing
      url: https://youtu.be/-RYkapHBVs8
---
#### Description 
Get Channel Analysis allows to retrieve channel calculations via API.

[View in postman](https://apidocs.zira.us/#2511a90b-e6bb-4b28-a403-0a7144416017)

**GET** `https://api.zira.us/public/system/analysis`
#### Example 

*https://api.zira.us/public/system/analysis?systemId=123&interval=1%20days&fromTime=2021-05-01T00:00:00&toTime=2021-05-30T00:00:00*


* systemId can be retrieved by choosing a channel and clicking the copy id button 
{% include image.html noBorder="true" img="getChannelAnalysis.png" lightbox="true" alt="get channel analysis" caption="get channel analysis" %}
#### Query Params

| Property  | Required | Type   | Example                                               | Description                                                                                                    |
| --------- | -------- | ------ | ----------------------------------------------------- | -------------------------------------------------------------------------------------------------------------- |
| systemId   | true     | String | `"123"`                                               | System id can be copied from zira UI       |
| interval | false     | String | `5 minutes" ; "15 minutes" ; "1 hours" ; "1 days`                               | Data aggregation interval          |
| fromTime    | false     | String | `"2021-05-01T00:00:00"` | 	start timestamp in ISO format  |
| toTime    | false     | String | `"2021-05-30T00:00:00"` | end timestamp in ISO format |


#### Response

```json
{
    "data": {
        "status": "Active",
        "lasts": null,
        "kpis": [
            {
                "name": "Total Volume",
                "unit": " Gal(US)",
                "group": null,
                "value": 2565,
                "toDate": "2021-04-07T05:37:02.415589Z",
                "compare": "show",
                "maxDate": "2021-04-07T05:35:16.669000Z",
                "ordinal": "1",
                "fromDate": "2021-04-07T00:00:00.000000Z",
                "interval": 60,
                "description": null,
                "comparePositiveIsGood": false
            },
            {
                "name": "Avg. Flow",
                "unit": " GPM",
                "group": null,
                "value": 7.52,
                "toDate": "2021-04-07T05:37:02.415589Z",
                "maxDate": "2021-04-07T05:35:16.669000Z",
                "ordinal": "4",
                "fromDate": "2021-04-07T00:00:00.000000Z",
                "interval": 60,
                "description": null
            },
            {
                "name": "Max Flow",
                "unit": " GPM",
                "group": null,
                "value": 98.2,
                "toDate": "2021-04-07T05:37:02.415589Z",
                "maxDate": "2021-04-07T05:35:16.669000Z",
                "ordinal": "5",
                "fromDate": "2021-04-07T00:00:00.000000Z",
                "interval": 60,
                "description": null
            },
            {
                "name": "Current Flow",
                "unit": " GPM",
                "group": null,
                "value": 5.59,
                "toDate": "2021-04-07T05:37:02.415589Z",
                "maxDate": "2021-04-07T05:35:16.669000Z",
                "ordinal": "6",
                "fromDate": "2021-04-07T00:00:00.000000Z",
                "interval": -1,
                "description": null
            },
            {
                "name": "PH",
                "unit": " pH",
                "group": null,
                "value": 6.07,
                "toDate": "2021-04-07T05:37:02.415589Z",
                "maxDate": "2021-04-07T05:35:32.948000Z",
                "ordinal": "7",
                "fromDate": "2021-04-07T00:00:00.000000Z",
                "interval": -1,
                "description": null
            }
        ],
        "charts": [
            {
                "data": [
                    [
                        1617753600000,
                        1104
                    ],
                    [
                        1617757200000,
                        619
                    ],
                    [
                        1617760800000,
                        523
                    ],
                    [
                        1617764400000,
                        84.6
                    ],
                    [
                        1617768000000,
                        29.9
                    ],
                    [
                        1617771600000,
                        204
                    ]
                ],
                "name": "Volume (Gallon)",
                "type": "column",
                "unit": " Gal(US)",
                "color": "#74b3d2",
                "group": null,
                "toDate": "2021-04-07T05:37:02.415589Z",
                "zIndex": 2,
                "maxDate": "2021-04-07T05:35:16.669000Z",
                "ordinal": "1",
                "visible": true,
                "fromDate": "2021-04-07T00:00:00.000000Z",
                "interval": 60,
                "description": null,
                "connectNulls": false
            },
            {
                "data": [
                    [
                        1617753600000,
                        18.6
                    ],
                    [
                        1617757200000,
                        10.1
                    ],
                    [
                        1617760800000,
                        8.7
                    ],
                    [
                        1617764400000,
                        1.32
                    ],
                    [
                        1617768000000,
                        0.556
                    ],
                    [
                        1617771600000,
                        5.75
                    ]
                ],
                "name": "Flow rate (GPM)",
                "type": "line",
                "unit": " GPM",
                "color": "#000000",
                "group": null,
                "toDate": "2021-04-07T05:37:02.415589Z",
                "zIndex": 2,
                "maxDate": "2021-04-07T05:35:16.669000Z",
                "ordinal": "2",
                "visible": true,
                "fromDate": "2021-04-07T00:00:00.000000Z",
                "interval": 60,
                "description": null,
                "connectNulls": false
            },
            {
                "data": [
                    [
                        1617753600000,
                        6.42
                    ],
                    [
                        1617757200000,
                        6.43
                    ],
                    [
                        1617760800000,
                        6.43
                    ],
                    [
                        1617764400000,
                        6.39
                    ],
                    [
                        1617768000000,
                        6.17
                    ],
                    [
                        1617771600000,
                        6.08
                    ]
                ],
                "name": "pH",
                "type": "line",
                "unit": " pH",
                "color": "#46c777",
                "group": null,
                "toDate": "2021-04-07T05:37:02.415589Z",
                "zIndex": 2,
                "maxDate": "2021-04-07T05:35:32.948000Z",
                "ordinal": "4",
                "visible": false,
                "fromDate": "2021-04-07T00:00:00.000000Z",
                "interval": 60,
                "description": null,
                "connectNulls": false
            }
        ],
        "targets": [
            {
                "name": "pH is too low",
                "color": "#ff7c06",
                "toDate": null,
                "ordinal": 4,
                "toValue": null,
                "fromDate": null,
                "fromValue": 5.5
            },
            {
                "name": "pH is too high",
                "color": "#ff0131",
                "toDate": null,
                "ordinal": 4,
                "toValue": null,
                "fromDate": null,
                "fromValue": 8.5
            }
        ],
        "version": "v3"
    }
}
```

we will device the response into 4 sections:

*lasts*:deprecated


*kpis*: this is a list of objects, when each object represents KPI.
properties:

* "name" - the name of the kpi
* "unit": the units of the kpi (if it has any),
* "value": the valueItself,
* "fromDate": requested start date,
* "toDate": requested end date,
* "minDate": first timestamp with data that was found,
* "maxDate": last timestamp with data that was found,
* "interval": the interval the data was aggregated at
* "group": the group by value (if the data is grouped by).

*NOTE* - ignore all other fields as they are internal fields

*charts* : an array of objects, each of the objects contain a single curve.

properties

* "data": an array of pairs, the first element is timestamp in epoch format, the second element is the value.
* "name": the name of the curve,
* "unit": the units of the values,
* "fromDate": requested start date,
* "toDate": requested end date,
* "minDate": first timestamp with data that was found,
* "maxDate": last timestamp with data that was found,
* "interval": the interval the data was aggregated at

*NOTE* - ignore all other fields as they are internal fields

*targets*:

