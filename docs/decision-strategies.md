# Decision Strategies

*Decision strategy acts as researcher's brain, and describes his/her logical steps.* Its specification will be used by Researcher to perform two fundamentals tasks, Selection and Decision. As discussed in the [Design](design.md#decision-strategy) section, in most cases a Selection is followed by a Decision, directly evaluating the already selected outcome. 

We will refer to this process as **Selection → Decision** sequence. These sequences are the building block of decision strategy. We use utilize them in several different stages of [Research](/research-workflow), and [Hacking](/hacking-workflow.md) workflows in order to mimic the thought process of Researcher and guide him throughout his research.

As researcher needs to perform several selections and decisions during her course of research, each selection and decision is defined separately in the configuration file. Figure 1 shows a simplified version of research workflow by only highlighing **Selection** and **Decision** stages. The diagram also replaces logical names with their parameter names counterpart as they are lsited in `decision_strategy` section of [configurtion file](configuration-file.md).

![<b>Figure 1.</b> Decision Workflow. Rectangles are representing a <b>Selection</b> steps while diamonds are <b>Decision</b> steps.](/figures/decision-workflow.png)

Figure 1 highlights 4 main **Selection → Decision** sequences of research and hackingw workflow. Here we 

1. **Initial** sequence
	1. Performing a *selection* on an original experiment
	2. Evaluating the selected outcome (if any) to make a *decision* on whether to enter the [Hacking Workflow](research-workflow.md#hacking-workflow).
2. **While Hacking** sequences
	1. Performing a *selection* on an altered experiment
		2. **Stashing Step:** *Selecting* certain outcomes for building a database of alternated outcomes
	2. Evaluating the selected outcome (if any) to make a *decision* on whether to continue with the rest of hacking strategies or not.
3. **After Hacking** sequences
	1. Performing a *selection* on the database of altered outcomes (collected during hacking workflow), **stashed results**.
	2. Evaluating the selected outcome — from the database of altered outcomes — to make a *decision* on whether to replicate the study or not.
3. **Before Submission** sequences
	4. Evaluating the final submission, S<sub>F</sub>, to make *decision* on whether to submit the final submission to Journal.

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

Policies are the building blocks of researcher’s logic. Each policy is a logical expression describing a query to be performed on list of available outcome variables. 

<!-- A query is defined by chaining one or more policies together into a set. We refer to this set as [Policy Chain](/decision-startegies.md#policy-chain).  -->

Here we discuss a range of available logical expression and variables that can be used to construct any elaborate quesries.

<!-- functions and variables that can be used to construct a policy, i.e., query. -->

### Policy

A policy is a string consists of a function and a variable. A function defines a kind of a query that is going to be applied on an experiment, and the variable specifies the parameter of the experiment that is going to be queried. For instance, `min(pvalue)` policy will query experiment’s outcomes for the outcome with the minimum *p*-value. 

List of available functions for constructing a policy is: 

- `min(x)`, returns an outcome with minimum `x` parameters among all outcomes
- `max(x)`, returns an outcome with maximum `x` parameters among all outcomes
- `first`, returns the first items in the list
- `last`, returns the last items of the list
- `sig`, returns a list of significant outomces
- `all`, returns all outcomes
- uniary operator, `!`
- binary operators, `>`, `<`, `>=`, `<=`, `==`


And list of all available parameters:

- `id`, a unique identifier of outcome variables
- `nobs`, number of observations associated with outcome variables
- `mean`, the mean value associated with the outcome variables
- `pvalue`, the *p*-value associated with outcome variables
- `effect`, the effect size associated with outcome variables
- `sig`, the significant flag associated with outcome variables, set by comapring pvalue against ɑ.

Any combinations of listed functions and parameters can be used to create *a* policy. For instance,

- `max(pvalue)`, returns an outcome variable with maximum *p*-value
- `max(effect)`, returns an outcome variable with minimum effect
- `sig`, returns outcome variables that are significant
- `!sig`, returns outcome variables that are **not** significant
- `effect > 0`, return outcome variables with positive effect
- `pvalue < 0.025`, return outcome variables with *p*-value lower than 0.025
- `id == 5`, returns outcome the outcome variable with the `id` set to 5.

### Policy Chain, PC

A policy chain is a list of queries applied one after another on an experiment. They are the main mean of constructing larger and more complicated queries. For example, `[“sig”, “min(pvalue)”]` queries an experiment for a list of significant outcomes and among them returns the one with minimum *p*-value. As demonstrated, policies will be applied one after another in a hierarchal order; in fact, they should be seen as AND statements, `"sig" AND "min(pvalue)"`, that are going to be applied on Experiments.

!!! important
    **Decision**(s) are defined in term of policy chains. In fact, decisions are set of queries assessing the truth of their policies. For instance, `will_start_hacking_decision_policies` is helping a researcher to decide on whether to start the hacking procedure or not. 

### Policy Chain Set, PCS

A *policy chain set* is a set of policy chains. Policy chain sets are mainly being used in **Selection** steps. A researcher goes through every policy chain in a hierarchal order and stops as soon as one returns a unique outcome. 

```json
{
  "initial_selection_policies": [
    [“sig”, “min(pvalue)”],
    [“effect > 0”, “min(pvalue)”],
    [“effect < 0”, “first”]
  ]
}
```

For instance, a research with the selection policy chain set above:

- starts by looking for `[“sig”, “min(pvalue)”]`
- if there is no outcome with these properties, he moves to search for `[“effect > 0”, “min(pvalue)”]`,
- and finally, if that returns no unique outcome, he applies the last set of queries on Experiment.

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