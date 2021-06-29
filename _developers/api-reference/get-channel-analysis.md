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
| toTime    | false     | String | `"2021-05-30T00:00:00"` | end timestamp in ISO format  `Get Data-Source`  API |

