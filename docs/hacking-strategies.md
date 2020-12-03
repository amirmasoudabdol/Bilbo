---
title: Introduction
---

# Hacking Strategies

*Hacking Strategy encapsulates vairous processes and procedures of performing a questionable research practices on a given Experiment.* SAM is capable of executing a complicated set of hacking strategies on a given Experiment. A list of hacking strategies will be applied one at a time, in the specified order. At the end of each method, the Researcher observes their influences on all outcome variables and decides on whether to stop, or what to report if results are satisfactory, see [here](design.md#hacking-strategy) and [here](flow.md#perform-research). Besides the definition of hacking strategies, we are able to modify researcher's behavior as well. 

In the configuration below, we can see the main body of defining hacking strategies for a researcher. Above the list of hacking strategies, a collection of parameters modify the behavior of the Researcher throughout the [Hacking Workflow](/hacking-workflow.md). While we will cover these parameters in detail in [Hacking Behavior](/hacking-behaviors.md) section, a list below briefly describes their function.

1. **`probability_of_being_a_hacker`**, `double`, indicates the chance of  chance of the Researcher entering the hacking workflow.
2. **`probability_of_committing_a_hack`**, `double`, indicates the chance of applying a given method on the Experiment. For a detailed example, see [Friese et al. 2020](/examples/Friese_et_al_2020.md)[@Friese_2020aa]
3. **`n_hacks`**, `integer`, indicates the number of hacking strategies to be selected from the list.
3. **`hacking_selection_priority`**, indicates the priority of hacking strategies during at selection stages
4. **`hacking_execution_order`**, indicates the execution order of hacking strategies during the execution of [hacking workflow](research-workflow.md#hacking-workflow).
5. **`hacking_strategies`**, a list of hacking strategies and their [**selection → decision**](/decision-strategies.md) sequences, see Figure 1.

!!! hackingstrategy "Hacking Strategy: Top Level Settings"
    ```json hl_lines="9-23"
    {
      "researcher_parameters":
      {
        "probability_of_being_a_hacker": 1,
        "probability_of_committing_a_hack": 1,
        "n_hacks: 3,
        "hacking_selection_priority": "random"
        "hacking_execution_order": "random"
        "hacking_strategies": [
          [ 
             // Hacking Strategy Specification
             {
                 "name": "H1"
             },
             // Selection
             [   
              []
             ],
             // Decision
             []
          ],
          ...
        ]
      }
    }
    ```

Highlighted lines of the code block above showcases a sequence of **hacking → selection → decision**. This corresponds to the highlighted region of the [Hacking Workflow] flowchart shown in Figure 1.

- [ ] TODO: Add more explanation
- [ ] TODO: Add an example for a complete hacking strategy

![<b>Figure 1.</b> Hacking Step](/figures/hacking-step.png)


## Hacking Strategy Specification

While each hacking strategy is accompanied with its list of unique parameters, all method *must* share a set of common parameters.

- **`name`**, `string`, each strategy should contains a name parameters, that's how SAM recognizes and configures each method, a list of available methods can be found in the left-hand side menu.
- **`stage`**, `string`, indicates on which stage of the research workflow, researcher is allowed to apply this method, see [hacking stage](#hacking-stage).
- **`defensibility`**, `double`, *defensibility* of a strategy indicates researcher's perception of how acceptable a given method is in his/her field
- **`prevalence`**, `double`, *prevalence* of a strategy indicates researcher's perception of how widespread a given method is among his/her fellow researchers.
- **`target`**, `string`, indicates which groups will be targeted by the hacking strategy.
	- `Control`
	- `Treatment`
	- `Both`
- **`stopping_condition`**, an *optional* [policy chain](/decision-strategies.md#policy-chain) indicating the stopping criteria of the method.


```
{
	"name": "OutliersRemoval",
	"target": "Both",
	"stage": "PostProcessing",
	"max_attempts": 1,
	"min_observations": 1,
	"multipliers": [2],
	"n_attempts": 1,
	"num": 10,
	"order": "random",
	“stopping_condition”: [“pre-reg”, “sig”]
}
```

## Prevalence and Defensibility

The `prevalence` and `defensibility` can be adjusted based on our preferences and type of simulations that we are going to conduct. There are higher level information at researcher's hand which helps him to make more informed decision during the hacking workflow. For insurance, we can define a cautious researcher who only applies strategies with high defensibility, ie., outliers removal. This is being enforced using `hacking_execution_order` and it will be discussed in [hacking behaviors](/hacking-behaviors.md) stage.

## Hacking Stages

Not all QRPs can be applied during every stage of conducting research. For instance, its preferred to apply the Questionable Rounding method after exploring other methods, and just before applying the Submission to the Journal. In addition, some strategies can be applied in different stages, for instance, Outliers Removal can be applied both during pre- and post-processing stages. 

The `stage` parameter controls this aspect of QRPs. While we set a logical default values for each method, we can enforce the execution of a method out of its usual stage. Here we list all available stages, as well as methods that are usually being applied during this stage:

- **Setup**
- **DataCollection**
	- Stopping Data Collection
- **PreProcessing**
	- Outliers Removal
- **PostProcessing**
	- Outliers Removal
	- Optional Stopping
	- Fabricating Data
	- Falsifying Data
- **Reporting**
	- Questionable Rounding



