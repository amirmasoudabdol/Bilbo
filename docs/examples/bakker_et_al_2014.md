---
title: Bakker et al., 2014
---

# Outlier Removal, Sum Scores, and The Inflation of the Type I Error Rate In Independent Samples T Tests: The Power of Alternatives and Recommendations[@Bakker_2014]

This report discusses the process of partially reproducing the simulation study conducted by Bakker et al, 2014[@Bakker_2014]. The simulation aims to study effects of removing outliers on Type I error. Besides a regular *[Linear Model](/data-strategies.md#linear-model)*, Bakker et al have simulated data from the *[General Graded Response Model](/data-strategies.md#general-graded-response-model)*[@Samejima_1997]. The original study also explores the power of alternative tests, e.g., Yuen's Test[@Yuen_1974], and Wilcoxon's Test[@Wilcoxon_1992].

## Experiment Design / Model Description

The original study is testing the effects of removing outliers in two main scenarios:

- **Non-Subjective Outliers Removal**, in which the effect of removing outliers with |*Z*| > *k — **for a fixed *k*** — is being measured.
- **Subjective Outliers Removal**, in which the effect of removing outliers with a variable *k* ∈ {3, 2.5, 2} is being measured.

Figure <a href="#fig:strategies_flowchart" data-reference-type="ref" data-reference="fig:strategies_flowchart">1</a> shows the flow of two main simulation scenarios. As discussed, by Bakker et al, 2014, the subjective Type I error is calculated based on results of the non-subjective simulation:

> Furthermore, we investigated the subjective use of *k*. This means that a comparison is counted as statistically significant if the test showed a statistically significant difference when all values were included in the sample or when the test showed a statistically significant difference when *k* is 3, 2.5, or 2. **This is comparable with adapting *k* until a statistically significant *p*-value is found**. This reflects a manner in which researchers can chase for significance (Ioannidis, 2005, 2012), ...

> <p style="text-align:right">  — Bakker et al., 2012, page 5.</p>

As stated by Bakker, this should be equivalent to calculating the subjective Type I Error from the posterior of the non-subjective simulation. We put this theory to test by running a separate simulation for the *subjective outliers removal*. In fact, in the reproduction simulation we are going to simulate the behavior of a researcher who dynamically reduces *k* until she finds a significant result. 

<figure>
	<img src="/examples/figures/bakker_2014/Marjan_2014_Flowchart.png" id="fig:strategies_flowchart" alt="Simulation Design" /><figcaption aria-hidden="true"><b>Figure 1.</b> Simulation Flowcharts</figcaption>
</figure>

## SAM Configuration

### Experiment Parameters and Study Design

In the original study, the data is generated based on two models, *Linear Model* and *General GRM* with following parameters:

- different number of items, *i* ∈ {2, 5, 10, 20, 40}
- different number of options per items, *j* ∈ {1, 5}
- different difficulty levels, *β* ∈ {0, 3}
- different sample sizes, *N* ∈ {20, 40, 100, 500}
- and one ability level, *α* ∈ 0

Finally, the [Rasch Model][@Embretson_2000] is being used as the response function of the GRM:

$$Pr(X_{ij} = 1) = \frac{exp(\theta_j - \beta_i)}{1 + exp(\theta_j - \beta_i)}$$

where $\theta_j$ is $j$'th examinee ability trait, and $\beta_i$ is the difficulty of item $i$.

In both scenarios, the study design consists of two groups, and a single dependent variant is being measured in each group, as described in Figure <a href="#fig:study_design" data-reference-type="ref" data-reference="fig:study_design">2</a>. 

<figure>
	<img src="/examples/figures/Bakker_2014/Marjan_2014_Study_Design.png" id="fig:study_design" alt="Study Design" /><figcaption aria-hidden="true"><b>Figure 2.</b> Study Designs</figcaption>
</figure>

Configurations below showcase how one can express the presented design in SAM. In the case of Linear Model, the setup is simple, we set the data strategy to [Linear Model](/data-strategies.md#linear-model) and define a multivariate normal distribution to populate all DVs. For simulating Rasch and GRM model, we use the [General Graded Response Model](/data-strategies.md#general-graded-response-model) framework, and set appropriate difficulty and ability parameters as shown below:

!!! datastrategy "Configuration: Data Strategy"
	=== "Linear"
		```json
		"experiment_parameters": {
		    "n_reps": 1,
		    "n_conditions": 2,
		    "n_dep_vars": 1,
		    "n_obs": 100,
			"data_strategy": {
				"name": "LinearModel",
				"measurements": {
					"dist": "mvnorm_distribution",
					"means": [0, μ],
					"stddevs": 1.0,
					"covs": 0.0
				}
			},
		    "test_strategy": {
		        "name": "TTest",
		        "alpha": 0.05,
		        "alternative": "TwoSided",
		        "use_continuity": true
		    },
		    "effect_strategy": {
		        "name": "MeanDifference"
		    }
		}
		```
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
		                μ
		            ],
		            "stddevs": 1.0,
		            "covs": 0.0
		        },
		        "n_categories": 5,
		        "difficulties": {
		            "dist": "mvnorm_distribution",
		            "means": [
		                θ,
		                θ,
		                θ,
		                θ
		            ],
		            "stddevs": 1.0,
		            "covs": 0.0
		        },
		        "response_function": "Rasch",
		    },
		    "test_strategy": {
		        "name": "TTest",
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
		        "name": "TTest",
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

For simulating the [Outliers Removal](/hacking-strategies/outliers-removal.md) process, we take a different approach than the one we have used for [Bakker et al., 2012](/examples/bakker_et_al_2012.md) simulation. Here, we simulate the outliers removal step before passing the Experiment to Researcher. This is equivalent to pre-processing the data and then running the final tests and analyses on it. 

For this purpose, we are using the `pre_processing_methods` parameter in `researcher_parameters` section. Pre-processing steps are similar to normal [hacking strategies](/hacking-strategies.md) with the difference that Researcher doesn't get to perform a [selection → decision sequence](/hacking-strategies.md#) after each step. They are being *fully* applied one after another, and when the list is exhausted, a copy of the *modified* Experiment will be passed to Researcher for further analysis. 

!!! hackingstrategy "Configuration: Pre-processing"
	=== "Non Subjective"
		```json
	        "probability_of_being_a_hacker": 0,
	        "probability_of_committing_a_hack": 0,
	        "hacking_strategies": [""],
	        "is_pre_processing": true,
	        "pre_processing_methods": [
	            {
	                "name": "OutliersRemoval",
	                "target": "Both",
	                "prevalence": 0.5,
	                "defensibility": 0.1,
	                "min_observations": 5,
	                "multipliers": [
	                    k
	                ],
	                "n_attempts": 1,
	                "num": N,
	                "order": "random"
	            }
	        ]
	    ```
    === "Subjective"
		```json
	        "probability_of_being_a_hacker": 0,
	        "probability_of_committing_a_hack": 0,
	        "hacking_strategies": [""],
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

Neither of the simulation scenarios involve a complicated design making routine compared to [Bakker et al., 2012](/examples/bakker_et_al_2012.md) multistep decision making process. Here, in both cases, we are only interested in reporting the only available dependent variable, and this can be done by setting `initial_selection_policies` to `["id == 1"]` or `["pre-reg"]`. With this configuration, Researcher initializes an Experiment, perform the pre-processing step, and "blindly" submit the only DV to Journal without altering the experiment.

This simple decision strategy can be used to skip the entire decision workflow, and study the Experiment in its purity without any dynamic interventions from Researcher.


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

Figure 3 shows the results of removing outliers from a normally distributed sum scores, aka. linear model. This is the equivalent of results showcased in Figure 1 of Bakker et al. 2014. While we didn't overly the results from the original study due to difficulty of extracting the data in compatible format, it can be seen that our results agrees with results form the original study, and we see a similar trends in Type I Error reduction as we increase *k*.

<figure>
  <picture>
    <source 
        srcset="/examples/figures/Bakker_2014/Linear_Model_dark.png" 
        media="(prefers-color-scheme: dark)">
  <img src="/examples/figures/Bakker_2014/Linear_Model_light.png"/><figcaption aria-hidden="true">Chance of finding a significant result with regards to different values of <span class="math inline"><em>α</em></span>.</figcaption>
  </picture> 
</figure>

Similarly, Figure 4 shows the results of removing outliers from Rasch and GRM. Figure 4 is equivalent of results presented in Figure 2, and 3 of Bakker study. We again see a similar trends with respect to increasing *k*, number of items and higher difficultly.

<figure>
  <picture>
    <source 
        srcset="/examples/figures/Bakker_2014/Rasch_GRM_Original_dark.png" 
        media="(prefers-color-scheme: dark)">
  <img src="/examples/figures/Bakker_2014/Rasch_GRM_Original_light.png"/><figcaption aria-hidden="true">Chance of finding a significant result with regards to different values of <span class="math inline"><em>α</em></span>.</figcaption>
  </picture> 
</figure>

### First Extension: Effect of Publication Bias

As we did with Bakker et al., 2012 study, we demonstrate how we can extend the currently established simulation with a few modification and explore different aspects of the problem using SAM.

In the first extension, we introduce a biased journal to the simulation by modifying the [selection strategy](/selection-strategies.md) of the Journal module as follow:

!!! journal "Configuration: Biased Journal"
	```json
	    "journal_parameters": {
	        "max_pubs": 5000,
	        "selection_strategy": {
	            "name": "SignificantSelection",
	            "alpha": 0.05,
	            "pub_bias": Pb,
	            "side": 0
	        }
	    }
	```

By varying this configuration, and keeping the rest of the setup intact, we will be able to study the effect of publication bias on our design. Figure 5 shows the results of this modification. As one would expect, we can see higher Type I error in publications as we increase the publication bias rate, from top to bottom. Also, we can see that Type I error rate decreases as we increase the number of items, and examinees, as expected.

=== "Rasch, θ = 0"
	<figure>
	  <picture>
	    <source 
	        srcset="/examples/figures/Bakker_2014/Rasch_theta_0_dark.png" 
	        media="(prefers-color-scheme: dark)">
	  <img src="/examples/figures/Bakker_2014/Rasch_theta_0_light.png"/><figcaption aria-hidden="true">Chance of finding a significant result with regards to different values of <span class="math inline"><em>α</em></span>.</figcaption>
	  </picture> 
	</figure>
=== "Rasch, θ = 3"
	<figure>
	  <picture>
	    <source 
	        srcset="/examples/figures/Bakker_2014/Rasch_theta_3_dark.png" 
	        media="(prefers-color-scheme: dark)">
	  <img src="/examples/figures/Bakker_2014/Rasch_theta_3_light.png"/><figcaption aria-hidden="true">Chance of finding a significant result with regards to different values of <span class="math inline"><em>α</em></span>.</figcaption>
	  </picture> 
	</figure>
=== "GRM, θ = 0"
	<figure>
	  <picture>
	    <source 
	        srcset="/examples/figures/Bakker_2014/GRM_theta_0_dark.png" 
	        media="(prefers-color-scheme: dark)">
	  <img src="/examples/figures/Bakker_2014/GRM_theta_0_light.png"/><figcaption aria-hidden="true">Chance of finding a significant result with regards to different values of <span class="math inline"><em>α</em></span>.</figcaption>
	  </picture> 
	</figure>
=== "GRM, θ = 3"
	<figure>
	  <picture>
	    <source 
	        srcset="/examples/figures/Bakker_2014/GRM_theta_3_dark.png" 
	        media="(prefers-color-scheme: dark)">
	  <img src="/examples/figures/Bakker_2014/GRM_theta_3_light.png"/><figcaption aria-hidden="true">Chance of finding a significant result with regards to different values of <span class="math inline"><em>α</em></span>.</figcaption>
	  </picture> 
	</figure>


### Second Extension: Meta-analysis and Bias Level

While we will discuss the power of Egger's Test and several other meta-analysis metrics, and publication bias correction methods in [Maassen et al.](/examples/esther_first_year.md) simulation study, here for the second extension, we focus on the linear model of Bakker et al., 2014 simulation and study the power/accuracy of Egger's Test on two different meta-analysis pool with different size as well as the accuracy of Random Effect estimator, Figure 6 and Figure 7 respectively. 

!!! journal "Configuration: Biased Journal"
	```json
    "journal_parameters": {
        "max_pubs": 5000,
        "selection_strategy": {
            "name": "SignificantSelection",
            "alpha": 0.05,
            "pub_bias": Pb,
            "side": 0
        },
        "meta_analysis_metrics": [
            {
                "name": "RandomEffectEstimator",
                "estimator": "DL"
            },
            {
                "name": "EggersTestEstimator",
                "alpha": 0.1
            }
        ]
    }
	```


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