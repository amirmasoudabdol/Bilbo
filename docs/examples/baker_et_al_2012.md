# Baker et al., 2012

In this report, we will attempt to discuss the replication and reproduction of the simulation study conducted by Baker et al., 2012[@Bakker_2012]. The simulation is designed to recreate a common routine of applying a set of questionable research practices, and consequently evaluate their effects on the observed effect size bias, and chance of finding significance results.

## Experiment Design / Model Description

As described by Bakker, the simulation study is concerned about 4 distinct strategies as follow:

> **Strategy 1.** Perform one large study (with N as the sample size) with sufficient power and publish it.
> 
> **Strategy 2.** Perform one large study and use some of the QRPs most popular in psychology (John et al., 2012). These QRPs may be performed sequentially until a significant result is found:
> - Test a second dependent variable that is correlated with the primary dependent variable (for which John et al. found a 65% admittance rate)
>  - Add 10 subjects (sequential testing; 57% admittance rate)
>  - Remove outliers (\|*Z* > 2\|) and rerun analysis (41% admittance rate)
> 
> **Strategy 3.** Perform, at most, five small studies each with (N/5) as sample size. Players may stop data collection when they find a significant result in the expected direction and only publish the desired result (the other studies are denoted “failed”; 48% admittance rate).
> 
> **Strategy 4.** Perform, at most, five small studies and apply the QRPs described above in each of these small studies if the need arises. Players may report only the first study that “worked.”
> 
> <p style="text-align:right">  — Bakker et al., 2012</p>

Two main distinguishing factors in the simulation are sample size, *N*, and whether the pre-defined set of QRPs are applied on the study or not. When it comes to sample sizes, Bakker defines two size class, small and large. Number of observations in small studies can be a value from $\{5, 10, 20\}$, and number of observation in large studies can be either of $\{25, 50, 100\}$. In fact, large studies are 5 times larger than small studies.

Another difference between *small*, and *large* studies is the repetitive nature of conducting *small* studies. In strategy 3 and 4, each trial is **almost** an exact replication of the main study — that might or might not have been gone through the QRP procedure. Results from these trials will be collected and at the end, the researcher will get a chance to report the most desirable outcome.

Figure <a href="#fig:qrp_large" data-reference-type="ref" data-reference="fig:qrp_large">1</a> and <a href="#fig:qrp_small" data-reference-type="ref" data-reference="fig:qrp_small">2</a> are showcasing the simulation setup as described by Bakker. Figure 1 is equivalent of Strategies 1 and 2 while Figure 2 showcases Strategies 3 and 4.

<figure>
	<picture>
	  <source 
    srcset="/figures/baker_2012/Marjan_2012_QRP_Large_Dark.png" 
        media="(prefers-color-scheme: dark)">
	  <img src="/figures/baker_2012/Marjan_2012_QRP_Large.png" id="fig:qrp_large" alt="Flowchart describing Strategy 1, and 2. In the case of Strategy 1, the simulation does not enter the QRP Procedure and reports the first dependent variable." />
	</picture>
	<figcaption aria-hidden="true"><b>Figure 1.</b> Flowchart describing Strategy 1, and 2. In the case of Strategy 1, the simulation does not enter the QRP Procedure and reports the first dependent variable.</figcaption>
</figure>

<figure>
	<img src="/figures/baker_2012/Marjan_2012_QRP_Small.png" id="fig:qrp_small" alt="Flowchart describing Strategy 3, and 4. In the case of Strategy 3, the simulation skips the QRP Procedure but still collects the final outcome from each replication attempts." />
	<figcaption aria-hidden="true"><b>Figure 2.</b> Flowchart describing Strategy 3, and 4. In the case of Strategy 3, the simulation skips the QRP Procedure but still collects the final outcome from each replication attempts.</figcaption>
</figure>

There are several QRPs involved in strategies 2 and 4.

- Every *small* or *large* study **might** go under the *Selective Reporting* process in which the researcher evaluates and reports the secondary outcome, if she does not find the primary outcome satisfactory.

- Every *small* or *large* study **might** go under the *Optional Stopping* routine in which the researcher adds 10 new subjects to each DV, and re-calculates her statistics in a quest to find a desirable result.

- Every study **might** go under the *Outliers Removal* process in which the researcher attempts to remove all subjects farther than 2 standard deviation from the sample mean in a quest to find a desirable result.

- In *large* studies, a simulation will stop as soon as the researcher find a significant result with positive effect. However, in *small* studies, while the researcher reports her finding after performing the set of QRPs (”QRP Procedure” in Fig. 1), she continues to repeat the same routine 5 times, and collects the outcome of each replication,

    - later in the simulation, as shown in Fig 2., she will select the appropriate outcome from the pool of outcomes collected from all replications.

    - _Strategy 3 follows the same logic with the only difference that each replication doesn’t go through the QRP routine, however, the researcher will **still** review her finding after performing 5 exact replications._

The rest of this article focuses on simulating Bakker’s study using SAM, and consequently comparing two approach with each other.

## SAM Configuration

In order to recreate Bakker's simulation using SAM, we start by planning [Researcher's Workflow](research-workflow.md) and translating that into a [configuration file](configuration-file.md).

<picture>
	<img width="300px" align="right" src="/examples/Bakker_2012/Marjan_2012_Expriment_Design_Light.png" id="fig:marjan_2012_design"/>
<picture>


Bakker's experiment is a 2x2 factorial design consists of two groups, Control (C) and Treatment (T) each measuring two dependent variables, as shown in Figure x. The sample population is a multivariate normal distribution with mean of $\hat{0}$ and $\hat{\mu}$, respectively, and standard deviation of $1$, and $0.5$ covarinace between dependent variables. Therefore, $\hat{DV} \in MN(\hat{\mu}, \Sigma)$ where $\hat{\mu} = (0, 0, \mu, \mu)$ and 


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

??? example "Configuration: _Data Strategy_"
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

Bakker's Researcher uses TTest to asses the significant of its findings. This choice can be expressed in the Test Strategy setting as follow:


??? example "Configuration: _Test Strategy_"
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

After setting Experiment parameters, we can start implementing Decision Strategy and Hacking Strategies.

### Strategy 1, and 3 (Without QRPs)

#### Hacking Strategy

In these strategies, researchers will not commit any QRPs, therefore the `probability_of_being_a_hacker` should be set to `0`. 

#### Decision Strategies

Following the workflow depicted in Figure 1, we will able to set different decision and selection policies in place for the researcher to achieve the exact path described by Bakker.

The researcher always starts by checking the primary outcome, if the selected outcome is not significant and doesn’t have a positive effect (i.e.`"initial_selection_policies": [["id == 2"]]`), she continues with the first hacking strategy. Since in strategies 1 and 3, we are not performing any QRPs, this path will not be taken. In the case of small studies, the researcher will replicate 5 exact studies, and consequently choose the most desirable outcome among them. Her preferences can be seen under `between_replications_selection_policies` parameter.

??? example "Configuration: _Decision Strategy_"
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

> Mention the difference between `will_continue_replicating_decision_policy` in small and large studies.


### Strategy 2, and 4 (With QRPs)

#### Hacking Strategies

In Strategy 2 and 4, researcher will execute at least one of the listed strategies. After each QRP, the researcher gets to select an outcome from the altered Experiment, after her selection, she can decide on whether she is going to stop there, or applies the next hacking strategy. In Bakker’s case, the *selection → decision* is simple. The researcher selects the outcome with positive effect and minimum *p*-value; then, she checks the desirability of the selected outcome, if the outcome is not desirable, she will execute the next QRP. These settings are highlighted in the following configuration.

??? example "Configuration: _Hacking Strategy_"
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

In Bakker’s simulation, the decision making process between strategies with and without QRPs are very similar. The main research workflow stays intact as shown in Figure 1, and 2. However, now that researchers can commit any QRPs, they will need to choose between all altered outcomes. Bakker’s players tend to collect their findings — regardless of being QRPed or not — throughout the simulation, and select the most desirable one at the end of their research. This process is shown in Figure 1 with dashed lines transferring results to a temporary dataset, and finally reaching for the most desirable one inside it.

As discussed, this process can be simulated in SAM as well. The  `stashing_policy` parameter indicates which of the outcomes will be collected by the researcher during its expedition. The `between_hacks_selection_policies` parameter indicates how is she going to select between those ..........

??? example "Configuration File: _Decision Strategy_"
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

# Results

The first part of the result section compares the result from the original simulation with the simulation performed by SAM. In the rest of the section, I extended the original simulation by evaluting the effect of *α* on the observed bias.

### Original vs. Reproduction

Figure <a href="#fig:original_vs_reproduced" data-reference-type="ref" data-reference="fig:original_vs_reproduced">3</a> compares the results from the original study and the results from the reproduced simulation. As it can be seen, the reproduction simulation — distinguished using points — are mainly agreeing with the original simulation with exception of some minor discrepancies in *small* studies. In all cases, the reproduction simulation captures more bias in small studies with QRPs.

<figure>
<img src="/figures/baker_2012/Marjan et al 2012 - Reproduction vs. Original - Comparison.png" id="fig:original_vs_reproduced" alt="Comparison between original and reproduced results (using SAM)." /><figcaption aria-hidden="true">Comparison between original and reproduced results (using SAM).</figcaption>
</figure>

### Extended Simulation

This section discuss the results of an extended simulation, where I explored the effect of different values of *α* ∈ {0.0005, 0.005, 0.05} on the observed ES bias. The main body of the simulation is itenditcal to the original simulation performed by Bakker.

Figure <a href="#fig:extended_sim_proportion_plot" data-reference-type="ref" data-reference="fig:extended_sim_proportion_plot">4</a> shows the chance of finding at least one significant result. As expected, from left to right, the chane of finding significant result — in all cases — increases as we increase the *α* but not so drastically. Check Figure <a href="#fig:extended_sim_proportion_vs_bias" data-reference-type="ref" data-reference="fig:extended_sim_proportion_vs_bias">6</a> for more clear comparison.

Figure <a href="#fig:extended_sim_bias_plot" data-reference-type="ref" data-reference="fig:extended_sim_bias_plot">5</a> shows the level of bias in the estimated effect. The effect of lowering the *α* on ES bias is not as obvious as it is on the chance of finding significant results. In almost all cases, the largest *α* leads to less bias in the effect as the true effect size increases. In strategy 4, where the researcher commits a set of QRPs on *small* studies, the bias rises even more drastically as we increase *α*. This is shown more clearly in Figure <a href="#fig:extended_sim_proportion_vs_bias" data-reference-type="ref" data-reference="fig:extended_sim_proportion_vs_bias">6</a>.

It’s worth mentioning that the researcher has not adoptted his strategies to the adjusted values of *α*. In all cases, she still adds 10 new subjects and removes subjects with values further than 2 standard deviations. Another extension to this model could investigate the effect of more aggressive QRPs when stricter *α*’s are introduced.

<figure>
<img src="/figures/baker_2012/Marjan et al 2012 - QRP - noQRP - Extended - Proportion Plot.png" id="fig:extended_sim_proportion_plot" alt="Chance of finding a significant result with regards to different values of \alpha." /><figcaption aria-hidden="true">Chance of finding a significant result with regards to different values of <span class="math inline"><em>α</em></span>.</figcaption>
</figure>

<figure>
<img src="/figures/baker_2012/Marjan et al 2012 - QRP - noQRP - Extended - ES Bias.png" id="fig:extended_sim_bias_plot" alt="ES Bias with regards to different values of \alpha." /><figcaption aria-hidden="true">ES Bias with regards to different values of <span class="math inline"><em>α</em></span>.</figcaption>
</figure>

<figure>
<img src="/figures/baker_2012/Marjan et al 2012 - Extended - Proportion vs Bias.png" id="fig:extended_sim_proportion_vs_bias" alt="Chance of finding a significant results, and level of ES bias with regards to different values of \alpha." /><figcaption aria-hidden="true">Chance of finding a significant results, and level of ES bias with regards to different values of <span class="math inline"><em>α</em></span>.</figcaption>
</figure>

The effect of *α* on the chance of finding a significant result and ES bias can be visualized using a heatmap as well. Figure <a href="#fig:extended_sim_heatmap_prop" data-reference-type="ref" data-reference="fig:extended_sim_heatmap_prop">7</a> and <a href="#fig:extended_sim_heatmap_bias" data-reference-type="ref" data-reference="fig:extended_sim_heatmap_bias">8</a> showcase the trends and oatterns more vividly. With regards to *chance of finding a significant result*, as discussed before, we can see a clear decline as we decrease *α*. This can be seen by the movement of the dark region (lower probablitiy) to the right side (higher effects).

While we can see a clear change in the probility of finding a significant result, the heatmap of ES bias looks very scattered and with no clear patterns or trends. This is the indication of a non-linear relation between *α* and ES bias. While decreasing alpha makes it harder to find a significant results, a weak experiment design carries its bias with it anyway.

<figure>
<img src="/figures/baker_2012/Marjan et al 2012 - QRP - noQRP - Extended - Proportion Plot - Heatmap.png" id="fig:extended_sim_heatmap_prop" alt="Heatmap of the chance of finding significant result" /><figcaption aria-hidden="true">Heatmap of the chance of finding significant result</figcaption>
</figure>

<figure>
<img src="/figures/baker_2012/Marjan et al 2012 - QRP - noQRP - Extended - ES Bias - Heatmap.png" id="fig:extended_sim_heatmap_bias" alt="Heatmap of the ES Bias" /><figcaption aria-hidden="true">Heatmap of the ES Bias</figcaption>
</figure>


\bibliography
