---
title: Introduction
---

# Researcher Parameters

This section defines the behavior of the Researcher. Researcher's parameters can be separated into three main parts, [Hacking Behaviors](hacking-behaviors.md), [Hacking Strategies](hacking-strategies.md), and [Decision Strategies](decision-strategies.md). The table below lists a few of the parameters, while each part's parameters will be discussed in more details later.


- **`decision_strategy`**, *`dict`*, Specification of a `DecisionStrategy`. See more `decision-strategies`.
- **`probability_of_being_a_hacker`**, *`number`*, Indicates the probability of a researcher deciding to apply any of the hacking strategies. [Hacking Behaviors](hacking-behaviors.md).
- **`hacking_strategies`**, *`list`*, A list of `list`, each indicating a chain of `HackingStrategy`.
- **`is_pre_processing`**, *`boolean`*, Indicates whether any pre-processing procedure is being performed on the data before passing the data to the researcher for analysis. 
- **`pre_processing_methods`**, *`list`*, Similar to `p_hacking_methods`. See [Pre-processing]: hacking-strategies.md#hacking-pre-processing  
