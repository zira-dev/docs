---
title: Reports
subtitle: Overview
# author: sara
tags: [setup]
---

## Introduction
Reports are like scheduled jobs running on repeating schedules.  
They utilize the channels's data (i.e analysis) and post it as a snapshot on the channel's Feed, which can be a good place to start useful for daily/weekly 

# Automatic Reports
Every channel gets 2 reports automatically:
- Daily Report - A report which runs by default every weekday at 07:00AM and includes the last day's 5-minute analysis. 
- Weekly Report - A report which runs by default every Monday at 07:00AM and includes the last weeks's hourly analysis.

It is possible to Disable or Edit their name and schedule - see below.

# Report Creation
We are working hard to allow creating new reports. Stay tuned :)

# Report Configuration
### Generic
- **Name*** - The name of the report.
### Schedule
- **Type** - The repeating schedule type: 
  - Hourly - Every Hour.
  - Daily - Every Day at a selected Hour
  - Weekly - Every Week, On the selected Day(s) and Hour.
  - Monthly - Every Month on the selected Day-of-Month and Hour.  
  It is advised to choose Day-of-Month <= 28, otherwise some months with less days would be skipped.