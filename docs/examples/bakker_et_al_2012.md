---
title: Bakker et al., 2012
---

!!! attention
    Please check out Abdol et al., 2021[@Abdol_2021] for the updated version of this project. In addition, you can find all the codes, and analysis on [GitHub](https://github.com/amirmasoudabdol/bakker-et-al-2012-reproduction-using-sam).

# The Rules of the Game Called Psychological Science[@Bakker_2012]

In this report, we will attempt to discuss the replication and reproduction of the simulation study conducted by Baker et al., 2012[@Bakker_2012]. The simulation is designed to recreate a common routine of applying a set of questionable research practices, and consequently evaluate their effects on the observed effect size bias, and chance of finding significance results.

## Experiment Design / Model Description

As described by Bakker, the simulation study is concerned about 4 distinct strategies as follow:

> **Strategy 1.** Perform one large study (with N as the sample size) with sufficient power and publish it.
> 
> **Strategy 2.** Perform one large study and use some of the QRPs most popular in psychology (John et al., 2012). These QRPs may be performed sequentially until a significant result is found:
> - Test a second dependent variable that is correlated with the primary dependent variable (for which John et al. found a 65% admittance rate)
>  - Add 10 subjects (sequential testing; 57% admittance rate)
>  - Remove outliers (|*Z*| > 2) and rerun analysis (41% admittance rate)
> 
> **Strategy 3.** Perform, at most, five small studies each with (N/5) as sample size. Players may stop data collection when they find a significant result in the expected direction and only publish the desired result (the other studies are denoted “failed”; 48% admittance rate).
> 
> **Strategy 4.** Perform, at most, five small studies and apply the QRPs described above in each of these small studies if the need arises. Players may report only the first study that “worked.”
> 
> <p style="text-align:right">  — Bakker et al., 2012</p>

Two main distinguishing factors in the simulation are sample size, *N*, and whether the pre-defined set of QRPs are applied on the study. When it comes to sample sizes, Bakker defines two size classes, small and large. Number of observations in small studies can be a value from {5, 10, 20}, and number of observation in large studies can be either of {25, 50, 100}. Basically, large studies are 5 times larger than small studies. Another difference between *small*, and *large* studies is the repetitive nature of conducting *small* studies. In strategy 3 and 4, each trial is **almost** an exact replication of the main study — that might or might not have been gone through the QRP procedure. Results from these trials will be collected and at the end, the researcher will get a chance to report the most desirable outcome.

Following flowcharts are visualizing the simulation workflow designed by Bakker. Figure <a href="#fig:qrp_large" data-reference-type="ref" data-reference="fig:qrp_large">1</a> is an equivalent of 1st and 2nd strategies while Figure <a href="#fig:qrp_small" data-reference-type="ref" data-reference="fig:qrp_small">2</a> showcases 3rd and 4th strategies. Notice the "Perform the QRP Procedure" step in Figure 2 where a study goes through the entire process described in Figure 1 labeled as "QRP Procedure".

<figure>
  <img src="/examples/figures/Bakker_2012/Marjan_2012_QRP_Large.png" id="fig:qrp_large" alt="Flowchart describing Strategy 1, and 2. In the case of Strategy 1, the simulation does not enter the QRP Procedure and reports the first dependent variable." />
  <figcaption aria-hidden="true"><b>Figure 1.</b> Flowchart describing Strategy 1, and 2. In the case of Strategy 1, the simulation does not enter the QRP Procedure and reports the first dependent variable.</figcaption>
</figure>

<figure>
  <img src="/examples/figures/Bakker_2012/Marjan_2012_QRP_Small.png" id="fig:qrp_small" alt="Flowchart describing Strategy 3, and 4. In the case of Strategy 3, the simulation skips the QRP Procedure but still collects the final outcome from each replication attempts." />
  <figcaption aria-hidden="true"><b>Figure 2.</b> Flowchart describing Strategy 3, and 4. In the case of Strategy 3, the simulation skips the QRP Procedure but still collects the final outcome from each replication attempts.</figcaption>
</figure>

There are several QRPs involved in strategies 2 and 4.

- Every *small* or *large* study **might** go under the *Selective Reporting* process in which the researcher evaluates and reports the secondary outcome, if she does not find the primary outcome satisfactory.

- Every *small* or *large* study **might** go under the *Optional Stopping* routine in which the researcher adds 10 new subjects to each DV, and re-calculates her statistics in a quest to find a desirable result.

- Every study **might** go under the *Outliers Removal* process in which the researcher attempts to remove all subjects farther than 2 standard deviation from the sample mean in a quest to find a desirable result.

- In *large* studies, a simulation will stop as soon as the researcher find a significant result with positive effect. However, in *small* studies, while the researcher reports her finding after performing the set of QRPs (”QRP Procedure” in Fig. 1), she continues to repeat the same routine 5 times, and collects the outcome of each replication,

    - Later in the simulation, as shown in Fig 2., she will select the appropriate outcome from the pool of outcomes collected from all replications.

    - → _Strategy 3 follows the same logic with the only difference that each replication doesn’t go through the QRP routines, however, the researcher will **still** review her finding after performing 5 exact replications._


Besides individual strategies, Bakker et al., explored a wide range of parameters in order to capture the influence of their design. The list of parameters can be found below:

- *μ* ∈ [0, 1]
- *N* ∈ {5, 10, 20, 25, 50, 100}
    - *Small* class, {5, 10, 20}
    - *Large* class, {25, 50, 100}
- *m*, *n* = 2
- 4 scenarios/strategies
  - 2 with QRP
  - 2 without QRP

The rest of this article focuses on simulating Bakker’s study using SAM, and consequently comparing two approach with each other. Further in the report, we will build on top of Bakker's study in order to investigate the nature of observed biases in more detail.

## SAM Configuration

In order to recreate Bakker's simulation using SAM, we start by planning [Researcher's Workflow](/research-workflow.md) and translating that into a [configuration file](/configuration-file.md).

<picture>
  <img width="300px" align="right" src="/examples/figures/Bakker_2012/Marjan_2012_Expriment_Design_Light.png" id="fig:marjan_2012_design"/>
</picture>

Bakker's experiment is a 2x2 factorial design consists of two groups, Control (C) and Treatment (T) each measuring two dependent variables, as shown in Figure below. The sample population is a multivariate normal distribution with mean of $\hat{0}$ for control group, and $\hat{\mu}$ for treatment group; and standard deviation of $1$, and $0.5$ covarinace between dependent variables. Therefore, $DV_{i} \in MN(\hat{\mu}, \Sigma)$ where $\hat{\mu} = (0, 0, \mu, \mu)$ and 


$$
\Sigma =
\begin{bmatrix}
1 & 0.5 & 0 & 0 \\
0.5 & 1 & 0 & 0 \\
0 & 0 & 1 & 0.5 \\
0 & 0 & 0.5 & 1
\end{bmatrix}
$$


This design can be expressed using a Linear Model data strategy as follow: 

??? datastrategy "Configuration: _Data Strategy_"
    ```json
    {
      ...
      "experiment_parameters": {
        "n_obs": 20,
        "n_conditions": 2,
        "n_dep_vars": 2,
        "data_strategy": {
          "name": "LinearModel",
          "measurements": {
              "dist": "mvnorm_distribution",
              "means": [0, 0, μ, μ],
              "sigma": [[1.0,   0.5,   0.0,   0.0],
                        [0.5,   1.0,   0.0,   0.0],
                        [0.0,   0.0,   1.0,   0.5],
                        [0.0,   0.0,   0.5,   1.0]]
        }
      }
      ...
    }
    ```

Bakker's Researcher uses TTest to asses the significant of its findings. This choice can be expressed with Test Strategy's setting as follow:

??? teststrategy "Configuration: _Test Strategy_"
    ```json
    {
      ...
      "experiment_parameters": {
        ...
        "test_strategy": {
          "name": "TTest",
          "alpha": 0.05,
          "alternative": "TwoSided",
          "var_equal": true
        }
      }
      ...
    }
    ```

For effect size measure, Bakker computed the standardized effect size different between two effect. In order to equip SAM with this method, we can use the following configuration of the [Effect Strategy](/effect-strategies.md):

??? experiment "Configuration: _Effect Strategy_"
    ```json
    {
      ...
      "experiment_parameters": {
        ...
        "effect_strategy": {
          "name": "StandardizedMeanDifference"
        }
      }
      ...
    }
    ```

After fully configuring Experiment's parameters, we can start translating the simulation logic from a [Research Workflow](/research-workflow.md) to Decision Strategy's configuration, and thereafter preparing the list of Hacking Strategies.

### Strategy 1, and 3 (Without QRPs)

#### Hacking Strategy

In 1st and 3rd strategies, researchers will NOT commit any QRPs, therefore the `probability_of_being_a_hacker` should be set to `0`. This is enough for configuring a researcher who does not explore the [Hacking Workflow](/hacking-workflow.md).

#### Decision Strategies

Following the workflow depicted in Figure 1, we are able to set different decision and selection policies in place for the researcher to achieve the exact path described by Bakker.

The researcher always starts by checking the primary outcome, if the selected outcome is not significant and does not have a positive effect (i.e.`"initial_selection_policies": [["id == 2"]]`), she executes the first hacking strategy. Since in 1st and 3rd strategies, we are not performing any QRPs, this path will not be taken. 

In the case of small studies, the researcher will replicate 5 exact studies. At the end of each replication, the researcher stores the first outcome variable (as indicated by `initial_selection_policies`) in a dataset of **All Reported Outcome**, Figure 2. Finally, she revisits this dataset, and chooses the most desirable outcome among them. Her preferences can be seen under `between_replications_selection_policies` parameter. This setup is in place to capture the main idea behind Bakker's simulation, that is, "beneficial to a researcher to run 5 small studies instead of one large study."

??? decisionstrategy "Configuration: _Decision Strategy_"
    ```json
    {
      ...
      "researcher_parameters": {
        ...
        "probability_of_being_a_hacker": 0,
        "decision_strategy": {
          "name": "DefaultDecisionMaker",
          "initial_selection_policies": [
            ["id == 2"]
          ],
          "will_start_hacking_decision_policies": ["effect < 0", "!sig"],
          "between_hacks_selection_policies": [
            ["effect > 0", "min(pvalue)"],
            ["effect < 0", "max(pvalue)"]
          ],
          "stashing_policy": ["all"],
          "between_replications_selection_policies": [
            ["effect > 0", "sig", "first"],
            ["effect > 0", "min(pvalue)"],
            ["effect < 0", "max(pvalue)"]
          ],
          "will_continue_replicating_decision_policy": [""],
          "submission_decision_policies": [""],
        }
      ...
      }
    }
    ```


### Strategy 2, and 4 (With QRPs)

#### Hacking Strategies

In 2nd and 4th strategies, the researcher will execute at least one of the listed strategies. After each QRP, the researcher gets to select an outcome from the altered Experiment, after her selection, she can decide on whether she is going to stop there, or applies the next hacking strategy. In Bakker’s case, the *selection → decision* is simple. The researcher selects the outcome with positive effect and minimum *p*-value; then, she checks the availability desirability of the selected outcome, if the outcome is not desirable, she executes the next QRP. These settings are highlighted in the following configuration.

??? hackingstrategy "Configuration: _Hacking Strategy_"
    ```json
    {
      "researcher_parameters": {
        "hacking_strategies": [
          [
            {
              "name": "OptionalStopping",
              "target": "Both",
              "max_attempts": 1,
              "n_attempts": 1,
              "num": 10
            },
            [
              ["effect > 0", "min(pvalue)" ]
            ],
            ["effect < 0", "!sig"]
          ],
          [
            {
              "name": "OutliersRemoval",
              "target": "Both",
              "max_attempts": 1,
              "min_observations": 1,
              "multipliers": [2],
              "n_attempts": 1,
              "num": 100,
              "order": "random"
            },
            [
              ["effect > 0", "min(pvalue)" ]
            ],
            ["effect < 0", "!sig"]
          ]
        ]
      }
    }
    ```
    
#### Decision Strategy

In Bakker’s simulation, the decision making process between strategies with and without QRPs are very similar. The main research workflow stays intact as shown in Figure 1, and 2. However, now that researchers can commit any QRPs, they will need to choose between all altered outcomes. Bakker’s players tend to collect their findings — regardless of being QRPed — throughout the simulation, and select the most desirable one at the end of their research. This process is shown in Figure 1 with dashed lines transferring results to a temporary dataset, and finally selecting for the most desirable outcome from the temporary database.

As discussed, this process can be simulated in SAM as well. The  `stashing_policy` parameter indicates which of the outcomes will be collected by the researcher during its expedition. At the end of the [Hacking Workflow](/hacking-workflow.md), the `between_hacks_selection_policies` parameter indicates how is the researcher going to select between those outcomes, ie., Hacked DB, or **All Outcomes Database** as stated in Figure 1.

??? decisionstrategy "Configuration File: _Decision Strategy_"
    ```json
    {
      ...
      "researcher_parameters": {
        ...
        "probability_of_being_a_hacker": 1,
        "decision_strategy": {
          "name": "DefaultDecisionMaker",
          "between_hacks_selection_policies": [
            ["effect > 0","min(pvalue)"],
            ["effect < 0","max(pvalue)"]
          ],
          "between_replications_selection_policies": [
            ["effect > 0", "sig", "first"],
            ["effect > 0", "min(pvalue)"],
            ["effect < 0", "max(pvalue)"]],
          "initial_selection_policies": [
            ["id == 2", "sig", "effect > 0"],
            ["id == 3", "sig", "effect > 0"]
          ],
          "stashing_policy": ["all"],
          "submission_decision_policies": [""],
          "will_continue_replicating_decision_policy": [""],
          "will_start_hacking_decision_policies": ["effect < 0", "!sig"]
        }
      ...
      }
    }
    ```

## Results

We start by comparing the results between the original simulation and the reproduced study.

### Original vs. Reproduction

Figure <a href="#fig:original_vs_reproduced" data-reference-type="ref" data-reference="fig:original_vs_reproduced">4</a> compares the results of the original study and the reproduced simulation. As it can be seen, the reproduction simulation — distinguished by points — are mainly agreeing with the original simulation with exception of some minor discrepancies in *small* studies. In all cases, the reproduction simulation captures more bias in small studies with QRPs.

<figure>
  <picture>
    <source 
        srcset="/examples/figures/Bakker_2012/Comparison_with_Original_Simulation_dark.png" 
        media="(prefers-color-scheme: dark)">
    <img src="/examples/figures/Bakker_2012/Comparison_with_Original_Simulation_light.png" id="fig:original_vs_reproduced" alt="Comparison between original and reproduced results (using SAM)." /><figcaption aria-hidden="true"><b>Figure 4. </b>Comparison between original and reproduced results (using SAM).</figcaption>
  </picture>
</figure>

#### The Source of Discrepency

Further investigation led to the finding of a minor bug in Bakker et al., code where a typo resulted in insertion of a wrong **large** study in the replication pool of  *small* simulation. This polluted the pool of small studies and reduced the overall observed bias, due to the wrongly inserted large study having lower bias among all other small studies. Figure <a href="#fig:patched_vs_reproduced" data-reference-type="ref" data-reference="fig:patched_vs_reproduced">5</a>, shows the comparison of results from the patched script, and SAM's results. As it is shown, patching Bakker's code accounted for the minor discrepancy and consequently we gets a perfect replication.

<figure>
  <picture>
    <source 
        srcset="/examples/figures/Bakker_2012/Comparison_with_Patched_Simulation_dark.png" 
        media="(prefers-color-scheme: dark)">
    <img src="/examples/figures/Bakker_2012/Comparison_with_Patched_Simulation_light.png" id="fig:patched_vs_reproduced" alt="Comparison between original and reproduced results (using SAM)." /><figcaption aria-hidden="true"><b>Figure 5. </b>Comparison between results from the patched script and results from SAM.</figcaption>
  </picture>
</figure>

## First Extension: α‘s Role

Building on top of Bakker’s simulation and using SAM’s flexibility we can extend their simulation to study the observed effect size bias, *ES Bias*, under different values of *α* ∈ {0.0005, 0.005, 0.05}.

The main body of the simulation is identical to the original simulation performed by Bakker. Therefore, we start from the final configuration file and in order to enforce different alpha levels, the only parameters that needs to be changes is `test_alpha`. 

??? teststrategy "Configuration: _Test Strategy_"
    ```json hl_lines="7"
    {
      ...
      "experiment_parameters": {
        ...
        "test_strategy": {
          "name": "TTest",
          "alpha": 0.05,
          "alternative": "TwoSided",
          "var_equal": true
        }
      }
      ...
    }
    ```
    
By running the simulation under selected range of parameters, we will be able summarize our results for different levels of alpha in Figure <a href="#fig:extended_sim_proportion_plot" data-reference-type="ref" data-reference="fig:extended_sim_proportion_plot">6</a> and <a href="#fig:extended_sim_bias_plot" data-reference-type="ref" data-reference="fig:extended_sim_bias_plot">7</a>. Here we can follow the effect of alpha on probability of finding significance and the amount of induced biased under Bakker’s rules. 

Figure <a href="#fig:extended_sim_proportion_plot" data-reference-type="ref" data-reference="fig:extended_sim_proportion_plot">6</a> shows the chance of finding at least one significant result. As expected, from left to right, the chance of finding significant result — in all cases — increases as we increase *α* but not so drastically. 

Figure <a href="#fig:extended_sim_bias_plot" data-reference-type="ref" data-reference="fig:extended_sim_bias_plot">7</a> shows the level of bias in the estimated effect. The effect of lowering the *α* on ES bias is not as obvious as it is on the chance of finding significant results. In almost all cases, the largest *α* leads to less bias in the effect as the true effect size increases. In 4th strategy, where the researcher applies a set of QRPs on *small* studies, the bias rises even more drastically as we lower *α*. It’s worth mentioning that the researcher has not adoptted his strategies to the adjusted values of *α*. In all cases, she still adds 10 new subjects and removes subjects with values further than 2 standard deviations.

<!-- Check Figure <a href="#fig:extended_sim_proportion_vs_bias" data-reference-type="ref" data-reference="fig:extended_sim_proportion_vs_bias">6</a> for more clear comparison. -->
<!-- This is shown more clearly in Figure <a href="#fig:extended_sim_proportion_vs_bias" data-reference-type="ref" data-reference="fig:extended_sim_proportion_vs_bias">6</a>. -->

<figure>
  <picture>
    <source 
        srcset="/examples/figures/Bakker_2012/First_Extension_Different_Alpha_Levels_Sig_dark.png" 
        media="(prefers-color-scheme: dark)">
  <img src="/examples/figures/Bakker_2012/First_Extension_Different_Alpha_Levels_Sig_light.png" id="fig:extended_sim_proportion_plot" alt="Chance of finding a significant result with regards to different values of \alpha." /><figcaption aria-hidden="true"><b>Figure 6. </b>Chance of finding a significant result with regards to different values of <span class="math inline"><em>α</em></span>.</figcaption>
  </picture> 
</figure>

<figure>
  <picture>
    <source 
        srcset="/examples/figures/Bakker_2012/First_Extension_Different_Alpha_Levels_ES_dark.png" 
        media="(prefers-color-scheme: dark)">
  <img src="/examples/figures/Bakker_2012/First_Extension_Different_Alpha_Levels_ES_light.png" id="fig:extended_sim_bias_plot" alt="ES Bias with regards to different values of \alpha." /><figcaption aria-hidden="true"><b>Figure 7. </b>ES Bias with regards to different values of <span class="math inline"><em>α</em></span>.</figcaption>
  </picture>
</figure>

The effect of *α* on the chance of finding a significant result and ES bias can be visualized using a heatmap as well. Figure <a href="#fig:extended_sim_heatmap_prop" data-reference-type="ref" data-reference="fig:extended_sim_heatmap_prop">7</a> and <a href="#fig:extended_sim_heatmap_bias" data-reference-type="ref" data-reference="fig:extended_sim_heatmap_bias">8</a> showcase the trends and patterns more vividly. With regards to *chance of finding a significant result*, as discussed before, we can see a clear decline as we decrease *α*. This can be seen by the movement of the dark region (lower probability) to the right side (higher effects).

While we can see a clear change in the probability of finding a significant result, the heatmap of ES bias looks very scattered and with no clear patterns or trends. This is the indication of a non-linear relation between *α* and ES bias. While decreasing alpha makes it harder to find a significant results, a weak experiment design carries its bias with it anyway.


### Effect of Replications

Before we end the first extension, we studied the effect of number of replications in Bakker et al. simulation. Figures below showcase the effect that different number of replications has on the chance of finding significant and also on the bias accumulated in effect size. While these figures might look crowded, the only thing we are trying to emphasize is the fact that more replications lead to more bias in our studies. This can be seen by tracing points' shapes in each plots. 

**In fact we believe this is the only source of bias in Bakker et al. simulation, and the effect of QRP is minimal in comparison to drastic level of bias induced by only running the same study several times.** The next extension put this hypothesis to test by replacing Bakker et al. QRPs with more aggressive methods and parameters.

=== "Chance of Finding Sig."

    <figure>
      <picture>
        <source 
            srcset="/examples/figures/Bakker_2012/First_and_Half_Extension_Different_Reps_Levels_Sig_dark.png" 
            media="(prefers-color-scheme: dark)">
      <img src="/examples/figures/Bakker_2012/First_and_Half_Extension_Different_Reps_Levels_Sig_light.png" id="fig:extended_sim_proportion_plot" alt="Chance of finding a significant result with regards to different number of replications." /><figcaption aria-hidden="true">Chance of finding a significant result with regards to different number of replications.</figcaption>
      </picture> 
    </figure>


=== "ES Bias"

    <figure>
      <picture>
        <source 
            srcset="/examples/figures/Bakker_2012/First_and_Half_Extension_Different_Reps_Levels_ES_dark.png" 
            media="(prefers-color-scheme: dark)">
      <img src="/examples/figures/Bakker_2012/First_and_Half_Extension_Different_Reps_Levels_ES_light.png" id="fig:extended_sim_bias_plot" alt="ES Bias with regards to different number of replications." /><figcaption aria-hidden="true">ES Bias with regards to different number of replications.</figcaption>
      </picture>
    </figure>


## Second Extension: More Aggressive QRPs

Another extension of this model could investigate the effect of more aggressive QRPs when stricter *α*’s are introduced. For instance, we could adjust Optional Stopping such that the researcher adds new subjects one by one until she finds a significance result. Furthermore, the Outliers Removal procedure can be replaced by a Subjective Outliers Removal method where the researcher continuously lowers *k* and remove corresponding outliers until she finds a significant results. These two changes can be added to the configuration file as following: 

??? hackingstrategy "Hacking Strategy: _Advance Hacker_"
    ```json linenums="1" hl_lines="13 29"
    {
      ...
      "hacking_strategies": [
        [
          {
            "name": "OptionalStopping",
            "target": "Both",
            "prevalence": 0.1,
            "defensibility": 0.1,
            "max_attempts": 1,
            "n_attempts": 10,
            "num": 1,
            "stopping_condition": ["sig"]
          },
          [
            ["effect > 0", "min(pvalue)" ]
          ],
          ["effect < 0", "!sig"]
        ],
        [
          {
            "name": "SubjectiveOutlierRemoval",
            "min_observations": 5,
            "range": [2, 4],
            "step_size": 0.5,
            "target": "Both",
            "prevalence": 0.1,
            "defensibility": 0.1,
            "stopping_condition": ["sig"]
          },
          [
            ["effect > 0", "min(pvalue)" ]
          ],
          ["effect < 0", "!sig"]
        ]
      ]
    ...
    }
    ```
    
Figures below show the results of these modifications. As it is shown, while these adjustments introduce slightly more bias into publications; their effect is not as drastic as one would assume. Combining there results with results of previous extension, we are more certain that the effect of QRPs is minimal. 

> This in fact strengthen Bakker et al. hypothesis by showcasing the immense effect and advantage of running small studies over larger studies. Studies with low sample size are volatile enough that a researcher could easily achieve significant results with unrealistic effect sizes throughout the realistic effect size spectrum.

<figure>
  <picture>
    <source 
        srcset="/examples/figures/Bakker_2012/Second_Extension_Different_Alpha_Levels_Sig_dark.png" 
        media="(prefers-color-scheme: dark)">
  <img src="/examples/figures/Bakker_2012/Second_Extension_Different_Alpha_Levels_Sig_light.png" id="fig:extended_sim_proportion_plot" alt="Chance of finding a significant result with regards to different values of \alpha." /><figcaption aria-hidden="true">Chance of finding a significant result with regards to different values of <span class="math inline"><em>α</em></span>.</figcaption>
  </picture> 
</figure>

<figure>
  <picture>
    <source 
        srcset="/examples/figures/Bakker_2012/Second_Extension_Different_Alpha_Levels_ES_dark.png" 
        media="(prefers-color-scheme: dark)">
  <img src="/examples/figures/Bakker_2012/Second_Extension_Different_Alpha_Levels_ES_light.png" id="fig:extended_sim_bias_plot" alt="ES Bias with regards to different values of \alpha." /><figcaption aria-hidden="true">ES Bias with regards to different values of <span class="math inline"><em>α</em></span>.</figcaption>
  </picture>
</figure>
 

## Third Extension: Influence of Publication Bias

In our last extension, we will explore the effect of publication bias on the level of effect size bias; moreover, we investigated the power of Egger's[@Egger_1997] test under different publication bias levels.

In order to incorporate the effect of publication bias to our simulation, we equip the Journal module with a [Selection Strategies](/journal.md#selection-strategies) that mimics this effect. The [Significant Selection](/selection-strategies.md#significant-selection) allows us to set adjust the publication bias of the Journal, `pub_bias` and induce different level of publication bias into our simulation. For this study, we use different values of publication bias, *{0., 0.1, ..., 0.9, 1.0}*.

??? journal "Journal: _Publication Bias_"
    ```json linenums="1" hl_lines="5-10"
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
            }
        ]
      }
      ...
    }
    ```

In this setup, we would like to run our meta analysis methods publication pool size of *K = 24*. This can be done by setting  `max_pubs` parameters of `journal_parameters`. With this configuration, after journal max-ed out its publications list, it calculates `RandomEffectEstimator` and `EggersTestEstimator`, and writes the results into different files for further analysis. 

Starting by our general plots, we can observer the effect of publication bias on proportion of significant results in our publications pool.

=== "0.0"

    <picture>
      <source 
          srcset="/examples/figures/Bakker_2012/Third_Extension_Sig_Mean_vs_Pub_Bias_dark_0001.png" 
          media="(prefers-color-scheme: dark)">
      <img src="/examples/figures/Bakker_2012/Third_Extension_Sig_Mean_vs_Pub_Bias_light_0001.png"/>
    </picture> 

=== "0.1"
    
    <picture>
      <source 
          srcset="/examples/figures/Bakker_2012/Third_Extension_Sig_Mean_vs_Pub_Bias_dark_0001.png" 
          media="(prefers-color-scheme: dark)">
      <img src="/examples/figures/Bakker_2012/Third_Extension_Sig_Mean_vs_Pub_Bias_light_0001.png"/>
    </picture> 

=== "0.2"
    
    <picture>
      <source 
          srcset="/examples/figures/Bakker_2012/Third_Extension_Sig_Mean_vs_Pub_Bias_dark_0002.png" 
          media="(prefers-color-scheme: dark)">
      <img src="/examples/figures/Bakker_2012/Third_Extension_Sig_Mean_vs_Pub_Bias_light_0002.png"/>
    </picture> 

=== "0.3"
    
    <picture>
      <source 
          srcset="/examples/figures/Bakker_2012/Third_Extension_Sig_Mean_vs_Pub_Bias_dark_0003.png" 
          media="(prefers-color-scheme: dark)">
      <img src="/examples/figures/Bakker_2012/Third_Extension_Sig_Mean_vs_Pub_Bias_light_0003.png"/>
    </picture> 

=== "0.4"
    
    <picture>
      <source 
          srcset="/examples/figures/Bakker_2012/Third_Extension_Sig_Mean_vs_Pub_Bias_dark_0004.png" 
          media="(prefers-color-scheme: dark)">
      <img src="/examples/figures/Bakker_2012/Third_Extension_Sig_Mean_vs_Pub_Bias_light_0004.png"/>
    </picture> 

=== "0.5"
    
    <picture>
      <source 
          srcset="/examples/figures/Bakker_2012/Third_Extension_Sig_Mean_vs_Pub_Bias_dark_0005.png" 
          media="(prefers-color-scheme: dark)">
      <img src="/examples/figures/Bakker_2012/Third_Extension_Sig_Mean_vs_Pub_Bias_light_0005.png"/>
    </picture> 

=== "0.6"
    
    <picture>
      <source 
          srcset="/examples/figures/Bakker_2012/Third_Extension_Sig_Mean_vs_Pub_Bias_dark_0006.png" 
          media="(prefers-color-scheme: dark)">
     <img src="/examples/figures/Bakker_2012/Third_Extension_Sig_Mean_vs_Pub_Bias_light_0006.png"/>
    </picture> 

=== "0.7"
    
    <picture>
      <source 
          srcset="/examples/figures/Bakker_2012/Third_Extension_Sig_Mean_vs_Pub_Bias_dark_0007.png" 
          media="(prefers-color-scheme: dark)">
      <img src="/examples/figures/Bakker_2012/Third_Extension_Sig_Mean_vs_Pub_Bias_light_0007.png"/>
    </picture> 

=== "0.8"
    
    <picture>
      <source 
          srcset="/examples/figures/Bakker_2012/Third_Extension_Sig_Mean_vs_Pub_Bias_dark_0008.png" 
          media="(prefers-color-scheme: dark)">
      <img src="/examples/figures/Bakker_2012/Third_Extension_Sig_Mean_vs_Pub_Bias_light_0008.png"/>
    </picture> 

=== "0.9"
    
    <picture>
      <source 
          srcset="/examples/figures/Bakker_2012/Third_Extension_Sig_Mean_vs_Pub_Bias_dark_0009.png" 
          media="(prefers-color-scheme: dark)">
     <img src="/examples/figures/Bakker_2012/Third_Extension_Sig_Mean_vs_Pub_Bias_light_0009.png"/>
    </picture> 

=== "1.0"
    
    <picture>
      <source 
          srcset="/examples/figures/Bakker_2012/Third_Extension_Sig_Mean_vs_Pub_Bias_dark_0010.png" 
          media="(prefers-color-scheme: dark)">
      <img src="/examples/figures/Bakker_2012/Third_Extension_Sig_Mean_vs_Pub_Bias_light_0010.png"/>
    </picture> 


Moreover, the level of bias can be seen below. As expected, raising the publicatoin bias raises the level of bias accross all our configurations, with sharper swell in lower true effect sizes.

=== "0.0"

    <picture>
      <source 
          srcset="/examples/figures/Bakker_2012/Third_Extension_ES_Bias_vs_Pub_Bias_dark_0001.png" 
          media="(prefers-color-scheme: dark)">
     <img src="/examples/figures/Bakker_2012/Third_Extension_ES_Bias_vs_Pub_Bias_light_0001.png"/>
    </picture> 

=== "0.1"
    
    <picture>
      <source 
          srcset="/examples/figures/Bakker_2012/Third_Extension_ES_Bias_vs_Pub_Bias_dark_0001.png" 
          media="(prefers-color-scheme: dark)">
      <img src="/examples/figures/Bakker_2012/Third_Extension_ES_Bias_vs_Pub_Bias_light_0001.png"/>
    </picture> 

=== "0.2"
    
    <picture>
      <source 
          srcset="/examples/figures/Bakker_2012/Third_Extension_ES_Bias_vs_Pub_Bias_dark_0002.png" 
          media="(prefers-color-scheme: dark)">
      <img src="/examples/figures/Bakker_2012/Third_Extension_ES_Bias_vs_Pub_Bias_light_0002.png"/>
    </picture> 

=== "0.3"
    
    <picture>
      <source 
          srcset="/examples/figures/Bakker_2012/Third_Extension_ES_Bias_vs_Pub_Bias_dark_0003.png" 
          media="(prefers-color-scheme: dark)">
      <img src="/examples/figures/Bakker_2012/Third_Extension_ES_Bias_vs_Pub_Bias_light_0003.png"/>
    </picture> 

=== "0.4"
    
    <picture>
      <source 
          srcset="/examples/figures/Bakker_2012/Third_Extension_ES_Bias_vs_Pub_Bias_dark_0004.png" 
          media="(prefers-color-scheme: dark)">
      <img src="/examples/figures/Bakker_2012/Third_Extension_ES_Bias_vs_Pub_Bias_light_0004.png"/>
    </picture> 

=== "0.5"
    
    <picture>
      <source 
          srcset="/examples/figures/Bakker_2012/Third_Extension_ES_Bias_vs_Pub_Bias_dark_0005.png" 
          media="(prefers-color-scheme: dark)">
      <img src="/examples/figures/Bakker_2012/Third_Extension_ES_Bias_vs_Pub_Bias_light_0005.png"/>
    </picture> 

=== "0.6"
    
    <picture>
      <source 
          srcset="/examples/figures/Bakker_2012/Third_Extension_ES_Bias_vs_Pub_Bias_dark_0006.png" 
          media="(prefers-color-scheme: dark)">
      <img src="/examples/figures/Bakker_2012/Third_Extension_ES_Bias_vs_Pub_Bias_light_0006.png"/>
    </picture> 

=== "0.7"
    
    <picture>
      <source 
          srcset="/examples/figures/Bakker_2012/Third_Extension_ES_Bias_vs_Pub_Bias_dark_0007.png" 
          media="(prefers-color-scheme: dark)">
      <img src="/examples/figures/Bakker_2012/Third_Extension_ES_Bias_vs_Pub_Bias_light_0007.png"/>
    </picture> 

=== "0.8"
    
    <picture>
      <source 
          srcset="/examples/figures/Bakker_2012/Third_Extension_ES_Bias_vs_Pub_Bias_dark_0008.png" 
          media="(prefers-color-scheme: dark)">
      <img src="/examples/figures/Bakker_2012/Third_Extension_ES_Bias_vs_Pub_Bias_light_0008.png"/>
    </picture> 

=== "0.9"
    
    <picture>
      <source 
          srcset="/examples/figures/Bakker_2012/Third_Extension_ES_Bias_vs_Pub_Bias_dark_0009.png" 
          media="(prefers-color-scheme: dark)">
      <img src="/examples/figures/Bakker_2012/Third_Extension_ES_Bias_vs_Pub_Bias_light_0009.png"/>
    </picture> 

=== "1.0"
    
    <picture>
      <source 
          srcset="/examples/figures/Bakker_2012/Third_Extension_ES_Bias_vs_Pub_Bias_dark_0010.png" 
          media="(prefers-color-scheme: dark)">
      <img src="/examples/figures/Bakker_2012/Third_Extension_ES_Bias_vs_Pub_Bias_light_0010.png"/>
    </picture>

Figures below showcase the power of Egger's test in detecting publication bias. The average performance of the test is accepetable within most parameter configurations. However, we see large regions of false positives where Egger's test overestimate the presence of the publication bias, especially within smaller true effect sizes. It is also worth mentioning that Egger's test performs quite poorly within a pool of studies with larger sample sizes, *L; N = 40*, even with publication bias as high as %90.

=== "0.0"

    <picture>
      <source 
          srcset="/examples/figures/Bakker_2012/Third_Extension_Eggers_Test_Pub_Bias_dark_0001.png" 
          media="(prefers-color-scheme: dark)">
      <img src="/examples/figures/Bakker_2012/Third_Extension_Eggers_Test_Pub_Bias_light_0001.png"/>
    </picture> 

=== "0.1"
    
    <picture>
      <source 
          srcset="/examples/figures/Bakker_2012/Third_Extension_Eggers_Test_Pub_Bias_dark_0001.png" 
          media="(prefers-color-scheme: dark)">
      <img src="/examples/figures/Bakker_2012/Third_Extension_Eggers_Test_Pub_Bias_light_0001.png"/>
    </picture> 

=== "0.2"
    
    <picture>
      <source 
          srcset="/examples/figures/Bakker_2012/Third_Extension_Eggers_Test_Pub_Bias_dark_0002.png" 
          media="(prefers-color-scheme: dark)">
      <img src="/examples/figures/Bakker_2012/Third_Extension_Eggers_Test_Pub_Bias_light_0002.png"/>
    </picture> 

=== "0.3"
    
    <picture>
      <source 
          srcset="/examples/figures/Bakker_2012/Third_Extension_Eggers_Test_Pub_Bias_dark_0003.png" 
          media="(prefers-color-scheme: dark)">
      <img src="/examples/figures/Bakker_2012/Third_Extension_Eggers_Test_Pub_Bias_light_0003.png"/>
    </picture> 

=== "0.4"
    
    <picture>
      <source 
          srcset="/examples/figures/Bakker_2012/Third_Extension_Eggers_Test_Pub_Bias_dark_0004.png" 
          media="(prefers-color-scheme: dark)">
      <img src="/examples/figures/Bakker_2012/Third_Extension_Eggers_Test_Pub_Bias_light_0004.png"/>
    </picture> 

=== "0.5"
    
    <picture>
      <source 
          srcset="/examples/figures/Bakker_2012/Third_Extension_Eggers_Test_Pub_Bias_dark_0005.png" 
          media="(prefers-color-scheme: dark)">
      <img src="/examples/figures/Bakker_2012/Third_Extension_Eggers_Test_Pub_Bias_light_0005.png"/>
    </picture> 

=== "0.6"
    
    <picture>
      <source 
          srcset="/examples/figures/Bakker_2012/Third_Extension_Eggers_Test_Pub_Bias_dark_0006.png" 
          media="(prefers-color-scheme: dark)">
      <img src="/examples/figures/Bakker_2012/Third_Extension_Eggers_Test_Pub_Bias_light_0006.png"/>
    </picture> 

=== "0.7"
    
    <picture>
      <source 
          srcset="/examples/figures/Bakker_2012/Third_Extension_Eggers_Test_Pub_Bias_dark_0007.png" 
          media="(prefers-color-scheme: dark)">
      <img src="/examples/figures/Bakker_2012/Third_Extension_Eggers_Test_Pub_Bias_light_0007.png"/>
    </picture> 

=== "0.8"
    
    <picture>
      <source 
          srcset="/examples/figures/Bakker_2012/Third_Extension_Eggers_Test_Pub_Bias_dark_0008.png" 
          media="(prefers-color-scheme: dark)">
      <img src="/examples/figures/Bakker_2012/Third_Extension_Eggers_Test_Pub_Bias_light_0008.png"/>
    </picture> 

=== "0.9"
    
    <picture>
      <source 
          srcset="/examples/figures/Bakker_2012/Third_Extension_Eggers_Test_Pub_Bias_dark_0009.png" 
          media="(prefers-color-scheme: dark)">
      <img src="/examples/figures/Bakker_2012/Third_Extension_Eggers_Test_Pub_Bias_light_0009.png"/>
    </picture> 

=== "1.0"
    
    <picture>
      <source 
          srcset="/examples/figures/Bakker_2012/Third_Extension_Eggers_Test_Pub_Bias_dark_0010.png" 
          media="(prefers-color-scheme: dark)">
      <img src="/examples/figures/Bakker_2012/Third_Extension_Eggers_Test_Pub_Bias_light_0010.png"/>
    </picture>



## Conclusion

In this example, we discussed the process of translating an existing project into SAM. We started by replicating the original simulation, fine-tunning our configuration and comparing our results. Consequently, after successfully replicating the original results, we built on top Bakker et al., simulation.

In our first extension, we showed that while lowering the alpha decreases the chance of finding significant results it does not necessarily help with the reduction of bias. Moreover, we showed that the number of replications directly influence the level of bias.

In the second extension, we showed that more aggressive QRPs do not proportionally contribute to higher effect size biases. Together with our results from first extension, we believe that the main source of bias in Bakker et al., is the number of replications and the role of QRPs are almost negligible.

In our third and last extension, we investigated the effect of publication bias on the overall bias and the power of Egger’s test in defecting publication bias. We showed that while Egger's test generally provide a good measure of publication bias in the presence of publication bias, it consistently overestimate the level of bias when there is not publication bias is present.





\bibliography
