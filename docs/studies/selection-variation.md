# Selection Variation

In this study we investigate the effect of varying the [intial selection](/decision-strategies.md). As we discussed, by modifying each of the **selection → decision** routine, we can induce alternative judgments into the decision strategy. In another word, we will be able to study the effect of [Selective Reporting](/hacking-strategies/selective-reporting.md) on different stages of conducting a research. 

Here, we are interested in finding out the influence of set of simple selection routines on the *Probability of Finding Significant, PFS*, and distribution of significant *p*-value.

## Study Design

!!! datastrategy "Configuration: Data Strategy"
	```json hl_lines="4 5 10"
    "experiment_parameters": {
        "n_reps": 1,
        "n_conditions": 2,
        "n_dep_vars": m,
        "n_obs": N,
        "data_strategy": {
            "name": "LinearModel",
            "measurements": {
                "dist": "mvnorm_distribution",
                "means": μ,
                "covs": 0.5,
                "stddevs": 1.0
            }
        }
        ...
    }
	```

## Parameters Pool

In order to study the effect of selective reporting on a wide range of study design and parameters, we will simulate all combinations of following parameters.

- *μ* ∈ [0, 1]
- *P<sub>b</sub>* ∈ [0, 0.95]
- *m* ∈ {0, 0.1, 0.25, 0.5, 0.75, 0.9, 0.95}
- *N* ∈ {5, 10, 20, 30, 50, 80}

We implement the selective reporting by altering `initial_selection_policies`, where we alternate Researcher's prefered choice. Each item in the list below indicates Researcher's **first** and **prefered** choice.

- `["sig", "effect > 0", "first"]`
- `["sig", "effect > 0", "random"]`
- `["sig", "effect > 0", "last"]`
- `["sig", "effect > 0", "min(pvalue)"]`
- `["sig", "effect > 0", "max(pvalue)"]`

As we discussed, `initial_selection_policies` is a [Policy Chain Set](/decision-strategies.md#policy-chain-set), meaning that it can be followed by an alternative in case Researcher is unable to find an outcome with the given criteria. We follow each selection with two *Policy Chain*, `["effect > 0", "min(pvalue)"], ["effect < 0", "max(pvalue)"]`. With this, our Researcher priotrizes each role after failing to satisfy the previous role. Due to the fact that the first policy chain is the only policy chain emphesizing on significant, the aggregate outcome of the simulation can be used to measure the chance of finding significant results.

!!! decisionstrategy "Configuration: Initial Selection Policy"
	```json
	{
        "decision_strategy": {
            "name": "DefaultDecisionMaker",
            "initial_selection_policies": [
                ["sig", "effect > 0", "max(pvalue)"],
                ["effect > 0", "min(pvalue)"],
                ["effect < 0", "max(pvalue)"]
            ],
            "will_start_hacking_decision_policies": [""],
            "stashing_policy": [""],
            "between_hacks_selection_policies": [[""]],
            "between_replications_selection_policies": [[""]],
            "will_continue_replicating_decision_policy": [""],
            "submission_decision_policies": [""]
        }
	}
	```

We can simply leave other selection and decision policies empty, as we do not plan to incorporate any hacking strategies or replications.

## Results

## Landscape of *Probability of Finding Significant*


=== "2"

	<figure>
	  <picture>
	    <source 
	        srcset="/studies/figures/selection-variation/PFS_2_Sel_Var_dark.png"
	        media="(prefers-color-scheme: dark)">
	    <img src="/studies/figures/selection-variation/PFS_2_Sel_Var_light.png" />
	  </picture>
	</figure>

=== "3"

	<figure>
	  <picture>
	    <source 
	        srcset="/studies/figures/selection-variation/PFS_3_Sel_Var_dark.png"
	        media="(prefers-color-scheme: dark)">
	    <img src="/studies/figures/selection-variation/PFS_3_Sel_Var_light.png" />
	  </picture>
	</figure>

=== "4"

	<figure>
	  <picture>
	    <source 
	        srcset="/studies/figures/selection-variation/PFS_4_Sel_Var_dark.png"
	        media="(prefers-color-scheme: dark)">
	    <img src="/studies/figures/selection-variation/PFS_4_Sel_Var_light.png" />
	  </picture>
	</figure>

=== "5"

	<figure>
	  <picture>
	    <source 
	        srcset="/studies/figures/selection-variation/PFS_5_Sel_Var_dark.png"
	        media="(prefers-color-scheme: dark)">
	    <img src="/studies/figures/selection-variation/PFS_5_Sel_Var_light.png" />
	  </picture>
	</figure>

## Level of ES Bias

=== "2"

	<figure>
	  <picture>
	    <source 
	        srcset="/studies/figures/selection-variation/ES_Bias_2_Sel_Var_dark.png"
	        media="(prefers-color-scheme: dark)">
	    <img src="/studies/figures/selection-variation/ES_Bias_2_Sel_Var_light.png" />
	  </picture>
	</figure>

=== "3"

	<figure>
	  <picture>
	    <source 
	        srcset="/studies/figures/selection-variation/ES_Bias_3_Sel_Var_dark.png"
	        media="(prefers-color-scheme: dark)">
	    <img src="/studies/figures/selection-variation/ES_Bias_3_Sel_Var_light.png" />
	  </picture>
	</figure>

=== "4"

	<figure>
	  <picture>
	    <source 
	        srcset="/studies/figures/selection-variation/ES_Bias_4_Sel_Var_dark.png"
	        media="(prefers-color-scheme: dark)">
	    <img src="/studies/figures/selection-variation/ES_Bias_4_Sel_Var_light.png" />
	  </picture>
	</figure>

=== "5"

	<figure>
	  <picture>
	    <source 
	        srcset="/studies/figures/selection-variation/ES_Bias_5_Sel_Var_dark.png"
	        media="(prefers-color-scheme: dark)">
	    <img src="/studies/figures/selection-variation/ES_Bias_5_Sel_Var_light.png" />
	  </picture>
	</figure>

## Landscape of *Significant P-value*

## Pub. Bias Effect