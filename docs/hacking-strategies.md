---
title: Hacking Strategies
layout: default
nav_order: 8
---

Hacking Strategies
==================

> *Hacking Strategy encapsulates the processes or procedures of performing different questionable research practices.*

SAM can execute a complicated set of hacking strategies on a given `Experiment`. A list of hacking strategies will be applied one at a time, in the specified order. `Researcher` can observe their influences on all outcome variables and decides when to stop, and what to report. See [here](design.md#hacking-strategy) and [here](flow.md#perform-research).

The configuration below shows how you can define a chain of hacking strategies. The `p_hacking_methods` is a *list of list of JSON objects*, see [crash course on JSON](configuration-file.md#crash-course-on-json). You can define several groups of hacking strategies, each listing different hacking strategies with different orders and parameters. Since JSON arrays' are ordered objects, this setup is suitable for controlling the order in which each group, and method in each group will be applied on the `Experiment`. The example below defines 3 groups of hacking strategies with different numbers of methods in each.

!!! hackingstrategy "Hacking Strategy: Top Level Settings"
    ```json
    {
      "probability_of_being_a_hacker": 1,
      "probability_of_committing_a_hack": 1,
      "hacking_selection_priority":
      "hacking_execution_order":
      "hacking_strategies": [
        [ 
           // Hacking Strategy Specification
           {
               "name": "H1"
           },
           // Selection Policy
           [   
            []
           ],
           // Decision Policy
           []
        ],
        ...
      ]
    }
    ```

A JSON object defines the specifications of each hacking strategy. The code below defines *H1* hacking with three parameters. During the [initialization phase](flow.md#initialization), SAM reads the specification and prepares the hacking strategy accordingly.

```json
{
  "name": "H1",
  "param_1": 1,
  "param_2": "yellow",
  "param_3": "at all cost"
}
```

The rest of this section lists all hacking strategies implemented in SAM. If you are interested in developing your own methods, head to `chap-extending-sam`{.interpreted-text role="doc"} chapter.



## Probability of Being a Hacker


## Probability of Commiting to a Hack



### Hacking Commitment Strategy


## Prevalence and Defensibility


## Hacking Strategies' Selection Priority



## Hacking Execution's Order