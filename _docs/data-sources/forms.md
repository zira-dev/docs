---
layout: doc
title: Forms
categories: [Data-sources]
author: Gadi Maizler
tags: 
---

Form is a type of data-source that allows clients to enter data manually in a convenient and intuitive way.  
creation of a new form is done by selecting "Form" collector.

{% include image.html noBorder="true" img="formCollector.png" lightbox="true" alt="form collector" caption="form collector" %}

the creation of a "Form" data-source has a dedicated user interface with the following parameters:
1. **Name** - textual field, the name of the data-source
2. **Linked form**(optional) - a drop down list, shows the list of the additional forms at the same site, this defines what form the user should be redirected to after form submission.
for example : if there is a certain routine that should be done each morning at 3, the user will be moved from one form to another to ease up the process.  
3. **Publish to**(optional) - a drop down list, shows the list of channels under the same site as the data-source, upon form submission a new post will be created on each of those channel, the post will contain all the data that was filled to the form.  
*more than one channel can me chosen*

4. **Description**(optional) - a short description of what the form is used for.

{% include image.html noBorder="true" img="createForm.png" lightbox="true" alt="create form" caption="create form" %}

-- when create a new form on a right side of the screen a preview will appear to show how the form will look like.

clicking the "Add form field" button will ad a new entry to the form.

each entry has a "type" field, depended on the type field additional parameters will appear.
{% include image.html noBorder="true" img="formNewField.png" lightbox="true" alt="form new field" caption="form new field" %}

#### Types
**"Text"** - this is a textual field that allows the user the enter any free text he desires.
parameters:
* name - the name of the field, it is a dropdown with the existing metric names, start typing the name needed and choose it. if the desired name does not you can add it.
   {% include image.html noBorder="true" img="newNameField1.png" lightbox="true" alt="new name field" caption="new name field" %}
* Description - the specific description of the field
* Required - whether this field is required, if the required field is checked, the user won't be able to submit the form unless the field is filled.
* Regex - the text that the user enters must match the regular expression entered here. 
* Min length - the minimum number of the characters needs to be filled at this field
* Max length - the maximum number of the characters needs to be filled at this field
 
**"Label"** - a name that can be any text. it can be used to divide the form into several sections or any other usage.
{% include image.html noBorder="true" img="formLabel.png" lightbox="true" alt="form label" caption="form label" %}  
**"Boolean"** - this field represents a checkbox.
parameters:
* name - the name of the field, it is a dropdown with the existing metric names, start typing the name needed and choose it. if the desired name does not you can add it.
* Description - the specific description of the field
* Selected by default - if this field is checked, the checkbox will be checked by default when opening the form.
{% include image.html noBorder="true" img="checkbox.png" lightbox="true" alt="checkbox" caption="checkbox" %}  


**"List"** - allows the user to choose from a pre defined list of values.
parameters:
* name - the name of the field, it is a dropdown with the existing metric names, start typing the name needed and choose it. if the desired name does not you can add it.
* Description - the specific description of the field
* Required - whether this field is required, if the required field is checked, the user won't be able to submit the form unless the field is filled.
* As radio -  effects on the way the list is shown to the user, radio buttons OR drop down
{% include image.html noBorder="true" img="formList1.png" lightbox="true" alt="form list drop down" caption="form list drop down1" %}  
{% include image.html noBorder="true" img="formList2.png" lightbox="true" alt="form list radio button" caption="form list radio button1" %}  

**"Image"** - allows the user to upload image as part of the form data.
parameters:
* name - the name of the field, it is a dropdown with the existing metric names, start typing the name needed and choose it. if the desired name does not you can add it.
* Description - the specific description of the field
* Required - whether this field is required, if the required field is checked, the user won't be able to submit the form unless the field is filled.  

**"Other"** -  all other metrics types are the same, the type represents the general category of the metric such as:  
Mass, Length, Volume, Flow, Area, Speed, etc... .  
parameters:
* name - the name of the field, it is a dropdown with the existing metric names, start typing the name needed and choose it. if the desired name does not you can add it.
* Description - the specific description of the field
* UOM(unit of measurement) - the unit of measurement of the expected input data.[more details](../schemas#standard-schema)
* Calculated - indicated whether this field is being calculated from the counter. in order for this calculation to work the Accumulated corresponding metric must be preset in the same schema[more details](../schemas#standard-schema)
* Expression - a textual field - this field defines what mathematical manipulation should be done on that field before it is being written into Zira. [more details](../schemas#standard-schema)