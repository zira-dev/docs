---
title: Create post
author: Zira training
tags: [setup]
---
This example shows how to integrate another application with zira feed by demonstrating how to automatically create post on zira channel using data retrieved by RSS feed.

Posting on zira channel will notify all channel followers when new post was added.

The example code can be easily modified in order to support data fetching from any API endpoint

#### 1. Create new application and generate API-key

{% include image.html noBorder="true" img="addNewApplication2.png" lightbox="true" alt="add application2" caption="Add New Application" %}
{% include image.html noBorder="true" img="addNewApplication3.png" lightbox="true" alt="add application3" caption="Generate API Key" %}
For more details: [Applications & API Keys](/developers/getting-started/api-keys/)


#### 2. copy the channel-id 

As describe in  Add post [API-Reference](/developers/api-reference/add-post/), the expected payload is:

```json
{
    "title":"Post title",
    "content": "Post content",
    "toChannelId": "The channel id, where the post will appear"
}

```
The channel id can be copied from the address bar as appear in bellow image:

{% include image.html noBorder="true" img="copy-channel-id.png" lightbox="true" alt="copy channel id" caption="Copy channel id from address bar" %}

#### 3. Code example

This example is written in javascript.

```js
const url  = 'https://feeds.simplecast.com/54nAGcIl' // this is a url for rss feed
const newPostUrl = 'https://api.zira.us/public/post' // this is the url for creation of a new post
const apiKey = '9c3bd0ea-1ada-42b2-859d-c12196c6336e' // this is the application key 

// npm install -s rss-parser
const Parser = require('rss-parser') // this node module is used the fetch and parse rss feed.
// npm install -s rss-parser
const fetch = require('node-fetch') // this node module is used to send a POST request.

const parser = new Parser()

async function getLatestItem(){
    const feed = await parser.parseURL(url)

// here we are creating the post content
    const content = 'Date: ' + feed.items[0].pubDate + '\n' +  feed.items[0].contentSnippet + '\n Link : \n' + feed.items[0].enclosure.url 

    const myBody = {
        content : content,
        toChannelId : '5789'
    }
    const options = {
        method : 'POST', 
        body : JSON.stringify(myBody),
        headers : {
            'X-API-Key' : apiKey,
            'Content-Type' : 'application/json'
        }
    }
    await fetch(newPostUrl, options)
}
getLatestItem()
```

#### 4. Result

the result of this execution is a generation of a single post with the latest entry at the rss feed:
{% include image.html noBorder="true" img="rssPost.png" lightbox="true" alt="rss post" caption="News post created by application fetching latest post of rss feed" %}