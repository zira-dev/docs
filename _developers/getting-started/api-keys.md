---
title: Applications & API-Keys
subtitle: how to generate API-key to authenticate API requests to Zira
# author: sara
tags: [introduction]
videos: 
    - title: Generate API-Key
      url: https://youtu.be/_OhSTyVSCSM
    - title: Using Postman for API testing
      url: https://youtu.be/-RYkapHBVs8
---

Zira allows you to create custom applications. 
For each Application, an API key generated for authentication purpose

**In order to create new application:**

1. Browse to your site page (for more info, check [companies & sites](../../_docs/getting-started/companies-and-sites.md))
2. Go to **Applications** tabs
3. Click **Add New Application** button at the top right corner of the page

{% include image.html noBorder="true" img="applications-tab.png" lightbox="true" alt="SIte Applications tab" caption="SIte Applications tab" %}

4. Provide a name and description for your application
5. Click **Generate API Key** button. New application with designated API-Key will be created 
6. Copy the API-Key by clicking the copy icon 
The API Key should be kept secret, it is highly recommended not to keep it within your code and not share it with unauthorized people
{% include image.html noBorder="true" img="generate-api-key.png" lightbox="true" alt="SIte Applications tab" caption="SIte Applications tab" %}
{% include image.html noBorder="true" img="copy-api-key.png" lightbox="true" alt="SIte Applications tab" caption="SIte Applications tab" %}


The `X-API-Key` header will be used to authenticate api requests to zira


## Example

```http
POST /public/post HTTP/1.1
Host: api.zira.us
X-API-Key: <YOUR_API_KEY>
Content-Length: 84
 
{
    "postTypeId": "1",
    "content": "Hello world!",
    "toChannelId": "12610"
}
```