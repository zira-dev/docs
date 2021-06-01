---
title: Triggers
subtitle: Overview
# author: sara
tags: [setup]
---
## Introduction

Triggers are similar to alerts and allow you to define rules and actions that are triggered upon a rule violation.
Triggers can be defined on a channel's chart data and can inspect the data as it arrives or as aggregated data over a period of time.
This can be useful for monitoring and alerting purposes.


## Channel Trigger Configuration
### Generic
- **Name*** - The name of the trigger.
- **Type** - Controls the type of the trigger. This in turn affects the visualization of the Post created by the trigger (if chosen so in the Trigger Actions). Possible values:
    - Neutral[default] - The rule violation is neither good nor bad. The Post will look ordinary.
    - Positive - The rule violation is something desirable, for example the outside temperature is not too cold to go out. The post will have a <span style="color:green">green</span> theme.
    - Negative - The rule violation is something undesirable, for example the outside temperature is too cold and it's better to stay home. The post will have a <span style="color:red">red</span> theme.
- **Disabled** - If set to true - the trigger rule would not be checked and its actions not triggered.
### Rule
- **Metric** - The value of the selected chart function
- **Aggregative Functions** - Has 2 arguments - the metric (chart function) and the period on which the aggregation would be calculated.  
  Available aggregative functions are:
  - Sum - Sum
  - Avg - Average
  - Max - Maximum
  - Min - Minimum
  - Trend - The sum of the deltas between every 2 readings. Useful to detect a trend such as Silo Refill.
  - No Values - The metric did not have any data during the entire period. Useful to detect missing data.
- **Equality Operators**:
  - \> - Greater than
  - < - Less than
  - = - Equals
- **Logical Operators**:
  - AND
  - OR 
### Message
This is the message that would be sent by the Alert Actions.  
You can embed the Metric Value and Metric Name in the message using the available helper buttons. Note that you may also include Metrics that are not used by the rule definition.  
If the left empty, a default message "" would be used.
### Actions
Actions are the result of the trigger Rule violation.
Currently the only supported action is to send the Message to multiple destinations:
- **Post** - The Message would be posted as a post on the selected Post To channel.
- **In-App** - The Message would appear as notification inside Zira.
- **Email** - The message would be sent via email to all people following the Post-To channel.
- **Push Notification** - The message would be sent as a push notifications to the mobile phones of all people following the Post To channel.

In addition, it is possible how to control how Actions are triggered on repeated rule violations:
- **Suspend For** - For how long the rule needs to be violated before the action is triggered for the first time.
- **Repeat After** - After being triggered, for how long the rule needs to be violated before repeating the Actions.


Restrictions:
- Triggers cannot be created on multi-value chart functions