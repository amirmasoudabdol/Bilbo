# Sample Size Variation

In this study, we will investigate the effect of sample size, *N*, on the level of bias, probablity of finding significant, as well as trying to investigate whether Researcher's perseverance to design their studies with *N ~ 20* is driven by an unwritten property of this specific sample size.

## Study Design

As with our [selective variation](/studies/selection-variation) study, we simulate a range of parameters; however, we use only one of the selection policies, as we have shown that there is no meaningful difference between them.

- *μ* ∈ [0, 1]
- *P<sub>b</sub>* ∈ {0, 0.1, 0.25, 0.5, 0.75, 0.9, 0.95}
- *m* ∈ {0, 0.1, 0.25, 0.5, 0.75, 0.9, 0.95}
- *N* ∈ {5, 10, 20, 30, 50, 80}
- *Initial<sub>sel</sub>*, `["sig", "effect > 0", "random"], ["effect > 0", "min(pvalue)"], ["effect < 0", "max(pvalue)"]`

## Results

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