---
title: new post from rss feed
subtitle: Overview
author: Gadi Maizler
tags: [setup]
---

## Introduction
This example demonstrates how Zira feed can be used to share data.

in this example the application will poll the data from an rss feed (The Daily by The New York Times).
it will parse the content will create a new post on a pre-defined Zira channel.
all channel followers will receive notification that a new post was created.


## Generation of a new application

* navigate to company->site->Application-> 'Add New Application'
{% include image.html noBorder="true" img="addNewApplication1.png" lightbox="true" alt="add application" caption="add application" %}
* give the application a unique name and a description and click "Generate API key"
{% include image.html noBorder="true" img="addNewApplication2.png" lightbox="true" alt="add application2" caption="add application2" %}
* a new application was created, please save the key it is possible to copy the key to the clipboard by clicking on the copy button.
{% include image.html noBorder="true" img="addNewApplication3.png" lightbox="true" alt="add application3" caption="add application3" %}



## retrieving a channel id
???????????????????  
?????????????????? it is impossible to do it from the application1!!!!   
???????????????????
## example

this example is written in javascript with nodejs engine.
it requires the installation of the following node modules:
https://www.npmjs.com/package/node-fetch
https://www.npmjs.com/package/rss-parser


the result of this execution is a generation of a single post with the latest entry at the rss feed:
{% include image.html noBorder="true" img="rssPost.png" lightbox="true" alt="rss post" caption="rss post" %}


code snippet:
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