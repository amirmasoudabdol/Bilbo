# Optional Stopping Variation

After investigating the influecens of initial selection logic, and sample size, here, we will investigate the effect of applying several variants of Optional Stopping on the probability of finding significant results and the level of effect size bias. Similarly to our [Sample Size Variation](/studies/sample-size-variation.md) and [Selection Variation](/studies/selection-variation.md) studies, we will cover a range of parameters in order to draw a landscape of our both target metrics, e.g., Probability of Finding Significant (PFS), and Effect Size Bias, (ESB). 

## Study Design

Based on results of our sample size study, we will adjust our sample size parameters, from simulating the entire range of [8, 100] to a discrete set of values. We think our approximation can still provide an overview of the interaction as [we observed](/studies/sample-size-variation.md) a predictable change of PFS and ES Bias along a fine-grind range of *N*. For the rest of Experiment’s parameters, we use the same set of parameters in order to draw a complete and comparable picture as before.

- *μ* ∈ [0, 1]
- *m* ∈ {2, 4, 6}
- *N* ∈ {10, 20, 30, 40, 50, 60, 70, 80}
- *P<sub>b</sub>* ∈ {0, 0.1, 0.25, 0.5, 0.75, 0.9, 0.95}

In order to cover a range of optional stopping approaches, we start by simulating a more conventional optional stopping and narrow down our search parameters.

## Optional Stopping on Both Groups

In our first study, we simulate the optional stopping by adding new observations as much as of *S* percent of the current sample size to every group. For example, a group with *N = 20* will have 22 observations after adding 10% new observations, *S = 10%*. Additionally, we vary the maxiumum number of trial that Researcher could perform the optional stopping with the given *S*. For instance, a Researcher — who is allowed to perform a maximum of 5 optional stopping trials — will continue adding 2 new obervations, for maximum number of 5 times, to each group until it finds a significant result. The variation of described parameters is as follow:

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

For our first results, we present the probablity of finding significant in the following set of figures. We present three main set of figures, each showcasing results from studies with different number of dependent variables, ie., 2, 4, 6. Additionally, we filtered our results for *T = 1*. Appendix A will discuss the effect of number of attempts.

In both cases, as we increase *S*, while we see some growth (and a shift toward left) in the yellow region of the contour plot, (region with highest probablity of finding significant) we do not believe that this growth or even the overall change of the landscape is noticeably different from our benchmark column — first column with no optional stopping.

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

In the case of effect size bias, as we showed in the sample size variation study, we see that the level of bias is higher as we add more dependent variables to our studies. Additionally, while optional stopping does not increase the overall level of bias, it shifts it toward higher sample sizes. This is expected, as a 

Moreover, we observe that the level of bias lowers as we increase *S*; however, the region that bias appears in the contour plot doesn’t move and only shrinks. We can also see that the bias region moves higher in the y-axes (ie., true effect size) as we increase the *α* level. 

Finally, we can see the influence of publication bias on the effect size bias. Expectedly, increasing the publication bias will reduce our overall effect size bias while it still includes highly biased studies within the region of small true effect sizes.

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

In the figure below, we can see the comparison between this study and the one performed previously, ie., adding new observation to both groups. In contrast to our expectation, adding new observation only to treatment groups does not have a considerable impact on the level of bias. This can be seen in the figure by tracking the slightly wider bias region in “Treatment” columns compared to their “Both” counterparts. 

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

<!-- Excluding 4! There is so little difference to see anyway! -->
<!-- === "4 Dependent Variables"

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
        </figure> -->

## Second Extension: Optional Stopping Field

<picture>
    <source 
        srcset="/studies/figures/optional-stopping-variation/Ratio_Distribution_dark.png"
        media="(prefers-color-scheme: dark)">
    <img src="/studies/figures/optional-stopping-variation/Ratio_Distribution_light.png" width="50%" align="right"/>
</picture>

In our second extension of our study, we investigate the effect of *variable optional stopping parameters*. 

<picture>
    <source 
        srcset="/studies/figures/optional-stopping-variation/Attempts_Distribution_dark.png"
        media="(prefers-color-scheme: dark)">
    <img src="/studies/figures/optional-stopping-variation/Attempts_Distribution_light.png" width="50%" align="right"/>
</picture>

In contrast to our previous simulations where we simulated a range of parameters, in this simulation we draw a random value for two main parameters of the optional stopping, `ratio` and `n_attempts`. Our choices for distribution of `ratio` and `n_attempts` is based on fine-tuned *truncated normal distribution*s as shown here. These distribution are mimicing a scenario in which Researches prefer to addi/collect fewer new observations, besides they ought to repeat this process as seldemly as possible.

<br>

!!! hackingstrategy
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
                    "ratio": {
                        "dist": "truncated_normal_distribution",
                        "mean": 0.1,
                        "stddev": 0.125,
                        "lower": 0.1,
                        "upper": 0.5,
                    },
                    "n_attempts": {
                        "dist": "truncated_normal_distribution",
                        "mean": 1,
                        "stddev": 1.25,
                        "lower": 1,
                        "upper": 5
                    },
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

As before, it is difficult to observe any meaningful changes in the landscape of PFS; however, we are able to spot more minor changes. 

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

While the changes to the landscape of PFS is almost invisible, we are surely able to observe some changes in the level of bias. As before, althought these changes are not drastic, they tend to confirm that optional stopping tends to reduce the level of bias. However, this is only more prevalent in lower effect sizes within lower sample sizes, *lower left region of figures*. In contrast, within the range of higher effect sizes, optional stopping tend to increase the bias ever so slightly.

It is important to point out that while we see minimal improvment on the level of bias in studies with optional stopping, this does not mean that those studies are now better. In contrast, our results indicates the detrimental effect of optional stopping on published studies. 

> ***If a study is already biased, optional stopping does not reduce the bias enough that makes it a good study; in fact, it burries its bias under higher sample size, and gives Journals a wrong incentive to publish the study.***

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

Another difference of our last extension is the fact that we changed our Journal’s configuration in order to be able to collect batches of results. Here we competed two batch sizes, *K = {8, 24}*. 

!!! journal "Configuration: Journal"
    ```json
    {
      ...
      "journal_parameters": {
        "max_pubs": k,
        "selection_strategy": {
            "name": "SignificantSelection",
            "pub_bias": p,
            "alpha": ɑ,
            "side": 0,
        },
        "meta_analysis_metrics": [
            {
                "name": "RandomEffectEstimator",
                "estimator": "DL"
            },
            {
                "name": "EggersTestEstimator",
                "alpha": 0.1
            },
            {
                "name": "RankCorrelation",
                "alpha": 0.1
            }
        ]
      }
      ...
    }
    ```

As discussed in [Meta Analysis](/meta-analyses.md), we can use these batches as our meta analysis pool, and consequently apply different meta analyses methods on them. Later these results can be exported and analyzed as shown in [Maassen’s Simulation](/examples/esther_first_year.md). 

While we do not expect Egger's Test to be able to detect the influence of optional stopping on publication bias, we are curious to see how it performs within the range of our parameters. As we can see in the figure below, Egger's test clearly performs better with larger sample sizes. Moreover, as expected, Egger gets more confident as publication level raises. As shown in [Maassen’s Simulation](/examples/esther_first_year.md), Egger performs much better in lower ɑ-levels as well. In addtion, notice the fact that Egger's Test is only capable of detecting high (*> 50%*) publication bias within very extreme *P<sub>b</sub>* values, and even then only within very high true effect sizes and low sample sizes.

> In fact, Egger's Test is fairly ineffective in a large region of our parameters set. The good news is, its most effective region lies within small sample sizes, *N ≲ 20*. 

In all cases, we can see a slightly more power withing studies undergone the optional stopping. However, as one would guess this is not to the courtesy of Egger's Test in detecting the influence of optional stopping. In fact, this is shows how optional stopping can pollute publication bias metrics like Egger's Test.



<!-- Results from Nov 26 Distro - Full Run -->
=== "K = 8"

    === "2 Dependent Variables"

        <figure>
          <picture>
            <source 
                srcset="/studies/figures/optional-stopping-variation/2nd_Ext/2nd_Ext_EggersTestEstimator_k_8_dvs_2_Optional_Stopping_dark.png"
                media="(prefers-color-scheme: dark)">
            <img src="/studies/figures/optional-stopping-variation/2nd_Ext/2nd_Ext_EggersTestEstimator_k_8_dvs_2_Optional_Stopping_light.png" />
          </picture>
        </figure>

    === "4 Dependent Variables"

        <figure>
          <picture>
            <source 
                srcset="/studies/figures/optional-stopping-variation/2nd_Ext/2nd_Ext_EggersTestEstimator_k_8_dvs_4_Optional_Stopping_dark.png"
                media="(prefers-color-scheme: dark)">
            <img src="/studies/figures/optional-stopping-variation/2nd_Ext/2nd_Ext_EggersTestEstimator_k_8_dvs_4_Optional_Stopping_light.png" />
          </picture>
        </figure>

    === "6 Dependent Variables"

        <figure>
          <picture>
            <source 
                srcset="/studies/figures/optional-stopping-variation/2nd_Ext/2nd_Ext_EggersTestEstimator_k_8_dvs_6_Optional_Stopping_dark.png"
                media="(prefers-color-scheme: dark)">
            <img src="/studies/figures/optional-stopping-variation/2nd_Ext/2nd_Ext_EggersTestEstimator_k_8_dvs_6_Optional_Stopping_light.png" />
          </picture>
        </figure>

=== "K = 24"

    === "2 Dependent Variables"

        <figure>
          <picture>
            <source 
                srcset="/studies/figures/optional-stopping-variation/2nd_Ext/2nd_Ext_EggersTestEstimator_k_24_dvs_2_Optional_Stopping_dark.png"
                media="(prefers-color-scheme: dark)">
            <img src="/studies/figures/optional-stopping-variation/2nd_Ext/2nd_Ext_EggersTestEstimator_k_24_dvs_2_Optional_Stopping_light.png" />
          </picture>
        </figure>

    === "4 Dependent Variables"

        <figure>
          <picture>
            <source 
                srcset="/studies/figures/optional-stopping-variation/2nd_Ext/2nd_Ext_EggersTestEstimator_k_24_dvs_4_Optional_Stopping_dark.png"
                media="(prefers-color-scheme: dark)">
            <img src="/studies/figures/optional-stopping-variation/2nd_Ext/2nd_Ext_EggersTestEstimator_k_24_dvs_4_Optional_Stopping_light.png" />
          </picture>
        </figure>

    === "6 Dependent Variables"

        <figure>
          <picture>
            <source 
                srcset="/studies/figures/optional-stopping-variation/2nd_Ext/2nd_Ext_EggersTestEstimator_k_24_dvs_6_Optional_Stopping_dark.png"
                media="(prefers-color-scheme: dark)">
            <img src="/studies/figures/optional-stopping-variation/2nd_Ext/2nd_Ext_EggersTestEstimator_k_24_dvs_6_Optional_Stopping_light.png" />
          </picture>
        </figure>


<!-- Rank Correlation

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
    </figure> -->


## Third Extension

<picture>
    <source 
        srcset="/studies/figures/optional-stopping-variation/N_Distribution_dark.png"
        media="(prefers-color-scheme: dark)">
    <img src="/studies/figures/optional-stopping-variation/N_Distribution_light.png" width="300" align="right"/>
</picture>

Looking at the chance of finding significant, we see 


!!! datastrategy "Configuration: Data Strategy"
    ```json
    {
        "experiment_parameters": {
        "n_reps": 1,
        "n_conditions": 2,
        "n_dep_vars": 2,
        "n_obs": {
            "dist": "piecewise_constant_distribution",
            "intervals": [6, 24, 300],
            "densities": [0.75,  0.25]
        },
        "data_strategy": {
            "name": "LinearModel",
            "measurements": {
                "dist": "mvnorm_distribution",
                "means": [0.0, 0.0, μ, μ],
                "covs": 0.5,
                "stddevs": 1.0
            }
        },
        "effect_strategy": {
            "name": "StandardizedMeanDifference"
        },
        "test_strategy": {
            "name": "TTest",
            "alpha": 0.05,
            "alternative": "TwoSided",
            "var_equal": true
        }
    }
    ```


<!-- Results from Nov 26 Double Distro Full Run -->
<figure>
  <picture>
    <source 
        srcset="/studies/figures/optional-stopping-variation/3rd_Ext/3rd_Ext_Double_Dist_PFS_Optional_Stopping_dark.png"
        media="(prefers-color-scheme: dark)">
    <img src="/studies/figures/optional-stopping-variation/3rd_Ext/3rd_Ext_Double_Dist_PFS_Optional_Stopping_light.png" />
  </picture>
</figure>

<figure>
  <picture>
    <source 
        srcset="/studies/figures/optional-stopping-variation/3rd_Ext/3rd_Ext_Double_Dist_ES_Bias_Optional_Stopping_dark.png"
        media="(prefers-color-scheme: dark)">
    <img src="/studies/figures/optional-stopping-variation/3rd_Ext/3rd_Ext_Double_Dist_ES_Bias_Optional_Stopping_light.png" />
  </picture>
</figure>

<figure>
  <picture>
    <source 
        srcset="/studies/figures/optional-stopping-variation/3rd_Ext/3rd_Ext_Double_Dist_Eggers_Optional_Stopping_dark.png"
        media="(prefers-color-scheme: dark)">
    <img src="/studies/figures/optional-stopping-variation/3rd_Ext/3nd_Ext_Double_Dist_Eggers_Optional_Stopping_light.png" />
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