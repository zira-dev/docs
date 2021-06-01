---
title: Charts
subtitle: Overview
# author: sara
tags: [setup]
---

## Introduction

Charts defines the series that would be displayed on the channel's graph. 

## Chart Configuration
### Common Configuration Options 
- **Name*** - The name of the Series, used as the series legend on the graph and point tooltip.
- **Function*** - The calculation function defining how the value is be calculated using the attached data sources.
- **Type** - Possible options: Line[default], Spline, Area, Column.
- **Visible** - True[default] is visible, False is hidden.
- **Color** - Specify the specific color using the #hex notation.
- **zIndex** - A Numeric value between 1-20 controling which series infront (higher number) or begind (lower number) other chart series. It is advisable to give columns a zIndex of 1 and all others a zIndex of 2 or above such that they would appear in front of the column.
- **Disable Y Grouping** - If multiple charts use the same unit of measure, they will automatically share the same Y Axis values. Setting this to True will force the chart to have it's own Y Axis.
### Line/Area/Spline-Only Configuration Options
- **Connect Nulls** - True will connect points even though they are not adjacent (when there are gaps in the data), False[default] will not.
- **Dash Style** - Make the line appear with dots/dash. Possible values are Solid[default], ShortDot, ShortDash.
### Column-Only Configuration Options
- **Overlap Columns** - False[default] will make the values in the column chart stack, True will make them overlap each other.