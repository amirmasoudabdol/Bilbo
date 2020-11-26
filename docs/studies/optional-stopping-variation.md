# Optional Stopping Variation

After investigating the influecens of initial selection logic, and sample size, here, we will investigate the effect of applying several variants of Optional Stopping on the probability of finding significant results and the level of effect size bias. Similarly to our [Sample Size Variation](/studies/sample-size-variation.md) and [Selection Variation](/studies/selection-variation.md) studies, we will cover a range of parameters in order to draw a landscape of our both target metrics, e.g., Probability of Finding Significant (PFS), and Effect Size Bias, (ESB). 

## Study Design

Based on results of our sample size study, we have adjusted the range of sample sizes from simulating the entire range of [8, 100] to a discrete set of values, as we think our approximation can still provide an overview of the interaction. This is based on an observed linearity of PFS and ES Bias along the fine-grind range of *N*. For the rest of Experiment’s parameters, we use the same set of parameters in order to draw a complete and comparable picture as before.

- *μ* ∈ [0, 1]
- *m* ∈ {2, 4, 6}
- *N* ∈ {10, 20, 30, 40, 50, 60, 70, 80}
- *P<sub>b</sub>* ∈ {0, 0.1, 0.25, 0.5, 0.75, 0.9, 0.95}

In order to cover a range of optional stopping approaches, we start by simulating a more conventional optional stopping and narrow down our search parameters to find the most *devastating* and strong form of optional stopping. 

## Optional Stopping on Both Groups

In our first study, we simulate the optional stopping by adding new observation as much as *S* percent of the current sample size to every group. For example, a group with *N = 20* will have 22 observations aftering adding 10% new observations, *S = 10%*. Additionally, we vary the maxiumum number of trial that Researcher could perform the optional stopping with the given *S*. For instance, a Researcher — who is allowed to perform a maximum 5 optional stopping trials — will continue adding 2 new obervations, for maximum number of 5 times, to each group until it finds a significant result. The variation of described parameters is as follow:

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
                    "ratio": 0.4,
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


For our first results, we present the probablity of finding significant in the following set of figures. We present three main set of figures, each showcasing results from studies with different number of dependent variables, ie., 2, 4, 6. Additionally, we filtered our results for *T = 1* in order to be able to compare them with studies without optional stopping. Appendix A will discuss the effect of number of attempts.

In both cases, as we increase *S*, while we see some growth in the yellow region of the contour plot — ie., the region with highest probablity of finding significant — we do not believe that this growth or even the overall change of the landscape is noticeably different from our benchmark column — first column with no optional stopping.

<!-- Results from Nov 26, Full Run -->
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

=== "6 Dependent Variables"

	=== "0.05"

		<figure>
		  <picture>
		    <source 
		        srcset="/studies/figures/optional-stopping-variation/PFS_0.05_attemps_1_dvs_6_Optional_Stopping_dark.png"
		        media="(prefers-color-scheme: dark)">
		    <img src="/studies/figures/optional-stopping-variation/PFS_0.05_attemps_1_dvs_6_Optional_Stopping_light.png" />
		    <figcaption aria-hidden="true">6 Dependent Variables</figcaption>
		  </picture>
		</figure>

	=== "0.005"

		<figure>
		  <picture>
		    <source 
		        srcset="/studies/figures/optional-stopping-variation/PFS_0.005_attemps_1_dvs_6_Optional_Stopping_dark.png"
		        media="(prefers-color-scheme: dark)">
		    <img src="/studies/figures/optional-stopping-variation/PFS_0.005_attemps_1_dvs_6_Optional_Stopping_light.png" />
		    <figcaption aria-hidden="true">6 Dependent Variables</figcaption>
		  </picture>
		</figure>

	=== "0.0005"

		<figure>
		  <picture>
		    <source 
		        srcset="/studies/figures/optional-stopping-variation/PFS_5e-04_attemps_1_dvs_6_Optional_Stopping_dark.png"
		        media="(prefers-color-scheme: dark)">
		    <img src="/studies/figures/optional-stopping-variation/PFS_5e-04_attemps_1_dvs_6_Optional_Stopping_light.png" />
		    <figcaption aria-hidden="true">6 Dependent Variables</figcaption>
		  </picture>
		</figure>

In the case of effect size bias, as we showed in the sample size variation study, we see that the level of bias is higher as add more dependent variables to our studies. Additionally, while optional stopping does not increase the overall level of bias, it shifts it toward higher sample sizes. This is expected, as a 

Moreover, we observe that the level of bias lowers as we increase *S*; however, the region that bias appears in the contour plot doesn’t move and only shrinks. We can also see that the bias region moves higher in the y-axes (ie., true effect size) as we increase the *α* level. 

Finally, we can see the influence of publication bias on the effect size bias. Expectedly, increasing the publication bias will reduce our overall effect size bias. 

<!-- Results from Nov 26, Full Run -->
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

=== "6 Dependent Variables"

	=== "0.05"

		<figure>
		  <picture>
		    <source 
		        srcset="/studies/figures/optional-stopping-variation/ES_Bias_0.05_attemps_1_dvs_6_Optional_Stopping_dark.png"
		        media="(prefers-color-scheme: dark)">
		    <img src="/studies/figures/optional-stopping-variation/ES_Bias_0.05_attemps_1_dvs_6_Optional_Stopping_light.png" />
		    <figcaption aria-hidden="true">6 Dependent Variables</figcaption>
		  </picture>
		</figure>

	=== "0.005"

		<figure>
		  <picture>
		    <source 
		        srcset="/studies/figures/optional-stopping-variation/ES_Bias_0.005_attemps_1_dvs_6_Optional_Stopping_dark.png"
		        media="(prefers-color-scheme: dark)">
		    <img src="/studies/figures/optional-stopping-variation/ES_Bias_0.005_attemps_1_dvs_6_Optional_Stopping_light.png" />
		    <figcaption aria-hidden="true">6 Dependent Variables</figcaption>
		  </picture>
		</figure>

	=== "0.0005"

		<figure>
		  <picture>
		    <source 
		        srcset="/studies/figures/optional-stopping-variation/ES_Bias_5e-04_attemps_1_dvs_6_Optional_Stopping_dark.png"
		        media="(prefers-color-scheme: dark)">
		    <img src="/studies/figures/optional-stopping-variation/ES_Bias_5e-04_attemps_1_dvs_6_Optional_Stopping_light.png" />
		    <figcaption aria-hidden="true">6 Dependent Variables</figcaption>
		  </picture>
		</figure>


## First Extension: Optional Stopping *Only* on Treatment Group

In our first extension, we investigate the effect of only applying the optional stopping on treatment groups, meaning that Researcher will only add new observations to the treatment group and leave the control group intact. 

In the figure below, we can see the comparison between this study  and the one performed above, ie., adding new observation to both groups. As one might have been expected, adding collection new observation only for treatment groups will have more severe effect on the level of effect size bias. This can be seen in the figure by noticing the slightly wider bias region in “Treatment” columns compared to their “Both” counterpart. 


<!-- Results from Nov 20, Compared to Nov 26 Full Run -->
=== "2 Dependent Variables"

	=== "0.05"

		<figure>
		  <picture>
		    <source 
		        srcset="/studies/figures/optional-stopping-variation/1st_Ext/Comp_ES_Bias_0.05_attemps_1_dvs_2_Optional_Stopping_dark.png"
		        media="(prefers-color-scheme: dark)">
		    <img src="/studies/figures/optional-stopping-variation/1st_Ext/Comp_ES_Bias_0.05_attemps_1_dvs_2_Optional_Stopping_light.png" />
		  </picture>
		</figure>

	=== "0.005"

		<figure>
		  <picture>
		    <source 
		        srcset="/studies/figures/optional-stopping-variation/1st_Ext/Comp_ES_Bias_0.005_attemps_1_dvs_2_Optional_Stopping_dark.png"
		        media="(prefers-color-scheme: dark)">
		    <img src="/studies/figures/optional-stopping-variation/1st_Ext/Comp_ES_Bias_0.005_attemps_1_dvs_2_Optional_Stopping_light.png" />
		  </picture>
		</figure>

	=== "0.0005"

		<figure>
		  <picture>
		    <source 
		        srcset="/studies/figures/optional-stopping-variation/1st_Ext/Comp_ES_Bias_5e-04_attemps_1_dvs_2_Optional_Stopping_dark.png"
		        media="(prefers-color-scheme: dark)">
		    <img src="/studies/figures/optional-stopping-variation/1st_Ext/Comp_ES_Bias_5e-04_attemps_1_dvs_2_Optional_Stopping_light.png" />
		  </picture>
		</figure>

=== "4 Dependent Variables"

	=== "0.05"

		<figure>
		  <picture>
		    <source 
		        srcset="/studies/figures/optional-stopping-variation/1st_Ext/Comp_ES_Bias_0.05_attemps_1_dvs_4_Optional_Stopping_dark.png"
		        media="(prefers-color-scheme: dark)">
		    <img src="/studies/figures/optional-stopping-variation/1st_Ext/Comp_ES_Bias_0.05_attemps_1_dvs_4_Optional_Stopping_light.png" />
		  </picture>
		</figure>

	=== "0.005"

		<figure>
		  <picture>
		    <source 
		        srcset="/studies/figures/optional-stopping-variation/1st_Ext/Comp_ES_Bias_0.005_attemps_1_dvs_4_Optional_Stopping_dark.png"
		        media="(prefers-color-scheme: dark)">
		    <img src="/studies/figures/optional-stopping-variation/1st_Ext/Comp_ES_Bias_0.005_attemps_1_dvs_4_Optional_Stopping_light.png" />
		  </picture>
		</figure>

	=== "0.0005"

		<figure>
		  <picture>
		    <source 
		        srcset="/studies/figures/optional-stopping-variation/1st_Ext/Comp_ES_Bias_5e-04_attemps_1_dvs_4_Optional_Stopping_dark.png"
		        media="(prefers-color-scheme: dark)">
		    <img src="/studies/figures/optional-stopping-variation/1st_Ext/Comp_ES_Bias_5e-04_attemps_1_dvs_4_Optional_Stopping_light.png" />
		  </picture>
		</figure>

## Second Extension: Optional Stopping Field

In our last extension of our study, we investigate the effect of a variable optional stopping parameters. In contrast to our previous simulations where we simulated a range of parameters, in this simulation we draw a random value for two main parameters of the optional stopping, i.e., `ratio` and `n_attempts`. 

<picture>
	<source 
	    srcset="/studies/figures/optional-stopping-variation/2nd_Ext/Ratio_Distribution_dark.png"
	    media="(prefers-color-scheme: dark)">
	<img src="/studies/figures/optional-stopping-variation/2nd_Ext/Ratio_Distribution_light.png" width="300" align="right"/>
</picture>

Our choices for distribution of `ratio` and `n_attempts` is a based on a *piecewise constant distribution* with which we fine tune the range and probability of values that we are interested in. For the `ratio`, we design a random number generator with the frequency shown below.

<picture>
	<source 
	    srcset="/studies/figures/optional-stopping-variation/2nd_Ext/Attempts_Distribution_dark.png"
	    media="(prefers-color-scheme: dark)">
	<img src="/studies/figures/optional-stopping-variation/2nd_Ext/Attempts_Distribution_light.png" width="300" align="right"/>
</picture>


As for the number of attempts, our distribution is as follow:



These choices are based on our previous observations and meant to simulate an extreme and yet realistic variety of optional stopping applied in a set studies.  In fact, they depict a population of researchers who often add a few number of new observations to their studies after inrush data collection, and it is less likely that they perform the optional stopping more than 1 times. 

Looking at the chance of finding significant, we see 

<!-- Results from Nov 26 Distro Full Run -->
=== "ɑ = 0.05"

	<figure>
	  <picture>
	    <source 
	        srcset="/studies/figures/optional-stopping-variation/2nd_Ext/2nd_Ext_PC_Dist_PFS_alpha_0.05_Optional_Stopping_dark.png"
	        media="(prefers-color-scheme: dark)">
	    <img src="/studies/figures/optional-stopping-variation/2nd_Ext/2nd_Ext_PC_Dist_PFS_alpha_0.05_Optional_Stopping_light.png" />
	  </picture>
	</figure>

=== "0.005"

	<figure>
	  <picture>
	    <source 
	        srcset="/studies/figures/optional-stopping-variation/2nd_Ext/2nd_Ext_PC_Dist_PFS_alpha_0.005_Optional_Stopping_dark.png"
	        media="(prefers-color-scheme: dark)">
	    <img src="/studies/figures/optional-stopping-variation/2nd_Ext/2nd_Ext_PC_Dist_PFS_alpha_0.005_Optional_Stopping_light.png" />
	  </picture>
	</figure>

=== "0.0005"

	<figure>
	  <picture>
	    <source 
	        srcset="/studies/figures/optional-stopping-variation/2nd_Ext/2nd_Ext_PC_Dist_PFS_alpha_5e-04_Optional_Stopping_dark.png"
	        media="(prefers-color-scheme: dark)">
	    <img src="/studies/figures/optional-stopping-variation/2nd_Ext/2nd_Ext_PC_Dist_PFS_alpha_5e-04_Optional_Stopping_light.png" />
	  </picture>
	</figure>



Looking at the level of effect size bias, we see

<!-- Results from Nov 26 Distro Full Run -->
=== "ɑ = 0.05"

	<figure>
	  <picture>
	    <source 
	        srcset="/studies/figures/optional-stopping-variation/2nd_Ext/2nd_Ext_PC_Dist_ES_Bias_alpha_0.05_Optional_Stopping_dark.png"
	        media="(prefers-color-scheme: dark)">
	    <img src="/studies/figures/optional-stopping-variation/2nd_Ext/2nd_Ext_PC_Dist_ES_Bias_alpha_0.05_Optional_Stopping_light.png" />
	  </picture>
	</figure>

=== "0.005"

	<figure>
	  <picture>
	    <source 
	        srcset="/studies/figures/optional-stopping-variation/2nd_Ext/2nd_Ext_PC_Dist_ES_Bias_alpha_0.005_Optional_Stopping_dark.png"
	        media="(prefers-color-scheme: dark)">
	    <img src="/studies/figures/optional-stopping-variation/2nd_Ext/2nd_Ext_PC_Dist_ES_Bias_alpha_0.005_Optional_Stopping_light.png" />
	  </picture>
	</figure>

=== "0.0005"

	<figure>
	  <picture>
	    <source 
	        srcset="/studies/figures/optional-stopping-variation/2nd_Ext/2nd_Ext_PC_Dist_ES_Bias_alpha_5e-04_Optional_Stopping_dark.png"
	        media="(prefers-color-scheme: dark)">
	    <img src="/studies/figures/optional-stopping-variation/2nd_Ext/2nd_Ext_PC_Dist_ES_Bias_alpha_5e-04_Optional_Stopping_light.png" />
	  </picture>
	</figure>

### Meta-Analysis

Another difference of our last extension is the fact that we changed our Journal’s configuration in order to be able to collect batches of results. 

!!! journal “Configuration: Journal”
	```json
	{}
	```





As discussed in Meta Analysis, we can use these batches as our meta analysis pool, and consequently apply different meta analyses methods on them. Later these results can be exported and analyzed as shown in Maassen’s Simulation. 

Here we competed two batch sizes, *K = {8, 24}*. 


Egger's

=== "K = 8"

	<figure>
	  <picture>
	    <source 
	        srcset="/studies/figures/optional-stopping-variation/2nd_Ext/2nd_Ext_EggersTestEstimator_k_8_Optional_Stopping_dark.png"
	        media="(prefers-color-scheme: dark)">
	    <img src="/studies/figures/optional-stopping-variation/2nd_Ext/2nd_Ext_EggersTestEstimator_k_8_Optional_Stopping_light.png" />
	  </picture>
	</figure>

=== "K = 24"

	<figure>
	  <picture>
	    <source 
	        srcset="/studies/figures/optional-stopping-variation/2nd_Ext/2nd_Ext_EggersTestEstimator_k_24_Optional_Stopping_dark.png"
	        media="(prefers-color-scheme: dark)">
	    <img src="/studies/figures/optional-stopping-variation/2nd_Ext/2nd_Ext_EggersTestEstimator_k_24_Optional_Stopping_light.png" />
	  </picture>
	</figure>


Rank Correlation

=== "K = 8"

	<figure>
	  <picture>
	    <source 
	        srcset="/studies/figures/optional-stopping-variation/2nd_Ext/2nd_Ext_RankCorrelation_k_8_Optional_Stopping_dark.png"
	        media="(prefers-color-scheme: dark)">
	    <img src="/studies/figures/optional-stopping-variation/2nd_Ext/2nd_Ext_RankCorrelation_k_8_Optional_Stopping_light.png" />
	  </picture>
	</figure>

=== "K = 24"

	<figure>
	  <picture>
	    <source 
	        srcset="/studies/figures/optional-stopping-variation/2nd_Ext/2nd_Ext_RankCorrelation_k_24_Optional_Stopping_dark.png"
	        media="(prefers-color-scheme: dark)">
	    <img src="/studies/figures/optional-stopping-variation/2nd_Ext/2nd_Ext_RankCorrelation_k_24_Optional_Stopping_light.png" />
	  </picture>
	</figure>


## Third Extension


Looking at the chance of finding significant, we see 

<!-- Results from Nov 26 Double Distro Full Run -->
<figure>
  <picture>
    <source 
        srcset="/studies/figures/optional-stopping-variation/3rd_Ext/3rd_Ext_Double_Dist_PFS_Optional_Stopping_dark.png"
        media="(prefers-color-scheme: dark)">
    <img src="/studies/figures/optional-stopping-variation/3rd_Ext/3rd_Ext_Double_Dist_PFS_Optional_Stopping_dark.png.png" />
  </picture>
</figure>

<figure>
  <picture>
    <source 
        srcset="/studies/figures/optional-stopping-variation/3rd_Ext/3rd_Ext_Double_Dist_ES_Bias_Optional_Stopping_dark.png"
        media="(prefers-color-scheme: dark)">
    <img src="/studies/figures/optional-stopping-variation/3rd_Ext/3rd_Ext_Double_Dist_ES_Bias_Optional_Stopping_dark.png" />
  </picture>
</figure>

<figure>
  <picture>
    <source 
        srcset="/studies/figures/optional-stopping-variation/3rd_Ext/3rd_Ext_Double_Dist_Eggers_Optional_Stopping_dark.png"
        media="(prefers-color-scheme: dark)">
    <img src="/studies/figures/optional-stopping-variation/3rd_Ext/3nd_Ext_Double_Dist_Eggers_Optional_Stopping_dark.pngg" />
  </picture>
</figure>


## Appendix A: Effect of Different Number of Attemps in Optional Stopping

#### Effect Size Bias

<!-- Results from Nov 26 Full Run -->
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

<!-- Results from Nov 20, Compared to Nov 26 Full Run -->
=== "2 Dependent Variables"

	=== "0.05"

		<figure>
		  <picture>
		    <source 
		        srcset="/studies/figures/optional-stopping-variation/1st_Ext/Comp_App_A_Attemps_Effect_ES_Bias_0.05_dvs_2_Optional_Stopping_dark.png"
		        media="(prefers-color-scheme: dark)">
		    <img src="/studies/figures/optional-stopping-variation/1st_Ext/Comp_App_A_Attemps_Effect_ES_Bias_0.05_dvs_2_Optional_Stopping_light.png" />
		  </picture>
		</figure>

	=== "0.005"

		<figure>
		  <picture>
		    <source 
		        srcset="/studies/figures/optional-stopping-variation/1st_Ext/Comp_App_A_Attemps_Effect_ES_Bias_0.005_dvs_2_Optional_Stopping_dark.png"
		        media="(prefers-color-scheme: dark)">
		    <img src="/studies/figures/optional-stopping-variation/1st_Ext/Comp_App_A_Attemps_Effect_ES_Bias_0.005_dvs_2_Optional_Stopping_light.png" />
		  </picture>
		</figure>

	=== "0.0005"

		<figure>
		  <picture>
		    <source 
		        srcset="/studies/figures/optional-stopping-variation/1st_Ext/Comp_App_A_Attemps_Effect_ES_Bias_5e-04_dvs_2_Optional_Stopping_dark.png"
		        media="(prefers-color-scheme: dark)">
		    <img src="/studies/figures/optional-stopping-variation/1st_Ext/Comp_App_A_Attemps_Effect_ES_Bias_5e-04_dvs_2_Optional_Stopping_light.png" />
		  </picture>
		</figure>

=== "4 Dependent Variables"

	=== "0.05"

		<figure>
		  <picture>
		    <source 
		        srcset="/studies/figures/optional-stopping-variation/1st_Ext/Comp_App_A_Attemps_Effect_ES_Bias_0.05_dvs_4_Optional_Stopping_dark.png"
		        media="(prefers-color-scheme: dark)">
		    <img src="/studies/figures/optional-stopping-variation/1st_Ext/Comp_App_A_Attemps_Effect_ES_Bias_0.05_dvs_4_Optional_Stopping_light.png" />
		  </picture>
		</figure>

	=== "0.005"

		<figure>
		  <picture>
		    <source 
		        srcset="/studies/figures/optional-stopping-variation/1st_Ext/Comp_App_A_Attemps_Effect_ES_Bias_0.005_dvs_4_Optional_Stopping_dark.png"
		        media="(prefers-color-scheme: dark)">
		    <img src="/studies/figures/optional-stopping-variation/App_A_Attemps_Effect_ES_Bias_0.005_dvs_4_Optional_Stopping_light.png" />
		  </picture>
		</figure>

	=== "0.0005"

		<figure>
		  <picture>
		    <source 
		        srcset="/studies/figures/optional-stopping-variation/1st_Ext/Comp_App_A_Attemps_Effect_ES_Bias_5e-04_dvs_4_Optional_Stopping_dark.png"
		        media="(prefers-color-scheme: dark)">
		    <img src="/studies/figures/optional-stopping-variation/1st_Ext/Comp_App_A_Attemps_Effect_ES_Bias_5e-04_dvs_4_Optional_Stopping_light.png" />
		  </picture>
		</figure>