---
title: Bakker et al., 2014
---

# Outlier Removal, Sum Scores, and The Inflation of the Type I Error Rate In Independent Samples T Tests: The Power of Alternatives and Recommendations[@Bakker_2014]

This report discusses the process of partially reproducing the simulation study conducted by Bakker et al, 2014[@Bakker_2014]. The simulation aims to study effects of removing outliers on Type I error. Besides a regular *[linear model](/data-strategies.md#linear-model)*, Bakker et al, have simulated data from the *[General Graded Response Model](/data-strategies.md#general-graded-response-model)*[@Samejima_1997]. The original study also explores the power of alternative tests, e.g., Yuen's Test[@Yuen_1974], and Wilcoxon's Test[@Wilcoxon_1992].

## Experiment Design / Model Description

The original study is testing the effects of removing outliers in two main scenarios:

- **Non-Subjective Outliers Removal**, in which the effect of removing outliers with |*Z* > *k*| — **for a fixed *k*** — is being measured.
- **Subjective Outliers Removal**, in which the effect of removing outliers with a variable *k* ∈ {3, 2.5, 2} is being measured.

The data is generated based on two models, *Linear Model* and *General GRM* with:

- different number of items, *i* ∈ {2, 5, 10, 20, 40}
- different number of options per items, *j* ∈ {1, 5}
- different difficulty levels, *β* ∈ {0, 3}
- different sample sizes, *N* ∈ {20, 40, 100, 500}
- and one ability level, *α* ∈ 0

Finally, [Rasch Model](https://en.wikipedia.org/wiki/Rasch_model#The_mathematical_form_of_the_Rasch_model_for_dichotomous_data) is being used as the response function:

$$Pr(X_{ij} = 1) = \frac{exp(\theta_j - \beta_i)}{1 + exp(\theta_j - \beta_i)}$$

where $\theta_j$ is $j$'th examinee ability trait, and $\beta_i$ is the difficulty of item $I$.

Figure <a href="#fig:strategies_flowchart" data-reference-type="ref" data-reference="fig:strategies_flowchart">1</a> shows the flow of two main simulation scenarios. As discussed, by Bakker et al, 2014, the subjective Type I error is calculated based on the results of the subjective simulation:

> Furthermore, we investigated the subjective use of *k*. This means that a comparison is counted as statistically significant if the test showed a statistically significant difference when all values were included in the sample or when the test showed a statistically significant difference when *k* is 3, 2.5, or 2. This is comparable with adapting *k* until a statistically significant p-value is found. This reflects a manner in which researchers can chase for significance (Ioannidis, 2005, 2012), ...

> <p style="text-align:right">  — Bakker et al., 2012, page 5.</p>

This reproduction simulation is in fact simulating the behavior of a researcher who dynamically reducing *k* until she finds a significant result. As stated by Bakker, this should be equivalent to calculating the subjective Type I Error from the posterior of the non-subjective simulation. We put this theory to test by running a separate simulation for the *subjective outliers removal*.

<figure>
<img src="/examples/figures/bakker_2014/Marjan_2014_Flowchart.png" id="fig:strategies_flowchart" alt="Simulation Design" /><figcaption aria-hidden="true">Simulation Design</figcaption>
</figure>

## SAM Configuration

### Experiment Parameters and Study Design

![Study Design](/examples/figures/Bakker_2014/Marjan_2014_Study_Design.png)


!!! datastrategy "Configuration: Data Strategy"
	=== "Rasch"
		```json
		"experiment_parameters": {
		    "n_reps": 1,
		    "n_conditions": 2,
		    "n_dep_vars": 1,
		    "n_obs": 100,
		    "data_strategy": {
		        "name": "GradedResponseModel",
		        "n_items": 40,
		        "abilities": {
		            "dist": "mvnorm_distribution",
		            "means": [
		                0,
		                0
		            ],
		            "stddevs": 1.0,
		            "covs": 0.0
		        },
		        "n_categories": 5,
		        "difficulties": {
		            "dist": "mvnorm_distribution",
		            "means": [
		                0,
		                0,
		                0,
		                0
		            ],
		            "stddevs": 1.0,
		            "covs": 0.0
		        },
		        "response_function": "Rasch",
		    },
		    "test_strategy": {
		        "name": "WilcoxonTest",
		        "alpha": 0.05,
		        "alternative": "TwoSided",
		        "use_continuity": true
		    },
		    "effect_strategy": {
		        "name": "MeanDifference"
		    }
		}
		```
	=== "GRM"
		```json
		"experiment_parameters": {
		    "n_reps": 1,
		    "n_conditions": 2,
		    "n_dep_vars": 1,
		    "n_obs": 100,
		    "data_strategy": {
		        "name": "GradedResponseModel",
		        "n_items": 40,
		        "abilities": {
		            "dist": "mvnorm_distribution",
		            "means": [
		                0,
		                0
		            ],
		            "stddevs": 1.0,
		            "covs": 0.0
		        },
		        "n_categories": 2,
	            "difficulties": [
	                {
	                    "dist": "normal_distribution",
	                    "mean": 0,
	                    "stddev": 1.0
	                }
	            ],
		        "response_function": "Rasch",
		    },
		    "test_strategy": {
		        "name": "WilcoxonTest",
		        "alpha": 0.05,
		        "alternative": "TwoSided",
		        "use_continuity": true
		    },
		    "effect_strategy": {
		        "name": "MeanDifference"
		    }
		}
		```

### Hacking Strategies

!!! hackingstrategy "Configuration: Pre-processing"
	```json
        "probability_of_being_a_hacker": 0,
        "probability_of_committing_a_hack": 0,
        "hacking_strategies": [
            ""
        ],
        "is_pre_processing": true,
        "pre_processing_methods": [
            {
                "name": "SubjectiveOutlierRemoval",
                "min_observations": 5,
                "prevalence": 0.5,
                "target": "Both",
                "defensibility": 0.1,
                "range": [
                    2,
                    3
                ],
                "step_size": 0.5,
                "stopping_condition": [
                    "sig"
                ]
            }
        ]
    ```

### Decision Strategies


!!! decisionstrategy "Configuration: Decision Strategy"
	```json
	"decision_strategy": {
	    "name": "DefaultDecisionMaker",
	    "initial_selection_policies": [
	        [
	            "id == 1"
	        ]
	    ],
	    "between_hacks_selection_policies": [[""]],
	    "between_replications_selection_policies": [[""]],
	    "stashing_policy": [""],
	    "submission_decision_policies": [""],
	    "will_continue_replicating_decision_policy": [""],
	    "will_start_hacking_decision_policies": [""]
	}
	```

## Results

### Original vs. Reproduction

Figure <a href="#fig:subjective_vs_non_subjective_type_i_error" data-reference-type="ref" data-reference="fig:subjective_vs_non_subjective_type_i_error">2</a> shows the result of the reproduction simulation. I did not try to reproduce the entire simulation and every parameters combinations. However, the reproduction simulation agrees with the original results when parameters are crossing. The SUbjective Type I Error is larger in most cases, and between simulations with similar parameters, those with harder items affected more drastically by subjectively removing of the outliers, Figure <a href="#fig:subjective_vs_non_subjective_type_i_error" data-reference-type="ref" data-reference="fig:subjective_vs_non_subjective_type_i_error">2</a>, right columns, *β* = 3.


<figure>
  <picture>
    <source 
        srcset="/examples/figures/Bakker_2014/Linear_Model_dark.png" 
        media="(prefers-color-scheme: dark)">
  <img src="/examples/figures/Bakker_2014/Linear_Model_light.png"/><figcaption aria-hidden="true">Chance of finding a significant result with regards to different values of <span class="math inline"><em>α</em></span>.</figcaption>
  </picture> 
</figure>

<!-- <figure>
<img src="/examples/figures/bakker_2014/Side-by-Side.png" id="fig:subjective_vs_non_subjective_type_i_error" alt="Non-Subjective (left panel) and Subjective (right panel) Type I Error" /><figcaption aria-hidden="true">Non-Subjective (left panel) and Subjective (right panel) Type I Error</figcaption>
</figure> -->

<figure>
  <picture>
    <source 
        srcset="/examples/figures/Bakker_2014/Rasch_GRM_Original_dark.png" 
        media="(prefers-color-scheme: dark)">
  <img src="/examples/figures/Bakker_2014/Rasch_GRM_Original_light.png"/><figcaption aria-hidden="true">Chance of finding a significant result with regards to different values of <span class="math inline"><em>α</em></span>.</figcaption>
  </picture> 
</figure>

### First Extension: Effect of Publication Bias


=== "θ = 0"
	<figure>
	  <picture>
	    <source 
	        srcset="/examples/figures/Bakker_2014/Rasch_GRM_theta_0_dark.png" 
	        media="(prefers-color-scheme: dark)">
	  <img src="/examples/figures/Bakker_2014/Rasch_GRM_theta_0_light.png"/><figcaption aria-hidden="true">Chance of finding a significant result with regards to different values of <span class="math inline"><em>α</em></span>.</figcaption>
	  </picture> 
	</figure>

=== "θ = 3"
	<figure>
	  <picture>
	    <source 
	        srcset="/examples/figures/Bakker_2014/Rasch_GRM_theta_3_dark.png" 
	        media="(prefers-color-scheme: dark)">
	  <img src="/examples/figures/Bakker_2014/Rasch_GRM_theta_3_light.png"/><figcaption aria-hidden="true">Chance of finding a significant result with regards to different values of <span class="math inline"><em>α</em></span>.</figcaption>
	  </picture> 
	</figure>


### Second Extension: Meta-analysis and Bias Level

<figure>
  <picture>
    <source 
        srcset="/examples/figures/Bakker_2014/Linear_Model_EggersTestEstimator_dark.png" 
        media="(prefers-color-scheme: dark)">
  <img src="/examples/figures/Bakker_2014/Linear_Model_EggersTestEstimator_light.png"/><figcaption aria-hidden="true">Chance of finding a significant result with regards to different values of <span class="math inline"><em>α</em></span>.</figcaption>
  </picture> 
</figure>


<figure>
  <picture>
    <source 
        srcset="/examples/figures/Bakker_2014/Linear_Model_RandomEffectEstimator_dark.png" 
        media="(prefers-color-scheme: dark)">
  <img src="/examples/figures/Bakker_2014/Linear_Model_RandomEffectEstimator_light.png"/><figcaption aria-hidden="true">Chance of finding a significant result with regards to different values of <span class="math inline"><em>α</em></span>.</figcaption>
  </picture> 
</figure>

\bibliography