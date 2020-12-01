---
title: Introduction
---

# Researcher Configurations

This section defines the behavior of Researcher. Researcher's parameters can be separated into two main parts, [Decision Strategies](/decision-strategies.md), [Hacking Behaviors](/hacking-strategies.md#hacking-behaviors) and [Hacking Strategies](/hacking-strategies.md). Researcher's parameters seection is divided into three main sub-sections as listed below:

<!-- The table below lists a few of the parameters, while each part's parameters will be discussed in more details in following sections. -->

- **`decision_strategy`**, *`dict`*, specification of [Decision Strategy](/decision-strategies.md)
- **Hacking Behavior**, a group of parameters defining the overall behavior and personality of Researcher, e.g.,
	- **`probability_of_being_a_hacker`**, *`number`*, Indicates the probability of a researcher deciding to apply any of the hacking strategies. [Hacking Behaviors](/hacking-strategies.md#hacking-behaviors).
	- see [Hacking Behavior](/hacking-behaviors.md) for more detail.
- **`hacking_strategies`**, *`list`*, a list of hacking strategies and their corresponding selection → decision sequences.


<!--
- **`is_pre_processing`**, *`boolean`*, Indicates whether any pre-processing procedure is being performed on the data before passing the data to the researcher for analysis. 
- **`pre_processing_methods`**, *`list`*, Similar to `p_hacking_methods`. See [Pre-processing]: hacking-strategies.md#hacking-pre-processing  
-->

- [ ] TODO: Add a full example