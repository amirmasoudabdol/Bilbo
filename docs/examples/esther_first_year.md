---
title: Maassen et al., 2016
---

# Estimating Effect Size in Meta-analysis in the Presence of Publication Bias and Questionable Research Practices

In this report, we aim to reproduce and expand Maassen's research project. In her project, Maassen evaluated the power of several publication bias tests on studies that have been gone under different questionable research practices. Additionally, she altered the intensity of publication bias in order to asses the volatility of their power's. 

> This paper investigates the impact of publication bias, two questionable research practices (i.e. optional stopping and selective reporting of dependent variables) and their combination on effect size estimates, coverage and power of fixed effect meta-analysis and heterogeneity estimates of random effects meta-analysis. Additionally, the power of three publication bias tests will be estimated, as well as the effect size estimate adjusted for funnel plot asymmetry and the number of trimmed studies from the trim and fill method.
> <p style="text-align:right">  — Maassen</p>

Beyond fixed- and random-effects estimators, the list of publication bias tests includes:

- Egger's Test[@Egger_1997]
- Test of Excess of Significant Findings[@Ioannidis_2007]
- Trim and Fill[@Duval_2000]
- Rank Correlation[@Begg_1994]


## Simulation Design

Maassen has included a range of parameters in her study. The simulation study has been conducted on all combination of parameters from the list below.

- *n* ∈ {2, 5}
- *P<sub>b</sub>* ∈ {0., 0.05, 0.5, 1}
- *K* ∈ {8, 24, 72}
- *N*
    - 75% Small ∈ [6, 21]
    - 25% Large ∈ [22, 300]
- *μ* ∈ {0, 0.147, 0.3835, 0.699375}
- *ɑ* ∈ 0.05
- QRPs
    - None
    - Selective Reporting
    - Selective Reporting
    - Optional Stopping

Starting from the top, the simulation study concerns itself with two main *Experiment Setup*. One with 2, and another with 5 conditions. The sample size, *N*, of each study is drawn from a piecewise linear distribution where 75% of samples are from [6, 21], and the rest are spreading uniformly between 22 and 300. In addition, true means, *μ*, of treatment conditions varies between 4 pre-calculated effect size representing studies with small, medium and large power.

![Maassen's Experiment Design](/examples/figures/Esther_FYP/Esthers_Experiment_Design.png)

In terms of QRPs, two main methods have been utilized, [Selective Reporting](selective-reporting.md), and [Optional Stopping](optional-stopping.md). While the optional stopping has been applied on both study designs (at most 3 times, adding ⅓ ⨉ N new observations), the selective reporting can only be applied on the design with 5 conditions (selecting the outcome with minimum *p*-value). 

Finally, after simulating *K* studies, Maassen applied both meta-analytic methods, and publication bias estimators, and reported their performance.

## SAM's Configuration

As discussed in other examples, visualizing the simulation flow helps us translate our design to SAM's configuration, Figure 2. While the right-hand side of the flowchart shows the main decision workflow, the left-side mainly describes the process of applying different QRPs based on specific simulation configurations.

![</b>Figure 2.</b> Maassen's Simulation Design](/examples/figures/Esther_FYP/Esthers_Simulation.png)

### Decision Strategy

As we discussed, selective reporting is being applied using the decision strategy module. The Researcher will either select the only available outcome if there is only one primary outcome (ie., no selective reporting), or she will select an outcome with minimum *p*-value in the presence of selective reporting, line 4. 

In cases where the Researcher is equipped with optional stopping, she will decide to apply the method if the selected outcome is not significant, line 5. Finally, if optional stopping has been applied more than once on a study, the last result will be selected, line 6.

!!! decisionstrategy "Configuration: _Decision Strategy_"
    === "2 Conditions"
        ```json linenums="1" hl_lines="4 5 7"
        {
          "decision_strategy": {
            "name": "DefaultDecisionMaker",
              "initial_selection_policies": [ ["id == 1"] ],
              "will_start_hacking_decision_policies": [ "!sig" ],
              "stashing_policy": [ "min(pvalue)" ],
              "between_hacks_selection_policies": [ ["last"] ],
              "between_replications_selection_policies": [[""]],
              "will_continue_replicating_decision_policy": [""],
              "submission_decision_policies": [""]
          }
        }
        ```
    === "5 Conditions"
        ```json linenums="1" hl_lines="4 5 7"
        {
          "decision_strategy": {
            "name": "DefaultDecisionMaker",
              "initial_selection_policies": [ ["min(pvalue)"] ],
              "will_start_hacking_decision_policies": [ "!sig" ],
              "stashing_policy": [ "min(pvalue)" ],
              "between_hacks_selection_policies": [ ["last"] ],
              "between_replications_selection_policies": [[""]],
              "will_continue_replicating_decision_policy": [""],
              "submission_decision_policies": [""]
          }
        }
        ```

#### Hacking Strategy

We can configure our hacking strategy as follows. Notice the repetition of [decision and selection policies](/decision-strategies.md#decision-selection-routine) at highlighted lines. This configuration mimics the behavior of "peeking at minimum *p*-value after each step". After addition of ⅓ ⨉ N, the Researcher selects the outcome with minimum *p*-value, and if the _selected outcome_ is significant, she stops and reports the outcome, if not, she continues adding another batch of observations, and repeat this process at most 3 times.

!!! hackingstrategy "Configuration: _Hacking Strategy_"
    ```json linenums="1" hl_lines="16 17 30 31 44 45"
    {
      "probability_of_being_a_hacker": 0 or 1,
      "probability_of_committing_a_hack": 1,
      "hacking_strategies": [
          [
            {
              "name": "OptionalStopping",
              "target": "Both",
              "prevalence": 1,
              "defensibility": 1,
              "max_attempts": 1,
              "n_attempts": 1,
              "num": 0,
              "add_by_fraction": 0.3
            },
            [ ["min(pvalue)"] ],
            ["!sig"]
          ],
          [
            {
              "name": "OptionalStopping",
              "target": "Both",
              "prevalence": 1,
              "defensibility": 1,
              "max_attempts": 1,
              "n_attempts": 1,
              "num": 0,
              "add_by_fraction": 0.3
            },
            [ ["min(pvalue)"] ],
            ["!sig"]
          ],
          [
            {
              "name": "OptionalStopping",
              "target": "Both",
              "prevalence": 1,
              "defensibility": 1,
              "max_attempts": 1,
              "n_attempts": 1,
              "num": 0,
              "add_by_fraction": 0.3
            },
            [ ["min(pvalue)"] ],
            ["!sig"]
          ]
        ]
    }
    ```

## Data, Test, and Effect Strategy

The combination of *Decision Strategy* and *Hacking Strategy* configurations will simulate the process described in Figure 2. Configurations for *Data*, *Test*, and *Effect* strategies have been discussed in more detail in [Bakker et al., 2012](bakker_et_al_2012.md) example.

??? datastrategy "Configuration: _Data Strategy_"
    === "2 Conditions"
        ```json linenums="1" 
        {
          "experiment_parameters": {
            "n_reps": 1,
            "n_conditions": n,
            "n_dep_vars": 1,
            "n_obs": {
              "dist": "piecewise_constant_distribution",
              "intervals": [6, 24, 300],
              "densities": [0.75,  0.25]
            },
            "data_strategy": {
              "name": "LinearModel",
              "measurements": {
                "dist": "mvnorm_distribution",
                  "means": [0.0, μ],
                  "covs": 0.0,
                  "stddevs": 1.0
                }
            }
        }
        ```
    === "5 Conditions"
        ```json linenums="1" 
        {
          "experiment_parameters": {
            "n_reps": 1,
            "n_conditions": n,
            "n_dep_vars": 1,
            "n_obs": {
              "dist": "piecewise_constant_distribution",
              "intervals": [6, 24, 300],
              "densities": [0.75,  0.25]
            },
            "data_strategy": {
              "name": "LinearModel",
              "measurements": {
                "dist": "mvnorm_distribution",
                  "means": [0.0, μ, μ, μ, μ],
                  "covs": 0.0,
                  "stddevs": 1.0
                }
            }
        }
        ```

??? teststrategy "Configuration: _Test Strategy_"
    ```json linenums="1" 
    {
      ...
      "experiment_parameters": {
        ...
        "test_strategy": {
          "name": "TTest",
          "alpha": ɑ,
          "alternative": "TwoSided",
          "var_equal": true
        }
      }
      ...
    }
    ```
    
??? effectstrategy "Configuration: _Effect Strategy_"
    ```json linenums="1" 
    {
      ...
      "experiment_parameters": {
        ...
        "effect_strategy": {
          "name": "MeanDifferences"
        }
      }
      ...
    }
    ```
    
### Journal 

In the case of Maassen, we need to induce different level of publication bias on our [selection](/selection-strategies.md) procedure. Moreover, we need to calculate a set of meta-analysis and publication bias tests after maxing-out the publications pool. These parameters can be set as follow:

??? journal "Journal: _Publication Bias_"
    ```json linenums="1" hl_lines="5-10"
    {
      ...
      "journal_parameters": {
        "max_pubs": K,
        "selection_strategy": {
          "name": "SignificantSelection",
          "pub_bias": Pb,
          "alpha": ɑ,
          "side": 0,
        },
        "meta_analysis_metrics": [
          {
            "name": "FixedEffectEstimator"
          },
          {
            "name": "RandomEffectEstimator",
            "estimator": "DL"
          },
          {
            "name": "EggersTestEstimator",
            "alpha": 0.1
          },
          {
            "name": "TrimAndFill",
            "alpha": 0.1,
            "estimator": "R0",
            "side": "auto"
          },
          {
            "name": "RankCorrelation",
            "alpha": 0.1,
            "alternative": "TwoSided"
          },
          {
            "name": "TestOfObsOverExptSig",
            "alpha": 0.1
          }
        ]
      }
      ...
    }
    ```

## Extended Simulation


In the case of Maassen's simulation, we decided to extend the simulation by covering full range of publication bias, *P<sub>b</sub>*, and true effect size, *μ*. This extension does not change our main body of configuration. We only need to generate more configuration files with different values of *P<sub>b</sub>*, and *μ*.

- **μ ∈ [0, 1]**
- **P<sub>b</sub> ∈ [0., 1.]**

Figures 3–8 illustrate our results in the form of contour plots. The x-axis corresponds to the range of true effect sizes, and y-axis shows the publication bias level, finally contour regions represent the level of bias, or power of our tests.

Staring by the proportion of significant results in our outcomes pool, we notice a regular and expected pattern of higher proportion of significant results with higher true effect sizes and higher rate of publication bias, ie., the yellow region of each plot. Moreover, we see a clear shrinkage in the size of this region as we lower *ɑ*. Furthermore, notice the growth of the darker regions in lower effect sizes; which can be seen as the influence of lowering *ɑ* on diminishing the chance of finding significant results with lower true effect sizes.

<!-- Results from Nov 27 Run -->
<figure>
  <picture>
    <source 
        srcset="/examples/figures/Esther_FYP/Esther_FYP_PFS_Counter_Filled_dark.png" 
        media="(prefers-color-scheme: dark)">
  <img src="/examples/figures/Esther_FYP/Esther_FYP_PFS_Counter_Filled_light.png" /><figcaption aria-hidden="true"><b>Figure 3.</b> Probability of Finding Sig.</figcaption>
  </picture> 
</figure>

Looking at the level of effect size bias, we observe higher bias in studies with 5 dependent variables. Moreover, notice the minor negligible effect of our QRPs on the level of bias. This is inline with our results from [Bakker et al., 2012](bakker_et_al_2012.md) where we concluded that the source of biases is the number of replications, and not the QRPs.

<!-- Results from Nov 27 Run -->
<figure>
  <picture>
    <source 
        srcset="/examples/figures/Esther_FYP/Esther_FYP_ES_Bias_Counter_Filled_dark.png" 
        media="(prefers-color-scheme: dark)">
  <img src="/examples/figures/Esther_FYP/Esther_FYP_ES_Bias_Counter_Filled_light.png" /><figcaption aria-hidden="true"><b>Figure 4.</b> Effect Size Bias</figcaption>
  </picture> 
</figure>

Figure below visualizes the accuracy of random-effect estimate's of the effect size. As we expected, the random-effect estimate improves as we increase *K*, and declines as we introduce more dependent variables.

<!-- Results from Nov 27 Run -->
<figure>
  <picture>
    <source 
        srcset="/examples/figures/Esther_FYP/Esther_FYP_RandomEffect_Bias_Counter_Filled_dark.png" 
        media="(prefers-color-scheme: dark)">
  <img src="/examples/figures/Esther_FYP/Esther_FYP_RandomEffect_Bias_Counter_Filled_light.png" /><figcaption aria-hidden="true"><b>Figure 5.</b> Random Effect Estimate's Bias</figcaption>
  </picture> 
</figure>

As shown below, power of Egger's test consistently improves as we add more publications to our pool, *K*. Moreover, as expected, we can observe the correlation of higher power with the increase of the publication bias rate. Notice the slight increase of the yellow region as we lowers *ɑ*, and add more dependent variables. Furthermore, as we discussed in [Bakker et al., 2012](bakker_et_al_2012.md), we observe a high rate of false positive in simulations with low publication bias rate.

<!-- Results from Nov 27 Run -->
<figure>
  <picture>
    <source 
        srcset="/examples/figures/Esther_FYP/Esther_FYP_Eggers_Test_Counter_Filled_dark.png" 
        media="(prefers-color-scheme: dark)">
  <img src="/examples/figures/Esther_FYP/Esther_FYP_Eggers_Test_Counter_Filled_light.png" /><figcaption aria-hidden="true"><b>Figure 6.</b> Power of Egger's Test</figcaption>
  </picture> 
</figure>

Begg's Rank Correlation Test is an another test for detecting publication bias. As stated by Begg et al.[@Begg_1994], the test has a fair power with *K > 75*, and expected to have lower power with lower *K*'s. While we only simulated pools of publications with *K = 72*, we can observe the increase in Begg's test power as we increase *K*. It is worth mentioning that Begg's test performs better than Egger's test in terms of false positives. This can be seen by comparing the size of yellow regions within lower half of each plot, as we see much smaller confidence in reporting publication bias when the true publication bias is lower.

<!-- Results from Nov 27 Run -->
<figure>
  <picture>
    <source 
        srcset="/examples/figures/Esther_FYP/Esther_FYP_RankCorrelation_Test_Counter_Filled_dark.png" 
        media="(prefers-color-scheme: dark)">
  <img src="/examples/figures/Esther_FYP/Esther_FYP_RankCorrelation_Test_Counter_Filled_light.png" /><figcaption aria-hidden="true"><b>Figure 7.</b> Power of Begg's Rank Correlation Test</figcaption>
  </picture> 
</figure>

??? info "Test Of Excess of Significant Findings [In Progress]"

    Finally, we measured the power of Test Of Excess of Significant Findings. Figure below shows the results of this measure across our parameters landscape. We are quite surprised with the test, and cannot quite make sense of it yet! Further explanation will follow!

    <!-- Results from Nov 27 Run -->
    <figure>
      <picture>
        <source 
            srcset="/examples/figures/Esther_FYP/Esther_FYP_TES_Counter_Filled_dark.png" 
            media="(prefers-color-scheme: dark)">
      <img src="/examples/figures/Esther_FYP/Esther_FYP_TES_Counter_Filled_light.png" /><figcaption aria-hidden="true"><b>Figure 8.</b> Power of Test of Excess of Significant Findings.</figcaption>
      </picture> 
    </figure>



\bibliography
