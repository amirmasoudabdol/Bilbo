# Selection Variation

In this study we investigate the effect of varying Researcher's [intial selection](/decision-strategies.md) [policy](/decision-strategies.md#policy-chain). As we discussed, by modifying each of the **selection → decision** routine, we can influence Researcher's judgments on his research. This is equivalent of simulating different paths that a researcher could take when it comes to reporting his final outcome, a.k.a, [Selective Reporting](/hacking-strategies/selective-reporting.md).

Here, we are interested in finding out the influence of set of simple selection routines on the *Probability of Finding Significant, PFS*, *Level of Bias*, and *Distribution of Significant p-value*.

## Study Design and Parameters Pool

We start by a simple [Linear Model](/data-strategies.md#linear-model) consisting of two groups, and variable number of dependant variables.

??? datastrategy "Configuration: Data Strategy"
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

In order to study the effect of selective reporting on a wide range of study design and parameters, we will simulate all combinations of following parameters:

- *μ* ∈ [0, 1]
- *m* ∈ {2, 3, 4, 5}
- *N* ∈ {5, 10, 20, 30, 50, 80}
- *P<sub>b</sub>* ∈ {0, 0.1, 0.25, 0.5, 0.75, 0.9, 0.95}

As discussed, we achieve the selective reporting by alternation of `initial_selection_policies`, i.e., Researcher's prefered choice. Each item in the list below indicates Researcher's **first** and **prefered** choice.

- `["sig", "effect > 0", "first"]`
- `["sig", "effect > 0", "random"]`
- `["sig", "effect > 0", "last"]`
- `["sig", "effect > 0", "min(pvalue)"]`
- `["sig", "effect > 0", "max(pvalue)"]`

As we discussed, `initial_selection_policies` is a [Policy Chain Set](/decision-strategies.md#policy-chain-set), meaning that it can be followed by alternatives in the case of Researcher not being able to find an outcome with the given criteria. We follow each selection with two *Policy Chain*, `["effect > 0", "min(pvalue)"], ["effect < 0", "max(pvalue)"]`. With this, our Researcher priotrizes each set after failing to satisfy the previous set. Due to the fact that the first policy chain is the only policy chain emphesizing on significant, the aggregate outcome of the simulation can be used to measure the chance of finding significant results.

??? decisionstrategy "Configuration: Initial Selection Policy"
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

We present our results within three main set of figures. 

## Landscape of *Probability of Finding Significant*

First, we look at the probability of finding significant results within the predefined hypercube of parameters enlisted above. Figure 1 is splited into 4 different figures, each showing results for a simulation study with different number of dependent variables. 

Overall, we see that most lines are overlapping each other. This means that our selections for selective reporting variation does not necessarily translate to a meaningful difference in the probability of finding significant results. However, the effect of different ɑ-level is visible and meaningful. Basically, lowering ɑ-level lowers the chance of finding significant results, as expected.

Moveover, we can observe the effect of publication bias on our results. As one would expect, higher publication bias will lead to higher concentration of significant results in Journal. In SAM, higher publication bias encourages Jouranl to reject less non-significant results, therefore, Researcher will discard more non-significant results, see [Journal](/journal-configurations.md)


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

E

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
	        srcset="/studies/figures/selection-variation/Type_I_Error_2_Sel_Var_dark.png"
	        media="(prefers-color-scheme: dark)">
	    <img src="/studies/figures/selection-variation/Type_I_Error_2_Sel_Var_light.png" />
	  </picture>
	</figure>

=== "3"

	<figure>
	  <picture>
	    <source 
	        srcset="/studies/figures/selection-variation/Type_I_Error_3_Sel_Var_dark.png"
	        media="(prefers-color-scheme: dark)">
	    <img src="/studies/figures/selection-variation/Type_I_Error_3_Sel_Var_light.png" />
	  </picture>
	</figure>

=== "4"

	<figure>
	  <picture>
	    <source 
	        srcset="/studies/figures/selection-variation/Type_I_Error_4_Sel_Var_dark.png"
	        media="(prefers-color-scheme: dark)">
	    <img src="/studies/figures/selection-variation/Type_I_Error_4_Sel_Var_light.png" />
	  </picture>
	</figure>

=== "5"

	<figure>
	  <picture>
	    <source 
	        srcset="/studies/figures/selection-variation/Type_I_Error_5_Sel_Var_dark.png"
	        media="(prefers-color-scheme: dark)">
	    <img src="/studies/figures/selection-variation/Type_I_Error_5_Sel_Var_light.png" />
	  </picture>
	</figure>

## Pub. Bias Effect