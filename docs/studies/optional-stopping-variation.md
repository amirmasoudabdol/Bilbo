# Optional Stopping Variation

In this study, we will investigate the effect of applying several variants of Optional Stopping on the probability of finding significant results and the level of bias on the aggregate effect size. 

Similarly to our Sample Size Variation and Selection Variation studies, we will cover a range of parameters to draw a landscape of our both targets. Based on results of our sample size study, we adjusted the range of sample sizes from simulating the entire range of [8, 100], we simulate a more discrete set of values. As discussed, this is based on the  observed linearity of PFS and ES Bias along the fine grind range of *N*. 

For the rest of Experiment’s parameters, we simulate a range of values as follow:

- *μ* ∈ [0, 1]
- *m* ∈ {2, 4, 6}
- *N* ∈ , {10, 20, 30, 40, 50, 60, 70, 80, 90, 100}
- *P<sub>b</sub>* ∈ {0, 0.1, 0.25, 0.5, 0.75, 0.9, 0.95}

In order to cover a range of optional stopping approaches, we start by simulating a more conventional optional stopping and narrow down our search parameters to find the most devastating form of optional stopping. 

As before, in each study, we investigate the effect of our configurations grid on two main metrics, Probability of Finding Significant (PFS), and Effect Size Bias, (ESB). 

## Optional Stopping on Both Groups

In our first study, we simulate the optional stopping by adding new observation as much as *S* percent of the current sample size. For instance, if our groups 


### Probability of Finding Significant



##### 2 Dependent Variables

=== "0.05"

	<figure>
	  <picture>
	    <source 
	        srcset="/studies/figures/optional-stopping-variation/PFS_0.05_attemps_1_dvs_2_Optional_Stopping_dark.png"
	        media="(prefers-color-scheme: dark)">
	    <img src="/studies/figures/optional-stopping-variation/PFS_0.05_attemps_1_dvs_2_Optional_Stopping_light.png" />
	  </picture>
	</figure>

=== "0.005"

	<figure>
	  <picture>
	    <source 
	        srcset="/studies/figures/optional-stopping-variation/PFS_0.005_attemps_1_dvs_2_Optional_Stopping_dark.png"
	        media="(prefers-color-scheme: dark)">
	    <img src="/studies/figures/optional-stopping-variation/PFS_0.005_attemps_1_dvs_2_Optional_Stopping_light.png" />
	  </picture>
	</figure>

=== "0.0005"

	<figure>
	  <picture>
	    <source 
	        srcset="/studies/figures/optional-stopping-variation/PFS_5e-04_attemps_1_dvs_2_Optional_Stopping_dark.png"
	        media="(prefers-color-scheme: dark)">
	    <img src="/studies/figures/optional-stopping-variation/PFS_5e-04_attemps_1_dvs_2_Optional_Stopping_light.png" />
	  </picture>
	</figure>

##### 4 Dependent Variables

=== "0.05"

	<figure>
	  <picture>
	    <source 
	        srcset="/studies/figures/optional-stopping-variation/PFS_0.05_attemps_1_dvs_4_Optional_Stopping_dark.png"
	        media="(prefers-color-scheme: dark)">
	    <img src="/studies/figures/optional-stopping-variation/PFS_0.05_attemps_1_dvs_4_Optional_Stopping_light.png" />
	  </picture>
	</figure>

=== "0.005"

	<figure>
	  <picture>
	    <source 
	        srcset="/studies/figures/optional-stopping-variation/PFS_0.005_attemps_1_dvs_4_Optional_Stopping_dark.png"
	        media="(prefers-color-scheme: dark)">
	    <img src="/studies/figures/optional-stopping-variation/PFS_0.005_attemps_1_dvs_4_Optional_Stopping_light.png" />
	  </picture>
	</figure>

=== "0.0005"

	<figure>
	  <picture>
	    <source 
	        srcset="/studies/figures/optional-stopping-variation/PFS_5e-04_attemps_1_dvs_4_Optional_Stopping_dark.png"
	        media="(prefers-color-scheme: dark)">
	    <img src="/studies/figures/optional-stopping-variation/PFS_5e-04_attemps_1_dvs_4_Optional_Stopping_light.png" />
	  </picture>
	</figure>


### Effect Size Bis

##### 2 Dependent Variables

=== "0.05"

	<figure>
	  <picture>
	    <source 
	        srcset="/studies/figures/optional-stopping-variation/ES_Bias_0.05_attemps_1_dvs_2_Optional_Stopping_dark.png"
	        media="(prefers-color-scheme: dark)">
	    <img src="/studies/figures/optional-stopping-variation/ES_Bias_0.05_attemps_1_dvs_2_Optional_Stopping_light.png" />
	  </picture>
	</figure>

=== "0.005"

	<figure>
	  <picture>
	    <source 
	        srcset="/studies/figures/optional-stopping-variation/ES_Bias_0.005_attemps_1_dvs_2_Optional_Stopping_dark.png"
	        media="(prefers-color-scheme: dark)">
	    <img src="/studies/figures/optional-stopping-variation/ES_Bias_0.005_attemps_1_dvs_2_Optional_Stopping_light.png" />
	  </picture>
	</figure>

=== "0.0005"

	<figure>
	  <picture>
	    <source 
	        srcset="/studies/figures/optional-stopping-variation/ES_Bias_5e-04_attemps_1_dvs_2_Optional_Stopping_dark.png"
	        media="(prefers-color-scheme: dark)">
	    <img src="/studies/figures/optional-stopping-variation/ES_Bias_5e-04_attemps_1_dvs_2_Optional_Stopping_light.png" />
	  </picture>
	</figure>

##### 4 Dependent Variables

=== "0.05"

	<figure>
	  <picture>
	    <source 
	        srcset="/studies/figures/optional-stopping-variation/ES_Bias_0.05_attemps_1_dvs_4_Optional_Stopping_dark.png"
	        media="(prefers-color-scheme: dark)">
	    <img src="/studies/figures/optional-stopping-variation/ES_Bias_0.05_attemps_1_dvs_4_Optional_Stopping_light.png" />
	  </picture>
	</figure>

=== "0.005"

	<figure>
	  <picture>
	    <source 
	        srcset="/studies/figures/optional-stopping-variation/ES_Bias_0.005_attemps_1_dvs_4_Optional_Stopping_dark.png"
	        media="(prefers-color-scheme: dark)">
	    <img src="/studies/figures/optional-stopping-variation/ES_Bias_0.005_attemps_1_dvs_4_Optional_Stopping_light.png" />
	  </picture>
	</figure>

=== "0.0005"

	<figure>
	  <picture>
	    <source 
	        srcset="/studies/figures/optional-stopping-variation/ES_Bias_5e-04_attemps_1_dvs_4_Optional_Stopping_dark.png"
	        media="(prefers-color-scheme: dark)">
	    <img src="/studies/figures/optional-stopping-variation/ES_Bias_5e-04_attemps_1_dvs_4_Optional_Stopping_light.png" />
	  </picture>
	</figure>


## First Extension: Optional Stopping *Only* on Treatment Group

### Effect Size Bias

##### 2 Dependent Variables

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

##### 4 Dependent Variables

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

##### 2 Dependent Variables

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

##### 4 Dependent Variables

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

##### 2 Dependent Variables

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

##### 4 Dependent Variables

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