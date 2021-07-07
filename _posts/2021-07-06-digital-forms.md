---
title: Go paperless with digital forms
subtitle: Use forms to digitize manual operations, use metrics and unit of measures in order to trigger alerts and visualize your data
tags: [updates, new, featured]
author: alex
---

<div style="text-align:center; background-color:#A2E1DB; padding:20px;border-radius:20px">
<img width="200" src="/uploads/form.svg"/>
</div>
Digitizing pen and paper processes brings instantaneous value and operational benefits to an organization.

- Eliminate the need of sensors. use digital forms to measure any kind of data
- Rule Triggers can be used to initiate business flows like alerts, reports and even automated tasks 
- Form data will be available and searchable 
- Data visualization and dashboards are supported like any other data-source
- Can be attached to a channel and used as part of teams daily routine
- Use QR code in the work station to instantly open the form using mobile device or tablet

Unlike other digital forms solutions we not support only textual fields but actually provide a way to log normalized data with readable names and unit of measures and even calculated fields. this will allow later to use the form output as actual data that can be easily visualized and used as a trigger for following business processes

### Example use cases

#### Quality control
Quality parameters that are logged using digital forms will allow to notify in real time about important incidents, moreover, the communication about the incident will happen within zira channel and enable QC persons, operators and supervisors to immediately act on the subject

Quality parameters will be logged in zira, searchable and available in click. the quality parameters can later visualized as quality KPIs or charts that show the quality parameters over time. 

Display KPIs by facility, machine, operator or shift. trigger task automatically upon new incident 

{% include image.html noBorder="true" img="bottle-qc.gif" lightbox="true" alt="Using QR code to open QC form" caption="QC Form example" %}

#### OEE (Overall Equipment Effectiveness) 

OEE is simple KPI that takes into account three parameters:
- Availability: 
  Availability defined as `Planned production time - Stop time /Planned production time`

- Performance:
  The ratio between optimal run time to actual run-time `(Optimal Time per part × Total parts Count) / Actual total Run Time`

- Quality:
    the quality defined as `Good parts Count / Total parts Count`

**`OEE = Availability × Performance × Quality`**

bellow example shows simple OEE tracking implementation that log stop time and reason by machine operator. 

<figure data-uk-lightbox="animation: slide">
<video style="border-radius:20px;padding-bottom:1px;border:1px solid" src="/uploads/create-form.mp4" loop muted playsinline uk-video="autoplay: inview"></video>
<figcaption data-uk-grid class="uk-flex-right"><span class="uk-width-auto">OEE form example</span></figcaption>
</figure>
Based on the real-time data populated by the form, we can trigger alerts when downtime accrued 


<figure data-uk-lightbox="animation: slide">
<video style="border-radius:20px;padding-bottom:1px;border:1px solid" src="/uploads/create-trigger.mp4" loop muted playsinline uk-video="autoplay: inview"></video>
<figcaption data-uk-grid class="uk-flex-right"><span class="uk-width-auto">Create a trigger in order to alert on important data</span></figcaption>
</figure>

We can easily visualize the data and use it in dashboards

*****SHOW ALL OEE RELATED WIDGETS****

#### Pre-shift checklist

Pre-shift checklist is a daily routine done by teams in order to verify list of parameters related to specific work station for all kind of reasons (Safety, mechanical inspection, working procedures, etc.) 

bellow example shows a checklist that logs mechanical parameters of production line

*****SHOW ALL OEE RELATED WIDGETS****

