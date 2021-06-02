---
layout: doc
title: Modbus Device
categories: [Data-sources]
author: Gadi Maizler
tags: 
---
Zira supports [Modbus](https://en.wikipedia.org/wiki/Modbus) data collection. 

After a the data-source is configured properly Zira will connect to the Modbus Gateway and collect the data from the relevant device.

creation of a new modbus data-source is done by selecting "Zira-modbus" collector.
{% include image.html noBorder="true" img="modbusCollector.png" lightbox="true" alt="modbus collector" caption="modbus collector" %}

after choosing the Zira-Modbus collector the parameters that described [here](../intoduction/#mandatory-configuration-parameters ) should be filled.
there are additional parameters that are specific to modbus:

{% include image.html noBorder="true" img="modbusParams.png" lightbox="true" alt="modbus params" caption="modbus-data-source" %}

