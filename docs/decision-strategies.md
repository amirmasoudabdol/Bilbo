---
title: Decision Strategies
layout: default
nav_order: 9
---

# Decision Strategies

> *Decision Strategy executes researcher's logic behind starting and
> stopping the questionable research practices.*

Decision strategy acts as the brain of the researcher. Their specifications will be used by the Researcher to perform two main tasks, Selection and Decision. As discussed in [Design](design.md#decision-strategy), in most cases a Selection follows by a Decision. We will refer to this process as **Selection → Decision** sequence. 

As researcher needs to perform several selections and decisions during her course of research, each selection and decision are defined separately in the configuration file. All possible selections and decisions steps can be found in the list below:

- Initial **Selection Policy**
- Will be Hacking **Decision Policy**
  - Each hacking strategy will end with a selection-decision of its own, read more on [Hacking Stage](research-workflow.md#hacking-stage)
    - Selection
    - Decision
    - ...
- Between Hacked Outcomes **Selection Policies**
- Will Continue Replicating **Decision Policies**
- Will be Submitting To Journal **Decision Policy**

Figure 1 shows a simplified version of research workflow only highlighing **Selection** and **Decision** stages.

![<b>Figure 1.</b> Decision Workflow](/figures/decision-workflow.png)

## Policies



### Policy

Policies are the main ingredients of researcher’s logic. Each policy  is a logical expression describing a query on an experiment’s available outcomes. 

A policy is a string consists of a function and a variable. A function defines a kind of a query that’s going to be applied on the experiment, and the variable specifies the parameters of the functions. For instance,  `min(pvalue)` policy will query experiment’s outcomes for the outcome with minimum *p*-value. 

List of available functions for constructing a policy is: 

- `min(x)`, returns an outcome with minimum `x` parameters among all outcomes
- `max(x)`, returns an outcome with maximum `x` parameters among all outcomes
- `first`
- `last`
- `sig`
- `all`
- **not** operator, `!`
- binary operators, `>`, `<`, `>=`, `<=`, `==`


And list of parameters:

- `id`
- `pvalue`
- `effect`
- `stddev`
- `nobs`

Any combinations of 



### Policy Chain, PC

A policy chain is a list of queries applied one after another on an experiment. For example, `[“sig”, “min(pvalue)”]` queries the experiment for a significant outcomes and among them returns the one with minimum *p*-value.

### Policy Chain Set, PCT

A policy chain set is a set of policy chains. Policy chain sets are being mainly being used for **Selection** steps. A researcher goes through every policy chain in a hierarchal order and stops as soon as one returns a unique outcome. For instance, a research with `initial_selection_policies` of `[[“sig”, “min(pvalue)”], [“effect > 0”, “min(pvalue)”], [“effect < 0”, “first”]]` starts by looking for `[“sig”, “min(pvalue)”]`, if there is no outcome with these properties, he moves to search for `[“effect > 0”, “min(pvalue)”]`, and if that returns no unique outcome, he will applies the last set of queries. 

Policy chain sets are designed to mimic the notion of a researchers with multiple priorities. An example of this behavior is demonstrated in [Bakker et al., 2012 simulation](/examples/bakker_et_al_2012.md). 