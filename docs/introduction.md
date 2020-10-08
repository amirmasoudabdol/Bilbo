---
title: Introduction
layout: default
nav_order: 2
---

# Introduction

Before we discuss SAM's implementation and design, let's review the common process of defining, conducting and reporting a scientific research. In the coming section, we will walk through a *simplified* **process of producing a scientific result**. This will help us expose typical components and entities of involved in different stages of conducting a research. Later, in the [Design](design.md) section, we will explain how each component is going to be represented in SAM.

## The Scientific Research Process

The *process* of producing a scientific research/study is often a cumbersome and complicated process. Despite all different ways of conducting a research, a typical scientific study starts by *formulating a hypothesis* when the [Researcher](design.md#researcher) jots down her ideas about how a certain process explains a certain phenomenon or how she thinks a complicated system works. To test this hypothesis, she *prepares an experiment* in order to define the underlying parameters, and boundaries of her theory.

After the [Experiment Setup](design.md#experiment-setup) is finalized, an [Experiment](design.md#experiment) is being conducted in which the researcher aims to collect certain types — and amount — of data in order to test her hypothesis, e.g., censors data, images, etc. The next step is a mixture of (pre-)processing and analysis of the data, and consequently coming up with a conclusion evaluating the initial hypothesis. If results are informative — regardless of agreeing or disagreeing with the *initial hypothesis* (i.e., *pre-registered hypothesis*) — the researcher selects a [Journal](design.md#journal) and submits her findings in the form of a [Manuscript](design.md#submission), in order for it to be reviewed according to journal's criteria. And finally, the Journal will decide whether the submitted manuscript worth publishing or not.

![<b>Figure 1.</b> The Simplified Process of Producing a Scientific Publication](/figures/Research_Process.png)

## Meta-analysis

As it has been shown and discussed \[cite, cite\], the aforementioned process is often long and prune to errors in every different stage. Natural complexity of conducting a research alongside large number of degree of freedoms available to researchers and journals will undoubtedly affect the quality of research and publications. Researchers — intentionally or unintentionally — may make mistakes, and journals may select a particular set of publications based on wrong or outdated criteria. As a result, various biases will be accumulated into the publications pool and ultimately affects our understanding of a certain topic \[cite, cite, cite\].

Studying the complicated interaction between a *Researcher*, his/her *Research*, the *Journal* (i.e. publishing medium), and finally the outcome (i.e., *Knowledge*), is proven to be a challenging task[@Bakker_2012][@Bakker_2014] \[Marjan, Robbie, Jelte, cite, cite, cite\]. The list of degrees of freedoms is long[@John_2012aa][@Agnoli_2017] \[cite\], and researchers are not fully aware of the consequences of certain procedures on the final outcome of their research. At the same time, the scientific community also do not fully understands (or agrees on) the propagative impacts of these practices on our collective knowledge \[cite, papers supporting some of the qrps\], a.k.a, *true effect size*.

In recent years, field of meta-analysis has grown in popularity to evaluate and *account* for various biases presented in publications. As a result, we have discovered the effect of researchers' degrees of freedom on published results \[cite\] and unwanted outcome of journals\' tendency to only publish positive and novel results \[cite\]. For instance, it has been shown that the process of adding new data points to an experiment — after the initial data collection — is a widespread practice[@John_2012aa][@Agnoli_2017] and it has a severe effect on researchers' ability to find significant results; and therefore makes his/her research more appealing to biased journals. 

<!-- While meta-analysts and methodologies are hard in work to identify and correct for these issues, lack of data, and understanding makes the task overly challenging. 

This will consequently skew our collective knowledge when being aggregated by journals biased toward significant results. -->


## SAM

Here with SAM we are hoping that we can address this issue. We are trying to develop a standard and flexible framework for studying and enriching our understanding of the aformentioned complicated interactions. SAM is streamlining the process of designing and execution of large simulation studies covering all aspects of **performing a scientific research**, from designing the experiment setup to the process of reviewing and acceptance of a research by journal. 

\bibliography