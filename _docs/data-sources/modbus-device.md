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

after choosing the Zira-Modbus collector the parameters that described [here](../introduction/#mandatory-configuration-parameters ) should be filled.
there are additional parameters that are specific to modbus:

* **Ip** - the ip of the modbus gateway *must be accessible from public network*
* **Port** -  the port of the modbus gateway
* **Slave Id** - meter identifier, between 1-255
* **Reading Interval** - in seconds, minimum value is 60 (1 minute), defined the data polling interval.

{% include image.html noBorder="true" img="modbusParams.png" lightbox="true" alt="modbus params" caption="modbus-data-source" %}

if the data-source type has known device models it will allow to choose the model or to use a schema.

when a model is chosen the following parameters needs to be chosen:

* **Manufacturer** - the Manufacturer of the device.
* **Model** - the specific model name of the device.

if a model is chosen the schema already fully defined.
{% include image.html noBorder="true" img="modbusModel.png" lightbox="true" alt="modbus model" caption="modbus-model" %}

