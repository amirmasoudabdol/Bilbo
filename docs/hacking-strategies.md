---
title: Introduction
---

# Hacking Strategies

Hacking Strategy encapsulates vairous processes and procedures of performing questionable research practices on a given Experiment.

SAM is able to execute a complicated set of hacking strategies on a given Experiment. A list of hacking strategies will be applied one at a time, in a specified order. At the end of each method, Researcher observes their influences on all outcome variables and decides when whether to stop, and what to report if results are satisfactory. See [here](design.md#hacking-strategy) and [here](flow.md#perform-research). Besides the definition of hacking strategies, we are able to modify researcher's behavior as well. 

In the configuration below, we can see the main body of defining hacking strategies for a researcher. We start by setting some general parameters, and then defining each method individually.

1. **`probability_of_being_a_hacker`**, the chance of entering the hacking workflow
2. **`probability_of_committing_a_hack`**, the chance of applying a given method on the experiment. For a detailed example, see [Friese et al. 2020](Friese_et_al_2020.md)[@Friese_2020aa]
3. **`n_hacks`**, number of hacking strategies to be selected from the list
3. **`hacking_selection_priority`**, indicates the priority of hacking strategies during at selection stages
4. **`hacking_execution_order`**, indicates the execution order of hacking strategies in [hacking workflow](research-workflow.md#hacking-workflow)
5. **`hacking_strategies`**, list of hacking strategies and their [**selection → decision**](decision-strategies.md) sequences.

!!! hackingstrategy "Hacking Strategy: Top Level Settings"
    ```json
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

Besides 

## Probability of Being a Hacker

The *probability of being a hacker* is a value between 0 and 1 that is being used by SAM to determine if a Researcher is a going through the hacking workflow or not. Besides a fixed value, we can give a distribution to be used for each Researcher, e.g.

```json
"probability_of_being_a_hacker": {
	"dist": "uniform_real_distribution",
	"a": 0,
	"b": 1
} 
```

In this case, SAM generates a new value for every new researcher. 

## Probability of Committing to a Hack

The *probability of committing to a hack* is a value between 0 and 1 that is being used by SAM to determine whether a researcher applies a hacking strategy on a *given* Experiment. 

### Hacking Commitment Strategy

Like before, while we can use a fixed value or a distribution for this parameters, we will be able to define a specific function that returns this probability based on the content of the Experiment. For instance, we may define a function that adjust the probability based on the distance of *p*-value to ɑ.

In [Friese et al. 2020](Friese_et_al_2020.md)[@Friese_2020aa] example, we utilize this parameter to implement their dynamic approach of calculating researcher's interest in hacking the *p*-value based on its distance to ɑ, and the calculated effect size.

```json
"hacking_probability_strategy": {
	"method": "FrankenbachStrategy",
	"base_hp": params["hacking_prob_base_hp"],
	"lo_p": 0.2,
	"hi_p": 0.4,
	"lo_sei": 0.1,
	"hi_sei": 0.6
}
```


## Hacking Strategy Specification

While each hacking strategy is companied with its set of unique parameters, every method shares a set of common parameters with each others. 

- **`name`**, each strategy should contains a name parameters, that's how SAM recognizes and configures that specific method, a list of available methods can be found in the left-hand side menu.
- **`stage`**, indicates on which stage of the research workflow, researcher is allowed to apply this method
- **`defensibility`**, the *defensibility* of a strategy indicates researcher's perception on how acceptable a given method is in his/her field
- **`prevalence`**, the *prevalence* of a strategy indicates researcher's perception of how widespread a given method is among his/her fellow researchers
- **`target`**<sup>*</sup>, the *target* parameters indicates which groups will be targeted by the researcher.
	- `Control`
	- `Treatment`
	- `Both`
- **`stopping_condition`**, a *optional* [policy chain](decision-strategy.md#policy-chain) indicating the stopping criteria of the method.


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

The `prevalence` and `defensibility` can be adjusted based on our preferences and type of studies that we are going conduct. There are higher level information at researcher's hand that helps him to make more informed decision during the hacking workflow. For insurance, we can define a cautious researcher who only applies strategies with high defensibility, ie., outliers removal.

### Number of Hacking Strategies

The `n_hacks` parameters determine how many of the hacking strategies are going to be selected and used by the researcher. Omitting this parameter will result in selection of all available parameters.

### Hacking Strategies' Selection Priority

If the value of `n_hacks` (*h<sub>n</sub>*) parameter is smaller than the total number of hacking strategies listed (*h<sub>t</sub>*), a researcher must select *h<sub>n</sub>* methods from the set of given strategies.

This selection can be done in various ways:

- Based on items prevalence
	- `asc(prevalence)`
	- `desc(prevalence)`
- Based on items defensibility
	- `asc(defensibility)`
	- `desc(defensibility)`
- Randomly, `random`
- Given ordered, `‌`

### Hacking Strategies Execution's Order

Similarly, when it comes to the execution of hacking strategies, researcher may decide which method he/she would likes to apply first. This can be based on similar criteria as described in `hacking_execution_order`:

Available values for `hacking_execution_order`:

- Based on items prevalence
	- `asc(prevalence)`
	- `desc(prevalence)`
- Based on items defensibility
	- `asc(defensibility)`
	- `desc(defensibility)`
- Randomly, `random`
- Given ordered, `‌`

## Hacking Stages

Not all QRPs can be applied on all the stage of conducting a research. For instance, Falsifying Data cannot be applied on the experiment during the initialization of the experiment setup when there is no data yet. In addition, some strategies can be applied in different stages, for instance, Outliers Removal can be applied both during pre- and post-processing stages.

The `stage` parameter controls this aspect of QRPs. While we set a logical default values for each method, you can enforce the execution of a method out of its usual stage. Here we list all available stages, as well as methods that are usually being applied during this stage:

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



