---
layout: doc
title: Triggers
categories: [Data-sources]
author: Gadi Maizler
tags: 
---


Trigger introduction


new trigger is added by navigating to data-source->settings->triggers



{% include image.html noBorder="true" img="datasourceSettings.png" lightbox="true" alt="data source settings" caption="data source settings" %}

{% include image.html noBorder="true" img="triggersTab1.png" lightbox="true" alt="triggers tab" caption="triggers tab" %}


#### General configuration
* **Name** - textual field, the name of the trigger, by default the name will be sent upon trigger violation. 
* **Type** - drop down, allows to define whether the violation is a positive, negative or neutral event. it effects the color of the post upon violation. 
* **Disabled** - a toggle, if it is checked the trigger will be inactive.



{% include image.html noBorder="true" img="datasourceTriggerConf.png" lightbox="true" alt="trigger configuration" caption="trigger configuration" %}