---
layout: doc
title: Import-Data
categories: [Data-sources]
author: Gadi Maizler
tags: 
---
### Introduction
Zira supports a batch upload of data from csv file.
it is done by downloading a csv template from Zira, filling the file with the data and sending it back to Zira.

### Uploading the data
navigate to data-source->upload
{% include image.html noBorder="true" img="datasource-upload.png" lightbox="true" alt="data-source-upload" caption="data-source-upload" %}

Download template
{% include image.html noBorder="true" img="templateDownload.png" lightbox="true" alt="download template" caption="download template" %}

the template with be downloaded with one entry which is a sample data, leave the headers and override the entries with the data needed to be uploaded.
{% include image.html noBorder="true" img="sampleData.png" lightbox="true" alt="sample data" caption="sample data" %}

after editing the file it will look like that:

{% include image.html noBorder="true" img="sampleData2.png" lightbox="true" alt="sample data2" caption="sample data2" %}


save the file, click the import button, a file browser will be opened. 
choose the file to upload.

{% include image.html noBorder="true" img="import.png" lightbox="true" alt="import" caption="import" %}

**Note** - It might take a couple of minutes until the data is ready in zira.