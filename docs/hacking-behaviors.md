# Hacking Behaviors

- [ ] TODO: Add some intro

### Probability of Being a Hacker

The *probability of being a hacker* is a value between 0 and 1 which determines whether the Researcher is executing the hacking workflow. Besides a fixed value, we are able to define a distribution to be used for each Researcher, for instance:

```json
"probability_of_being_a_hacker": {
	"dist": "uniform_real_distribution",
	"a": 0,
	"b": 1
} 
```
In this case, for each new Researcher, SAM draws a value from the given distribution and set the chance of him entering the Hacking Workflow. This setting allows for design and simulation of population of Researchers each with different probablity of being a hacker.

### Probability of Committing to a Hack

The *probability of committing to a hack* is a value between 0 and 1 which determines whether the Researcher applies a hacking strategy on a *given* Experiment,. Like before, while we can use a fixed value or a distribution for this parameters.

#### Hacking Commitment Strategy

Additionally, we are able to define a specific function to calcualte this probability based on the content of Experiment. For instance, we may define a function that adjust this probability based on the distance of *p*-value from ɑ. In this case, the Researcher could individually evaluate each Experiment and decide on whether he wants to commit to a QRP based on the properties of the current Experiment. This allows for a much more fine-grained filtering and execution of QRPs, and overall smarter Researchers.

In [Friese et al. 2020](/examples/Friese_et_al_2020.md)[@Friese_2020aa] example, we utilize this parameter to implement their dynamic approach of calculating researcher's interest in hacking the *p*-value based on its distance to ɑ, and the calculated effect size.

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
