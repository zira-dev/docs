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
Label - 
Text - 
Number -
Boolean - 