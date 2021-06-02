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

### Modbus data-source model
when a model is chosen the following parameters needs to be chosen:

* **Manufacturer** - the Manufacturer of the device.
* **Model** - the specific model name of the device.

if a model is chosen the schema already fully defined.
{% include image.html noBorder="true" img="modbusModel.png" lightbox="true" alt="modbus model" caption="modbus-model" %}

 
### Modbus data-source schema

there are 2 types of schemas:
Modbus and Modbus-Analog
Modbus-Analog has all Modbus parameters and the 4 analog [parameters](../schemas/#analog-schema).

#### Schema parameters
* **Name** - textual field, the name of the schema. the name is unique at site level.
* **Register Offset** - numeric field, defines the offset the register for all metrics in the schema. 
* **Holding** - boolean toggle, are registers that are read  holding or input registers.

#### Schema metric parameters
Modbus has all standard schema [parameters](../schemas/#standard-schema ) with additional modbus specific parameters:
* **Register Type** - a drop down list, defines the type of the data that is being retrieved from the device. 
  * int16
  * uint16
  * int32
  * uint32
  * float32
  * float64
* **Base Register** - numeric value, defines the start register of the data.  
* **Endian** -  drop down list, big or little endian. defines how to interpret the data.
{% include image.html noBorder="true" img="modbusSchema.png" lightbox="true" alt="modbus schema" caption="modbus-schema" %}