---
title: Benchmarks
subtitle: Overview
# author: sara
tags: [setup]
---

## Introduction
Benchmarks allow you to set Baselines, Targets, Highs and Lows on existing charted data.  
Benchmarks are visualized on the graph allowing you to see how your actual data compares to the benchmark(s).  
They also allow you to automatically see the gap between the actual data and the benchmark as a KPI (mostly useful for Target benchmarks).

--benchmark config screenshot here--

## Benchmark Configuration
- **Name*** - The name of the benchmark. This would appear alongside the benchmark visualization on the graph.
- **Type*** - The type of the benchmark:
    - Baseline - This represents the baseline of past data in order to compare it with future data.
    - Target - This is useful to set a target you want to reach.
    - Set-Point (High) - Useful for setting an upper limit.
    - Set-Point (Low) - Useful for setting a lower limit.
- **Charted Series*** - The charted series the benchmark is defined on. The benchmark visibility depends on the visibility of the charted series - When it is visible, so would the benchmark. When it is hidden (through series configuration or clicking the series legend below the graph) the benchmark would be hidden as well.
- **Color*** - Controls the color of the benchmark visualization on the graph.
- **From Value*** - The benchmark base value. The gap KPI would be calculated using this value.
- **To Value** - If this is left empty, the benchmark would be visualized as a line. If this has a value it would be visualized as a band.
- **From/To Dates** - If the *From Date* is set, the benchmark would be effective and also visualized only after the selected date. If the *To Date* is set, the benchmark would be effective and also visualized only before the selected date. If both From and To dates are left empty - the benchmark would be effective indefinitly. This is useful for example to set different targets for different years, where the most recent target has a From Date set but not a To Date. When the year is over - update the existing benchmark with an To Date, and then create a new one starting from the next day.
- **Link** - A link is plain text and is used to form a relation between a Benchmark, a Chart Series and a KPI. See more info below.


Restrictions:
- You cannot create multiple benchmarks with the same name on the same channel.
- You cannot create multiple benchmarks with the same Type on the same Charted Series on overlapping date ranges. 

## Automatic Benchmark KPI
When creating a benchmark, a KPI representing the benchmark value is automatically added to the channel.
## Automatic Gap KPI
When creating a benchmark, we first find the benchmark's link (L1). If not defined, we look for the link (L2) on the Chart Series the benchmark was defined on. If either L1 or L2 is found - we look for a KPI (K) with the same link. If such is found - a new KPI is added to calculate the Gap of (K) from the benchmark. If neither L1, L2 or K is found - nothing happens.