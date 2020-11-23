# Sample Size Variation

In this study, we will investigate the effect of sample size variation, *N*, on the level of bias, and probablity of finding significant. We will also investigate whether Researcher's perseverance to design studies with *N ~ 20* is driven by an unwritten property of this specific sample size.

## Study Design

As with our [selection variation](/studies/selection-variation) study, we simulate a range of parameters; however, we use only one of the selection policies, *Initial<sub>S</sub>*, as we have shown that there is no meaningful difference between them, see [here](/studies/selection-variation.md#results).

- *μ* ∈ [0, 1]
- *P<sub>b</sub>* ∈ {0, 0.1, 0.25, 0.5, 0.75, 0.9, 0.95}
- *m* ∈ {2, 3, 4, 5, 6}
- *N* ∈ {8, 9, ..., 99, 100}
- *Initial<sub>S</sub>*, `["sig", "effect > 0", "random"], ["effect > 0", "min(pvalue)"], ["effect < 0", "max(pvalue)"]`

In order to get an accurate picture of landscape of ES Bias, and PFS, we will simulate a full range of true effect sizes, as well as a wide range of possible sample sizes. 

## Results

Figure below shows the contour plot of PFS against true effect size, *μ* (y-axis), and sample size, *N* (x-axis). Additionally, each row is dedicated to a specific level of publication bias, *P<sub>b</sub>*, and each column presents set of studies with different number of dependent variables, *m*. Finally, the vertical red indicator accross all plots corresponds to *N = 20*.

As we can see by following the trace of yellow region, ie., a region with highest PFS, Researcher's chance of finding significant results with higher effect sizes declines as the number of dependent variables decreases. Notice the shift of the yellow region from right to left accross all configurations as we increase the number of dependent variables. 

More interestingly, in almost all configurations, the yellow region is almost available for *N < 20*. What this entails is the fact that *N ≲ 20* always stays a viable region with high chance of finding signficant results — despite all variation of all other parameters —, *with m = 2 providing the highest chance of finding something significant among studies with N ≲ 20.*

Expectedly, researcher's chance of finding significant result declines as we lower the ɑ-level. However, looking closely at results, we can conclude while the researcher does not have as high of a chance of finding significant results, ie., yellow region with [80%, 100%], his chance of finding significant is still quite high and varies between 0% to 80%, with [20%, 80%] providing plenty oppurtunities. 

We should also point out the fact that even with very low ɑ-level, researches with *N ≲ 20* are providing higher chance of finding significant. More noticably, increasing the publication bias streches this chance. In fact, we speculate that journals with higher publication bias are most likely accumulating more studies with *N ≲ 20*.

### Landscape of *Probablity of Finding Significant*

=== "0.05"

	<figure>
	  <picture>
	    <source 
	        srcset="/studies/figures/sample-size-variation/PFS_0.05_N_Range_dark.png"
	        media="(prefers-color-scheme: dark)">
	    <img src="/studies/figures/sample-size-variation/PFS_0.05_N_Range_light.png" />
	  </picture>
	</figure>

=== "0.005"

	<figure>
	  <picture>
	    <source 
	        srcset="/studies/figures/sample-size-variation/PFS_0.005_N_Range_dark.png"
	        media="(prefers-color-scheme: dark)">
	    <img src="/studies/figures/sample-size-variation/PFS_0.005_N_Range_light.png" />
	  </picture>
	</figure>

=== "0.0005"

	<figure>
	  <picture>
	    <source 
	        srcset="/studies/figures/sample-size-variation/PFS_5e-04_N_Range_dark.png"
	        media="(prefers-color-scheme: dark)">
	    <img src="/studies/figures/sample-size-variation/PFS_5e-04_N_Range_light.png" />
	  </picture>
	</figure>

### Landscape of *ES Bias*

Looking at the level of effect size bias, we oberve an interesting phenomena where increasing the number of depedent variables, *m*, streches the effect size landscape toward right, meaning as we increase *m*, we will most definitely incrase our bias. Noticably, increasing the publication bias, will shift our bias toward studies with lower effect size and larger sample size. Combined with our observations from PFS, we can speculate that journals with high publication bias are either accumulating studies with low sample size and large biases (*d > 0.6*), or studies with large sample size and medium biases, *0.0 < d < 0.6*.

Surprisingly, we can see that lowering ɑ will shift the bias toward higher effect sizes. As we discussed during the analysis of PFS, this phenomena entails that as we lower the ɑ, we reduce researcher's chance of finding significant results while we force those significants results to have a higher bias. Moreover, we can see the devestating effect of lower ɑ-level. In fact, to add to our conclusion, we see that journals with lower ɑ-level, will tend to accumulate publications with high biases toward upper bound of true effect size. In fact, their effect sizes look more dramatic while being gravely incorrect. 

=== "0.05"

	<figure>
	  <picture>
	    <source 
	        srcset="/studies/figures/sample-size-variation/ES_Bias_0.05_N_Range_dark.png"
	        media="(prefers-color-scheme: dark)">
	    <img src="/studies/figures/sample-size-variation/ES_Bias_0.05_N_Range_light.png" />
	  </picture>
	</figure>

=== "0.005"

	<figure>
	  <picture>
	    <source 
	        srcset="/studies/figures/sample-size-variation/ES_Bias_0.005_N_Range_dark.png"
	        media="(prefers-color-scheme: dark)">
	    <img src="/studies/figures/sample-size-variation/ES_Bias_0.005_N_Range_light.png" />
	  </picture>
	</figure>

=== "0.0005"

	<figure>
	  <picture>
	    <source 
	        srcset="/studies/figures/sample-size-variation/ES_Bias_5e-04_N_Range_dark.png"
	        media="(prefers-color-scheme: dark)">
	    <img src="/studies/figures/sample-size-variation/ES_Bias_5e-04_N_Range_light.png" />
	  </picture>
	</figure>

<!-- 
### Landscape of *Significant P-values*


=== "0.05"

	<figure>
	  <picture>
	    <source 
	        srcset="/studies/figures/sample-size-variation/MSP_0.05_N_Range_dark.png"
	        media="(prefers-color-scheme: dark)">
	    <img src="/studies/figures/sample-size-variation/MSP_0.05_N_Range_light.png" />
	  </picture>
	</figure>

=== "0.005"

	<figure>
	  <picture>
	    <source 
	        srcset="/studies/figures/sample-size-variation/MSP_0.005_N_Range_dark.png"
	        media="(prefers-color-scheme: dark)">
	    <img src="/studies/figures/sample-size-variation/MSP_0.005_N_Range_light.png" />
	  </picture>
	</figure>

=== "0.0005"

	<figure>
	  <picture>
	    <source 
	        srcset="/studies/figures/sample-size-variation/MSP_5e-04_N_Range_dark.png"
	        media="(prefers-color-scheme: dark)">
	    <img src="/studies/figures/sample-size-variation/MSP_5e-04_N_Range_light.png" />
	  </picture>
	</figure> 
-->