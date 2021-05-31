---
title: KPIs
subtitle: Overview
# author: sara
tags: [setup]
---

## Introduction

KPI stands for Key Performance Indicator - A value that would give meaning to the data sources attached to the channel.  
KPIs are displayed above the chart and can appear in 2 ways:
- KPI Widget. This widget contains the following 2 values:
    - KPI value
    - % Compared to previous period (Optional)
- Pie Widget - multiple values are shown as a PIE.

## KPI Configuration
- **Name*** - The name of the KPI, used as the header of the widget.
- **Function*** - The calculation function defining how the value is be calculated using the attached data sources.
- **Value Positive Is Good** - This controls the text color of the *KPI value* and is only relevant to the KPI Widget :
  - If not set - would be colored <span style="color:black">black</span> regardless of value.
  - If true, a Positive value would be colored <span style="color:green">green</span> while a negative would be colored <span style="color:red">red</span>.
  - If false, a Positive value would be colored <span style="color:red">red</span> while a negative would be colored <span style="color:green">green</span>.
- **Compare Positive Is Good** - This controls whether the *% compared to previous period* would be shown and its text color and is only relevant to the KPI Widget: 
  - If not set - *% compared to previous period* will not be displayed.
  - If true, a Positive *% compared to previous period* value would be colored <span style="color:green">green</span> while a negative would be colored <span style="color:red">red</span>.
  - If false, a Positive *% compared to previous period* would be colored <span style="color:red">red</span> while a negative would be colored <span style="color:green">green</span>.
- **PIE** - A numeric value (1-9). All KPIs sharing the same numeric PIE value would be displayed together as a PIE instead of the regular KPI widget. This is usually helpful on multi-value KPI functions. You can have multiple PIE widgets by having multiple functions configured with different PIE numbers.