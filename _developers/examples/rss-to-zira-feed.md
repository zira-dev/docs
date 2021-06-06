---
title: new post from rss feed
subtitle: Overview
author: Gadi Maizler
tags: [setup]
---

## Introduction
This example demonstrates how Zira feed can be used to share data.

in this example the application will poll the data from an rss feed (The Daily by The New York Times).
it will parse the content and the link to the podcast and will create a new post on a pre-defined Zira channel.
all channel followers will receive notification that a new post was created.


## Generation of Application Token



```javascript
const url  = 'https://feeds.simplecast.com/54nAGcIl' // this is a url for rss feed
const newPostUrl = 'https://integ.api.zira.us/public/post' // this is the url for creation of a new post
const apiKey = '9c3bd0ea-1ada-42b2-859d-c12196c6336e' // this is the application key 

// npm install -s rss-parser
const Parser = require('rss-parser') // this node module is used the fetch and parse rss feed.
// npm install -s rss-parser
const fetch = require('node-fetch') // this node module is used to send a POST request.

const parser = new Parser()

async function getLatestItem(){
    const feed = await parser.parseURL(url)

    const content = 'Date: ' + feed.items[1].pubDate + '\n' +  feed.items[1].contentSnippet + '\n Link : \n' + feed.items[1].enclosure.url

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