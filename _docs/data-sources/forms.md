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
is has several parameters:
* name - the name of the field, it is a dropdown with the existing metric names, start typing the name needed and choose it. if the desired name does not you can add it.
   {% include image.html noBorder="true" img="newNameField1.png" lightbox="true" alt="new name field" caption="new name field" %}
* Description - the specific description of the field
* Required - whether this field is required, if the required field is checked, the user won't be able to submit the form unless the field is filled.
* Regex - the text that the user enters must match the regular expression entered here. 
* Min length - the minimum number of the characters needs to be filled at this field
* Max length - the maximum number of the characters needs to be filled at this field
 
**"Label"** - this field has only a name that can be any text. it can be used to divide the form into several sections or any other usage.
{% include image.html noBorder="true" img="formLabel.png" lightbox="true" alt="form label" caption="form label" %}  
**"Number"** - 
**"Boolean"** -  
**"List"** - 
**"Image"** -  
**Other"** - 