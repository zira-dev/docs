---
title: Add Readings
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

[View in postman](https://apidocs.zira.us/#d87591b7-336e-4ab1-9791-5c6a4b143ad5)

**GET** `https://api.zira.us/public/system/analysis?systemId=&interval=&fromTime=&toTime=`
#### Example 

https://api.zira.us/public/system/analysis?systemId=123&interval=1%20days&fromTime=2021-05-01T00:00:00&toTime=2021-05-30T00:00:00


* systemId can be retrieved by choosing a channel and clicking the copy id button 
{% include image.html noBorder="true" img="getSystemChannel.png.png" lightbox="true" alt="create form" caption="create form" %}
#### Query Params

| Property  | Required | Type   | Example                                               | Description                                                                                                    |
| --------- | -------- | ------ | ----------------------------------------------------- | -------------------------------------------------------------------------------------------------------------- |
| systemId   | true     | String | `"123"`                                               | System id can be copied from zira UI       |
| interval | false     | String | `5 minutes" ; "15 minutes" ; "1 hours" ; "1 days`                               | Data aggregation interval          |
| fromTime    | false     | String | `"2021-05-01T00:00:00"` | the key names are the metric ids copied from Zira UI or fetched programmatically using  `Get Data-Source`  API |
| toTime    | false     | String | `"2021-05-30T00:00:00"` | the key names are the metric ids copied from Zira UI or fetched programmatically using  `Get Data-Source`  API |

