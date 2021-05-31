---
layout: doc
title: Schemas
categories: [Data-sources]
author: Gadi Maizler
tags: 
# videos: 
#     - title: Create new data-source
#       url: https://www.youtube.com/watch?v=ys8dQOZwK5I&ab_channel=Zira
---

Schema is an entity that is attached to a data-source, this entity describes the data that is expected to be received.


a schema is a list of metrics, with an additional configuration such as schema type.

{% include image.html noBorder="true" img="schemaExample.png" lightbox="true" alt="Hamburger menu" caption="data-sources-context" %}

in our case we will start with the standard schema.

in standard schema each metric holds the following parameters:

1. **Is main** - a boolean toggle, only a single metric can be marked as main metric, when looking at the data-source list the last reading field will hold the latest value of the main metric.  
in addition, while this device is attached to a channel, if non of the metric participate in any of the calculations of that channel, the default calculation functions of the main metric wil be used and will be reflected at the graphs. 
2. **Is required** - a boolean toggle, defines whether this metric is mandatory, if this toggle is on and the value is missing (upon post new reading) schema validation will fail an the whole reading will be thrown away.  
*this field should be turned on fields that without them the other values has no meaning*
3. **Metric** - a drop down, the drop down will show a list of the existing metrics defined in Zira, if non of them suits it is possible to create a new metric (at a different screen).  
for example of metrics: Pressure, flow, AccountId, Accumulated Volume , Volume, etc...
4. **UOM(unit of measurement)** - a drop down, the list contains all relevant unit of measurement dependent on the last field.  
for example: if the Volume metric was chosen the list of UOMs will be:
Cubic feet, Cubic meter, Liter, Gallons, etc...  
this indicates in what units the data is going to be injected to Zira.
5. **Last Display Factor** - **DEPRECATED** 
6. **Expression**  - a textual field - this field defines what ma
7. **Is Calculated** - a boolean toggle