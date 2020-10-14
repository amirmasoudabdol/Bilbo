# Decision Strategies

Decision strategy acts as researcher's brain, and describes his/her logical steps. Its specification will be used by the Researcher to perform two main tasks, Selection and Decision. As discussed in [Design](design.md#decision-strategy), in most cases a Selection is followed by a Decision. We will refer to this process as **Selection → Decision** sequence. 

As researcher needs to perform several selections and decisions during her course of research, each selection and decision are defined separately in the configuration file. Figure 1 shows a simplified version of research workflow by only highlighing **Selection** and **Decision** stages. The diagram also replaces logical names with their parameter names counterpart as they are appearing in `decision_strategy` section of [configurtion file](configuration-file.md).

![<b>Figure 1.</b> Decision Workflow. Rectangles are representing a <b>Selection</b> steps while diamonds are <b>Decision</b> steps.](/figures/decision-workflow.png)

Figure's 1 diagram highlights 4 main **Selection → Decision** sequences of conducting a research:

1. **Initial** sequence
	1. Performing a *selection* on an intact experiment
	2. Evaluating the selected outcome (if any) for making a *decision* to whether we should enter the [Hacking Workflow](research-workflow.md#hacking-workflow).
2. **While Hacking** sequences
	1. Performing a *selection* on an altered experiment
		2. *Selecting* certain outcomes for building a database of alternated outcomes
	2. Evaluating the selected outcome (if any) for making a *decision* to whether continue with the rest of hacking strategies or not.
3. **After Hacking** sequences
	1. Performing a *selection* on the database of altered outcomes (collected during hacking workflow)
	2. Evaluating the selected outcome — from the database of altered outcomes — for making a *decision* to whether we needs to replicate the study or not.
3. **Before Submission** sequences
	4. Evaluating the final submission, S<sub>F</sub>, for making *decision* to whether we are going ahead and submit the final outcome to Journal.

All possible selections and decisions steps can be found in the list below:

- `initial_selection_policies`
- `will_start_hacking_decision_policies`
    - `stashing_policy`
    - `h_s_selection`
    - `h_s_decision`
    - ...
- `between_hacks_selection_policies`
- `between_replications_selection_policies`
- `will_continue_replicating_decision_policy`
- `submission_decision_policies`


## Policies

Policies are the main ingredients of researcher’s logic. Each policy is a logical expression describing a query on an experiment’s available outcomes. A query is defined by chaining one or more policies together into a set. We refer to this set as [Policy Chain](decision-startegies.md#policy-chain). 

Here we discuss the range of available functions and variables that can be used to construct a policy, i.e., query.

### Policy

A policy is a string consists of a function and a variable. A function defines a kind of a query that is going to be applied on the experiment, and the variable specifies the parameters of the experiment that is going to be queried. For instance, `min(pvalue)` policy will query experiment’s outcomes for the outcome with minimum *p*-value. 

List of available functions for constructing a policy is: 

- `min(x)`, returns an outcome with minimum `x` parameters among all outcomes
- `max(x)`, returns an outcome with maximum `x` parameters among all outcomes
- `first`, returns the first items in the list
- `last`, returns the last items of the list
- `sig`, returns outcomes that are significant
- `all`, returns all outcomes
- uniary operator, `!`
- binary operators, `>`, `<`, `>=`, `<=`, `==`


And list of all available parameters:

- `id`, a unique identifier of outcome variables
- `nobs`, number of observations associated with outcome variables
- `mean`, mean associated with the outcome variables
- `pvalue`, *p*-value associated with outcome variables
- `effect`, effect size associated with outcome variables
- `sig`, significant level associated with outcome variables

Any combinations of listed functions and parameters can be used to create *a* policy. For instance,

- `max(pvalue)`, returns an outcome variable with maximum *p*-value
- `max(effect)`, returns an outcome variable with minimum effect
- `sig`, returns outcome variables that are significant
- `!sig`, returns outcome variables that are **not** significant
- `effect > 0`, return outcome variables with positive effect
- `pvalue < 0.025`, return outcome variables with *p*-value lower than 0.025
- `id == 5`, returns outcome the outcome variable with the `id` set to 5.

### Policy Chain, PC

A policy chain is a list of queries applied one after another on an experiment. They are the main mean for constructing larger and more complicated queries. For example, `[“sig”, “min(pvalue)”]` queries the experiment for a significant outcomes and among them returns the one with minimum *p*-value. As demonstrated, policies will be applied one after another in a hierarchal order; in fact, they can be think of as AND statements, `"sig" AND "min(pvalue)"`, that are being applied on Experiments.

**Decision**(s) are defined in terms of policy chains. In fact, decisions are set of queries assessing the truth of their policies. For instance, `will_start_hacking_decision_policies` is a query helping the researcher to decide whether he would start the hacking procedure or not. 

### Policy Chain Set, PCT

A *policy chain set* is a set of policy chains. Policy chain sets are mainly being used in **Selection** steps. A researcher goes through every policy chain in a hierarchal order and stops as soon as one returns a unique outcome. For instance, a research with:

```json
{
  "initial_selection_policies": [
    [“sig”, “min(pvalue)”],
    [“effect > 0”, “min(pvalue)”],
    [“effect < 0”, “first”]
  ]
}
```

- starts by looking for `[“sig”, “min(pvalue)”]`
- if there is no outcome with these properties, he moves to search for `[“effect > 0”, “min(pvalue)”]`,
- and finally, if that returns no unique outcome, he will applies the last set of queries. 

Policy chain sets are designed to mimic behaviors of a researchers with multiple priorities. An example of this behavior is demonstrated in [Bakker et al., 2012 simulation](/examples/bakker_et_al_2012.md). 

!!! decisionstrategy "Example: Bakker et al., 2012's Decision Strategy"
    ```json
    {
      "decision_strategy": {
          "name": "DefaultDecisionMaker",
          "between_hacks_selection_policies": [
              ["effect > 0", "min(pvalue)"],
              ["effect < 0", "max(pvalue)"]
          ],
          "between_replications_selection_policies": [
            ["effect > 0", "sig", "first"],
            ["effect > 0", "min(pvalue)"],
            ["effect < 0", "max(pvalue)"]
          ],
          "initial_selection_policies": [
            ["id == 2", "sig", "effect > 0"],
            ["id == 3", "sig", "effect > 0" ]
          ],
          "stashing_policy": [
            "all"
          ],
          "submission_decision_policies": [
            ""
          ],
          "will_continue_replicating_decision_policy": [""],
          "will_start_hacking_decision_policies": ["effect < 0", "!sig"]
        }
    }
    ```