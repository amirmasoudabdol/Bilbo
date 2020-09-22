---
Title: Baker et al., 2012
layout: default
parent: Examples
---

Baker et al., 2012
====================

In this report, I will attempt to discuss the replication and reproduction of the simulation study conducted by Bakker et al, 2012. The simulation designed to recreate a common routine of applying a set of questionable research practices, and evaluate their effects on the observed effect size bias, and chance of finding significance results.

Experiment Design / Model Description
-------------------------------------

As described by Bakker, the simulation study is concerned about 4 distinct strategies as follow:

> - **Strategy 1.** Perform one large study (with N as the sample size) with sufficient power and publish it.
> 
> - **Strategy 2.** Perform one large study and use some of the QRPs most popular in psychology (John et al., 2012). These QRPs may be performed sequentially until a significant result is found:
>  - Test a second dependent variable that is correlated with the primary dependent variable (for which John et al. found a 65% admittance rate)
>  - Add 10 subjects (sequential testing; 57% admittance rate)
>  - Remove outliers (\|*Z* > 2\|) and rerun analysis (41% admittance rate)
> 
> - **Strategy 3.** Perform, at most, five small studies each with (N/5) as sample size. Players may stop data collection when they find a significant result in the expected direction and only publish the desired result (the other studies are denoted “failed”; 48% admittance rate).
> 
> - **Strategy 4.** Perform, at most, five small studies and apply the QRPs described above in each of these small studies if the need arises. Players may report only the first study that “worked.”
> 
> <p style="text-align:right">  — Bakker et al., 2012</p>

Two main distinguishing factors in the simulation are sample size, *N*, and whether the pre-defined set of QRPs are applied on the study or not. Another important key difference between *small*, and *large* studies is the repetitive nature of conducting *small* studies. Each small study is almost a replication of the main study — that might or might not go through the QRP procedure. Figure <a href="#fig:qrp_large" data-reference-type="ref" data-reference="fig:qrp_large">1</a> and <a href="#fig:qrp_small" data-reference-type="ref" data-reference="fig:qrp_small">2</a> are showcasing the simulation setup as described by Bakker. Figure 1 is equivalent of the Strategy 2 while Figure 2 showcases the strategy 4.

There are several QRPs are involved in both cases. Mainly, regarding the strategies 2, and 4,

- Every *small* or *large* study **might** go under the *Selective Reporting* process in which the researcher evaluates and reports the secondonary outcome, if she does not find the primary outcome satisfactory.

- Every *small* or *large* study **might** go under the *Optional Stopping* routine in which the researcher adds 10 new subjects to each DV, and re-calculates her statistics in a quest to find a desirable result.

- Also, every study **might** go under the *Outliers Removal* process in which the researcher attempts to remove all subjects farther than 2 standard deviation from the sample mean in a quest to find a desirable result.

- In *large* studies, a simulation will stop as soon as the researcher find a significant result with positive effect. However, in *small* studies, while the researcher reports her finding after performing the set of QRPs (”QRP Procedure” in Fig. 1), she continues to repeat the same routine for 5 times, and collect the final outcome of each replication,

    - later in the simulation, as shown in Fig 2., she will select the appropriate outcome from the pool of outcomes collected from all replications.

    - _Strategy 3 follows the same logic with the only difference that each replication doesn’t go through the QRP routine, but, the researcher will **still** review her finding after performing 5 replications._

<figure>
    <picture>
      <source 
        srcset="/figures/baker_2012/Marjan_2012_QRP_Large_Dark.png" 
        media="(prefers-color-scheme: dark)">
      <img src="/figures/baker_2012/Marjan_2012_QRP_Large.png" id="fig:qrp_large" alt="Flowchart describing Strategy 1, and 2. In the case of Strategy 1, the simulation does not enter the QRP Procedure and reports the first dependent variable." />
    </picture>
<figcaption aria-hidden="true">Flowchart describing Strategy 1, and 2. In the case of Strategy 1, the simulation does not enter the QRP Procedure and reports the first dependent variable.</figcaption>
</figure>

<figure>
<img src="/figures/baker_2012/Marjan_2012_QRP_Small.png" id="fig:qrp_small" alt="Flowchart describing Strategy 3, and 4. In the case of Strategy 3, the simulation skips the QRP Procedure but still collects the final outcome from each replication attempts." /><figcaption aria-hidden="true">Flowchart describing Strategy 3, and 4. In the case of Strategy 3, the simulation skips the QRP Procedure but still collects the final outcome from each replication attempts.</figcaption>
</figure>


SAM Configuration
-----------------


### Strategy 1, and 3 (Without QRPs)


### Strategy 2, and 4 (With QRPs)


Results
-------

The first part of the result section compares the result from the original simulation with the simulation performed by SAM. In the rest of the section, I extended the original simulation by evaluting the effect of *α* on the observed bias.

### Original vs. Reproduction

Figure <a href="#fig:original_vs_reproduced" data-reference-type="ref" data-reference="fig:original_vs_reproduced">3</a> compares the results from the original study and the results from the reproduced simulation. As it can be seen, the reproduction simulation — distinguished using points — are mainly agreeing with the original simulation with exception of some minor discrepancies in *small* studies. In all cases, the reproduction simulation captures more bias in small studies with QRPs.

<figure>
<img src="/figures/baker_2012/Marjan et al 2012 - Reproduction vs. Original - Comparison.png" id="fig:original_vs_reproduced" alt="Comparison between original and reproduced results (using SAM)." /><figcaption aria-hidden="true">Comparison between original and reproduced results (using SAM).</figcaption>
</figure>

### Extended Simulation

This section discuss the results of an extended simulation, where I explored the effect of different values of *α* ∈ {0.0005, 0.005, 0.05} on the observed ES bias. The main body of the simulation is itenditcal to the original simulation performed by Bakker.

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
