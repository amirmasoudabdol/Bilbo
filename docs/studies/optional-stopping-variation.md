# Optional Stopping Variation

In this study, we will investigate the effect of applying several variants of Optional Stopping on the probability of finding significant results and the level of bias on the aggregate effect size. 

Similarly to our Sample Size Variation and Selection Variation studies, we will cover a range of parameters to draw a landscape of our both targets. Based on results of our sample size study, we adjusted the range of sample sizes from simulating the entire range of [8, 100], we simulate a more discrete set of values. As discussed, this is based on the  observed linearity of PFS and ES Bias along the fine grind range of *N*. 

For the rest of Experiment’s parameters, we simulate a range of values as follow:

- *μ* ∈ [0, 1]
- *m* ∈ {2, 4, 6}
- *N* ∈ {10, 20, 30, 40, 50, 60, 70, 80, 90, 100}
- *P<sub>b</sub>* ∈ {0, 0.1, 0.25, 0.5, 0.75, 0.9, 0.95}

In order to cover a range of optional stopping approaches, we start by simulating a more conventional optional stopping and narrow down our search parameters to find the most devastating form of optional stopping. 

As before, in each study, we investigate the effect of our configurations grid on two main metrics, Probability of Finding Significant (PFS), and Effect Size Bias, (ESB). 

## Optional Stopping on Both Groups

In our first study, we simulate the optional stopping by adding new observation as much as *S* percent of the current sample size. For example, a group with *N = 20* will have 22 observations aftering adding 10% new observations, *S = 10%*. Additionally, we vary the maxiumum number of trial that Researcher could perform the optional stopping with the given *S*. For instance, a Researcher — who is allowed to perform on maximum 5 optional stopping round — will continue adding 2 new obervations, for maximum number of 5, to each group until it finds a significant result.

- *S* ∈ {0.1, 0.2, 0.3, 0.4, 0.5}
- *T* ∈ {1, 3, 5}

With these paramters, we hope that we could cover a wide range of possible optional stopping variations, and hopefully find valuable insight into the landsacpe of PFS, and ES Bias.


!!! hackingstrategy "Configuration: Hacking Strategy"
	```json
	{
		...
        "hacking_strategies": [
            [
                {
                    "name": "OptionalStopping",
                    "target": "Both",
                    "prevalence": 1,
                    "defensibility": 1,
                    "max_attempts": 1,
                    "n_attempts": 3,
                    "num": 0,
                    "add_by_fraction": 0.4,
                    "stopping_condition": [
                        "sig"
                    ]
                },
                [
                    [
                        "sig",
                        "effect > 0",
                        "random"
                    ],
                    [
                        "effect > 0",
                        "min(pvalue)"
                    ],
                    [
                        "effect < 0",
                        "max(pvalue)"
                    ]
                ],
                [
                    "id < 0"
                ]
            ]
        ],
        ...
    }
	```

## Results

### Probability of Finding Significant

For our first results, we present the probablity of finding significant in the following set of figures. We present two main set of figures, one for studies with 2 dependent variables, and the other for studies with 4 dependent variables in each group. Additionally, we filtered our results for *T = 1*. Appendix A will discuss the effect of number of attempts.

In both cases, as we increase *S*, while we see some growth in the yellow region of the contour plot — ie., the region with highest probablity of finding significant — we don't think that this growth or even the overall change of the landscape is noticeably different from our benchmark column, first column with no optional stopping.

=== "2 Dependent Variables"

	=== "0.05"

		<figure>
		  <picture>
		    <source 
		        srcset="/studies/figures/optional-stopping-variation/PFS_0.05_attemps_1_dvs_2_Optional_Stopping_dark.png"
		        media="(prefers-color-scheme: dark)">
		    <img src="/studies/figures/optional-stopping-variation/PFS_0.05_attemps_1_dvs_2_Optional_Stopping_light.png" />
		    <figcaption aria-hidden="true">2 Dependent Variables</figcaption>
		  </picture>
		</figure>

	=== "0.005"

		<figure>
		  <picture>
		    <source 
		        srcset="/studies/figures/optional-stopping-variation/PFS_0.005_attemps_1_dvs_2_Optional_Stopping_dark.png"
		        media="(prefers-color-scheme: dark)">
		    <img src="/studies/figures/optional-stopping-variation/PFS_0.005_attemps_1_dvs_2_Optional_Stopping_light.png" />
		    <figcaption aria-hidden="true">2 Dependent Variables</figcaption>
		  </picture>
		</figure>

	=== "0.0005"

		<figure>
		  <picture>
		    <source 
		        srcset="/studies/figures/optional-stopping-variation/PFS_5e-04_attemps_1_dvs_2_Optional_Stopping_dark.png"
		        media="(prefers-color-scheme: dark)">
		    <img src="/studies/figures/optional-stopping-variation/PFS_5e-04_attemps_1_dvs_2_Optional_Stopping_light.png" />
		    <figcaption aria-hidden="true">2 Dependent Variables</figcaption>
		  </picture>
		</figure>

=== "4 Dependent Variables"

	=== "0.05"

		<figure>
		  <picture>
		    <source 
		        srcset="/studies/figures/optional-stopping-variation/PFS_0.05_attemps_1_dvs_4_Optional_Stopping_dark.png"
		        media="(prefers-color-scheme: dark)">
		    <img src="/studies/figures/optional-stopping-variation/PFS_0.05_attemps_1_dvs_4_Optional_Stopping_light.png" />
		    <figcaption aria-hidden="true">4 Dependent Variables</figcaption>
		  </picture>
		</figure>

	=== "0.005"

		<figure>
		  <picture>
		    <source 
		        srcset="/studies/figures/optional-stopping-variation/PFS_0.005_attemps_1_dvs_4_Optional_Stopping_dark.png"
		        media="(prefers-color-scheme: dark)">
		    <img src="/studies/figures/optional-stopping-variation/PFS_0.005_attemps_1_dvs_4_Optional_Stopping_light.png" />
		    <figcaption aria-hidden="true">4 Dependent Variables</figcaption>
		  </picture>
		</figure>

	=== "0.0005"

		<figure>
		  <picture>
		    <source 
		        srcset="/studies/figures/optional-stopping-variation/PFS_5e-04_attemps_1_dvs_4_Optional_Stopping_dark.png"
		        media="(prefers-color-scheme: dark)">
		    <img src="/studies/figures/optional-stopping-variation/PFS_5e-04_attemps_1_dvs_4_Optional_Stopping_light.png" />
		    <figcaption aria-hidden="true">4 Dependent Variables</figcaption>
		  </picture>
		</figure>


### Effect Size Bis

In the case of effect size bias, as we showed in the sample size variation study, we see that the level of bias is higher in experiments with 4 dependent variables. Additionally, the level of bias after performing optional stopping is higher as well. 

Moreover, we observe that the level of bias lowers as we increase *S*; however, the region that bias appears in the contour plot doesn’t move and only shrinks. We can also see that the bias region moves higher in the y-axes (ie., true effect size) as we increase the *α* level. 

Finally, we can see the influence of publication bias on the effect size bias. Expectedly, increasing the publication bias will reduce our overall effect size bias. 

=== "2 Dependent Variables"

	=== "0.05"

		<figure>
		  <picture>
		    <source 
		        srcset="/studies/figures/optional-stopping-variation/ES_Bias_0.05_attemps_1_dvs_2_Optional_Stopping_dark.png"
		        media="(prefers-color-scheme: dark)">
		    <img src="/studies/figures/optional-stopping-variation/ES_Bias_0.05_attemps_1_dvs_2_Optional_Stopping_light.png" />
		    <figcaption aria-hidden="true">2 Dependent Variables</figcaption>
		  </picture>
		</figure>

	=== "0.005"

		<figure>
		  <picture>
		    <source 
		        srcset="/studies/figures/optional-stopping-variation/ES_Bias_0.005_attemps_1_dvs_2_Optional_Stopping_dark.png"
		        media="(prefers-color-scheme: dark)">
		    <img src="/studies/figures/optional-stopping-variation/ES_Bias_0.005_attemps_1_dvs_2_Optional_Stopping_light.png" />
		    <figcaption aria-hidden="true">2 Dependent Variables</figcaption>
		  </picture>
		</figure>

	=== "0.0005"

		<figure>
		  <picture>
		    <source 
		        srcset="/studies/figures/optional-stopping-variation/ES_Bias_5e-04_attemps_1_dvs_2_Optional_Stopping_dark.png"
		        media="(prefers-color-scheme: dark)">
		    <img src="/studies/figures/optional-stopping-variation/ES_Bias_5e-04_attemps_1_dvs_2_Optional_Stopping_light.png" />
		    <figcaption aria-hidden="true">2 Dependent Variables</figcaption>
		  </picture>
		</figure>

=== "4 Dependent Variables"

	=== "0.05"

		<figure>
		  <picture>
		    <source 
		        srcset="/studies/figures/optional-stopping-variation/ES_Bias_0.05_attemps_1_dvs_4_Optional_Stopping_dark.png"
		        media="(prefers-color-scheme: dark)">
		    <img src="/studies/figures/optional-stopping-variation/ES_Bias_0.05_attemps_1_dvs_4_Optional_Stopping_light.png" />
		    <figcaption aria-hidden="true">4 Dependent Variables</figcaption>
		  </picture>
		</figure>

	=== "0.005"

		<figure>
		  <picture>
		    <source 
		        srcset="/studies/figures/optional-stopping-variation/ES_Bias_0.005_attemps_1_dvs_4_Optional_Stopping_dark.png"
		        media="(prefers-color-scheme: dark)">
		    <img src="/studies/figures/optional-stopping-variation/ES_Bias_0.005_attemps_1_dvs_4_Optional_Stopping_light.png" />
		    <figcaption aria-hidden="true">4 Dependent Variables</figcaption>
		  </picture>
		</figure>

	=== "0.0005"

		<figure>
		  <picture>
		    <source 
		        srcset="/studies/figures/optional-stopping-variation/ES_Bias_5e-04_attemps_1_dvs_4_Optional_Stopping_dark.png"
		        media="(prefers-color-scheme: dark)">
		    <img src="/studies/figures/optional-stopping-variation/ES_Bias_5e-04_attemps_1_dvs_4_Optional_Stopping_light.png" />
		    <figcaption aria-hidden="true">4 Dependent Variables</figcaption>
		  </picture>
		</figure>


## First Extension: Optional Stopping *Only* on Treatment Group

### Effect Size Bias

=== "2 Dependent Variables"

	=== "0.05"

		<figure>
		  <picture>
		    <source 
		        srcset="/studies/figures/optional-stopping-variation/Comp_ES_Bias_0.05_attemps_1_dvs_2_Optional_Stopping_dark.png"
		        media="(prefers-color-scheme: dark)">
		    <img src="/studies/figures/optional-stopping-variation/Comp_ES_Bias_0.05_attemps_1_dvs_2_Optional_Stopping_light.png" />
		  </picture>
		</figure>

	=== "0.005"

		<figure>
		  <picture>
		    <source 
		        srcset="/studies/figures/optional-stopping-variation/Comp_ES_Bias_0.005_attemps_1_dvs_2_Optional_Stopping_dark.png"
		        media="(prefers-color-scheme: dark)">
		    <img src="/studies/figures/optional-stopping-variation/Comp_ES_Bias_0.005_attemps_1_dvs_2_Optional_Stopping_light.png" />
		  </picture>
		</figure>

	=== "0.0005"

		<figure>
		  <picture>
		    <source 
		        srcset="/studies/figures/optional-stopping-variation/Comp_ES_Bias_5e-04_attemps_1_dvs_2_Optional_Stopping_dark.png"
		        media="(prefers-color-scheme: dark)">
		    <img src="/studies/figures/optional-stopping-variation/Comp_ES_Bias_5e-04_attemps_1_dvs_2_Optional_Stopping_light.png" />
		  </picture>
		</figure>

=== "4 Dependent Variables"

	=== "0.05"

		<figure>
		  <picture>
		    <source 
		        srcset="/studies/figures/optional-stopping-variation/Comp_ES_Bias_0.05_attemps_1_dvs_4_Optional_Stopping_dark.png"
		        media="(prefers-color-scheme: dark)">
		    <img src="/studies/figures/optional-stopping-variation/Comp_ES_Bias_0.05_attemps_1_dvs_4_Optional_Stopping_light.png" />
		  </picture>
		</figure>

	=== "0.005"

		<figure>
		  <picture>
		    <source 
		        srcset="/studies/figures/optional-stopping-variation/Comp_ES_Bias_0.005_attemps_1_dvs_4_Optional_Stopping_dark.png"
		        media="(prefers-color-scheme: dark)">
		    <img src="/studies/figures/optional-stopping-variation/Comp_ES_Bias_0.005_attemps_1_dvs_4_Optional_Stopping_light.png" />
		  </picture>
		</figure>

	=== "0.0005"

		<figure>
		  <picture>
		    <source 
		        srcset="/studies/figures/optional-stopping-variation/Comp_ES_Bias_5e-04_attemps_1_dvs_4_Optional_Stopping_dark.png"
		        media="(prefers-color-scheme: dark)">
		    <img src="/studies/figures/optional-stopping-variation/Comp_ES_Bias_5e-04_attemps_1_dvs_4_Optional_Stopping_light.png" />
		  </picture>
		</figure>


## Appendix A: Effect of Different Number of Attemps in Optional Stopping

#### Effect Size Bias

=== "2 Dependent Variables"

	=== "0.05"

		<figure>
		  <picture>
		    <source 
		        srcset="/studies/figures/optional-stopping-variation/App_A_Attemps_Effect_ES_Bias_0.05_dvs_2_Optional_Stopping_dark.png"
		        media="(prefers-color-scheme: dark)">
		    <img src="/studies/figures/optional-stopping-variation/App_A_Attemps_Effect_ES_Bias_0.05_dvs_2_Optional_Stopping_light.png" />
		  </picture>
		</figure>

	=== "0.005"

		<figure>
		  <picture>
		    <source 
		        srcset="/studies/figures/optional-stopping-variation/App_A_Attemps_Effect_ES_Bias_0.005_dvs_2_Optional_Stopping_dark.png"
		        media="(prefers-color-scheme: dark)">
		    <img src="/studies/figures/optional-stopping-variation/App_A_Attemps_Effect_ES_Bias_0.005_dvs_2_Optional_Stopping_light.png" />
		  </picture>
		</figure>

	=== "0.0005"

		<figure>
		  <picture>
		    <source 
		        srcset="/studies/figures/optional-stopping-variation/App_A_Attemps_Effect_ES_Bias_5e-04_dvs_2_Optional_Stopping_dark.png"
		        media="(prefers-color-scheme: dark)">
		    <img src="/studies/figures/optional-stopping-variation/App_A_Attemps_Effect_ES_Bias_5e-04_dvs_2_Optional_Stopping_light.png" />
		  </picture>
		</figure>

=== "4 Dependent Variables"

	=== "0.05"

		<figure>
		  <picture>
		    <source 
		        srcset="/studies/figures/optional-stopping-variation/App_A_Attemps_Effect_ES_Bias_0.05_dvs_4_Optional_Stopping_dark.png"
		        media="(prefers-color-scheme: dark)">
		    <img src="/studies/figures/optional-stopping-variation/App_A_Attemps_Effect_ES_Bias_0.05_dvs_4_Optional_Stopping_light.png" />
		  </picture>
		</figure>

	=== "0.005"

		<figure>
		  <picture>
		    <source 
		        srcset="/studies/figures/optional-stopping-variation/App_A_Attemps_Effect_ES_Bias_0.005_dvs_4_Optional_Stopping_dark.png"
		        media="(prefers-color-scheme: dark)">
		    <img src="/studies/figures/optional-stopping-variation/App_A_Attemps_Effect_ES_Bias_0.005_dvs_4_Optional_Stopping_light.png" />
		  </picture>
		</figure>

	=== "0.0005"

		<figure>
		  <picture>
		    <source 
		        srcset="/studies/figures/optional-stopping-variation/App_A_Attemps_Effect_ES_Bias_5e-04_dvs_4_Optional_Stopping_dark.png"
		        media="(prefers-color-scheme: dark)">
		    <img src="/studies/figures/optional-stopping-variation/App_A_Attemps_Effect_ES_Bias_5e-04_dvs_4_Optional_Stopping_light.png" />
		  </picture>
		</figure>

#### First Extension: Effect Size Bias

=== "2 Dependent Variables"

	=== "0.05"

		<figure>
		  <picture>
		    <source 
		        srcset="/studies/figures/optional-stopping-variation/Comp_App_A_Attemps_Effect_ES_Bias_0.05_dvs_2_Optional_Stopping_dark.png"
		        media="(prefers-color-scheme: dark)">
		    <img src="/studies/figures/optional-stopping-variation/Comp_App_A_Attemps_Effect_ES_Bias_0.05_dvs_2_Optional_Stopping_light.png" />
		  </picture>
		</figure>

	=== "0.005"

		<figure>
		  <picture>
		    <source 
		        srcset="/studies/figures/optional-stopping-variation/Comp_App_A_Attemps_Effect_ES_Bias_0.005_dvs_2_Optional_Stopping_dark.png"
		        media="(prefers-color-scheme: dark)">
		    <img src="/studies/figures/optional-stopping-variation/Comp_App_A_Attemps_Effect_ES_Bias_0.005_dvs_2_Optional_Stopping_light.png" />
		  </picture>
		</figure>

	=== "0.0005"

		<figure>
		  <picture>
		    <source 
		        srcset="/studies/figures/optional-stopping-variation/Comp_App_A_Attemps_Effect_ES_Bias_5e-04_dvs_2_Optional_Stopping_dark.png"
		        media="(prefers-color-scheme: dark)">
		    <img src="/studies/figures/optional-stopping-variation/Comp_App_A_Attemps_Effect_ES_Bias_5e-04_dvs_2_Optional_Stopping_light.png" />
		  </picture>
		</figure>

=== "4 Dependent Variables"

	=== "0.05"

		<figure>
		  <picture>
		    <source 
		        srcset="/studies/figures/optional-stopping-variation/Comp_App_A_Attemps_Effect_ES_Bias_0.05_dvs_4_Optional_Stopping_dark.png"
		        media="(prefers-color-scheme: dark)">
		    <img src="/studies/figures/optional-stopping-variation/Comp_App_A_Attemps_Effect_ES_Bias_0.05_dvs_4_Optional_Stopping_light.png" />
		  </picture>
		</figure>

	=== "0.005"

		<figure>
		  <picture>
		    <source 
		        srcset="/studies/figures/optional-stopping-variation/Comp_App_A_Attemps_Effect_ES_Bias_0.005_dvs_4_Optional_Stopping_dark.png"
		        media="(prefers-color-scheme: dark)">
		    <img src="/studies/figures/optional-stopping-variation/App_A_Attemps_Effect_ES_Bias_0.005_dvs_4_Optional_Stopping_light.png" />
		  </picture>
		</figure>

	=== "0.0005"

		<figure>
		  <picture>
		    <source 
		        srcset="/studies/figures/optional-stopping-variation/App_A_Attemps_Effect_ES_Bias_5e-04_dvs_4_Optional_Stopping_dark.png"
		        media="(prefers-color-scheme: dark)">
		    <img src="/studies/figures/optional-stopping-variation/App_A_Attemps_Effect_ES_Bias_5e-04_dvs_4_Optional_Stopping_light.png" />
		  </picture>
		</figure>