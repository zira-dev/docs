---
title: Download CSV data
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
Add Reading API allows to insert readings related to specific data-source.


[View in postman](https://apidocs.zira.us/#d87591b7-336e-4ab1-9791-5c6a4b143ad5)

**GET** `https://api.zira.us/public/export?meterId=METER_ID&endTime=END_TIME&startTime=START_TIME`

#### Example response

```json
{
    "data": {
        "fileUrl": "DOWNLOAD_URL"
    }
}

```
This API returns the download URL, use it within web-browser email or any background service in order to download the actual .csv file

#### Properties

| Property  | Required | Type   | Example                                               | Description                                                                                                    |
| --------- | -------- | ------ | ----------------------------------------------------- | -------------------------------------------------------------------------------------------------------------- |
| meterId   | true     | String | `"123"`                                               | Zira data-source id.  can be copied from Zira UI or fetched programmatically using `Get Data-Source` API       |
| timestamp | true     | String | `"2021-01-21T19:32:00"`                               | Date-time of the reading using ISO 8601 standard  Reading will appear on zira using the site timezone          |
| values    | true     | Object | `[{  "temperature" : "123" ,  "humidity" : "456"  }]` | the key names are the metric ids copied from Zira UI or fetched programmatically using  `Get Data-Source`  API |