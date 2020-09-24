Introduction
============

This report discusses the reproduction process of the simulation study conducted by Bakker et al, 2014[@Bakker_2014]. The simulation aims to study the effects of removing outliers on Type I error on studies based on Graded Response Model. The original study also explores alternative tests but I will not address those in this report.

Experiment Setup
================

The original study is testing the effects of removing outliers in two different scenarios:

- **Non-Subjective Outliers Removal**, in which the effect of removing outliers with \|*Z* > *k*\|, for a fixed *k*, is being measured.

- **Subjective Outliers Removal**, in which the effect of removing outliers with a variable *k* ∈ {3, 2.5, 2} is being measured.

The data is generated based on *Graded Response Model* with:

- different number of items, *i* ∈ {2, 5, 10, 20, 40}

- different number of options per items, *j* ∈ {1, 5}

- different difficulty levels, *β* ∈ {0, 3}

- different sample sizes, *N* ∈ {20, 40, 100, 500}

- and one ability level, *α* ∈ 0

fianlly, item scores are being calculated based on the Rasch Model:

$$ Pr(X_{ij} = 1) = \frac{exp(\theta_j - \beta_i)}{1 + exp(\theta_j - \beta_i)} $$

Figure <a href="#fig:strategies_flowchart" data-reference-type="ref" data-reference="fig:strategies_flowchart">1</a> shows the flowchart of the two main simulation setups. As discussed by Bakker et al, 2012, the subjective Type I error is calcuated based on the results of the subjective simulation:

> Furthermore, we investigated the subjective use of *k*. This means that a com- parison is counted as statistically significant if the test showed a statistically significant difference when all values were included in the sample or when the test showed a statistically significant difference when *k* is 3, 2.5, or 2. This is comparable with adapting *k* until a statistically significant p-value is found. This reflects a manner in which researchers can chase for significance (Ioannidis, 2005, 2012), ...

> <p style="text-align:right">  — Bakker et al., 2012, page 5.</p>

The reproduction simulation is in fact simulating the behavior of the researcher who dynamically reducing *k* until she finds a significant result. As stated by Bakker, this should be equivalent to calculating the subjective Type I Error from the posterior of the non-subjective simulation. (While for the most configurations, the estimate is quite accurate, I am not yet convinced that both approach always lead to the same level of Type I Error.)

<figure>
<img src="/figures/baker_2014/Marjan_2014_Flowchart.png" id="fig:strategies_flowchart" alt="Simulation Design" /><figcaption aria-hidden="true">Simulation Design</figcaption>
</figure>

Results
=======

Figure <a href="#fig:subjective_vs_non_subjective_type_i_error" data-reference-type="ref" data-reference="fig:subjective_vs_non_subjective_type_i_error">2</a> shows the result of the reproduction simulation. I did not try to reproduce the entire simulation and every parameters combinations. However, the reproduction simulation agrees with the original results when parameters are crossing. The SUbjective Type I Error is larger in most cases, and between simulations with similar parameters, those with harder items affected more drastically by subjectively removing of the outliers, Figure <a href="#fig:subjective_vs_non_subjective_type_i_error" data-reference-type="ref" data-reference="fig:subjective_vs_non_subjective_type_i_error">2</a>, right columns, *β* = 3.

<figure>
<img src="/figures/baker_2014/Side-by-Side.png" id="fig:subjective_vs_non_subjective_type_i_error" alt="Non-Subjective (left panel) and Subjective (right panel) Type I Error" /><figcaption aria-hidden="true">Non-Subjective (left panel) and Subjective (right panel) Type I Error</figcaption>
</figure>

\bibliography