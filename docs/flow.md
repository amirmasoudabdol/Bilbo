---
title: Flow
---

# Execution Flow

SAM simulates the process of producing a scientific research through several subprocesses as depicted in Figure 1. Each rounded rectangle describes a process, often performs by one of the components or through the collaboration between different components. This chapter describes each subprocess in more details.

![<b>Figure 1.</b> Overall Execution Flow of SAM](/figures/main-routine.png)

!!! info
	In the this and following sections, we will heavily use flowchart digrams to visualize and express processes and algorithms. If you are not familiar with general syntax of flowcharts, please read out the Wikipedia article on [Flowcharts](https://en.wikipedia.org/wiki/Flowchart#Building_blocks).

## Initialization

During the initialization phase, SAMs loads a configuration file and initializes different compartments based on the given parameters. Details of the configuration file is described in more details [here](configuration-file.md). 

![<b>Figure 2.</b> Initialization Routine.](/figures/initialization.png)

After reading user parameters, SAM proceeds with initializing each of its components. Initialization mainly prepares the internal specifications of each compartment. At the end of the initialization stage, `Researcher` is aware of all parameters and is ready to conduct the — already established — `Experiment`.

## Preparing the Research

The preparation of the research is the first step of the simulation. This step resembles the process of collecting the data for the study. At this stage, the `Researcher` uses the information provided by `Experiment Setup` to produce/collect data points for each group/condition/dv using the `Data Strategy` module.

![<b>Figure 3.</b> Preparing the Research.](/figures/prepare-research.png)

## Performing the Research

At this stage, `Researcher` uses `Test Strategy` (defined in `Experiment Setup`) to run the test and populates relevant parameters, e.g., `statistic, pvalue, sig, side`. Similarly, `Effect Strategy` will be used to calculate effect sizes.

The next step is to check whether `Researcher` is satisfied with test results. This is being done by passing the `Experiment` to `Decision Strategy`. `Researcher` relies on decision strategy's verdict to decide whether to proceed with the current Submission or to continue applying one or more of the hacking strategies on the experiment before submitting the study for the review. This process will be discussed in more details in *[Decision Strategy](decision-strategy.md)* section.

![Figure 4. Steps involving performing the research](/figures/perform-research.png)

## Publishing the Research

Process of publishing a research resembles the preparation of the final manuscript and sending it to the Journal for review.

After performing the research, applying any of QRPs (if necessary), `Researcher` continues with the preparation of its **final** Submission. This is being done through the `Decision Strategy` where the researcher select a specific outcome based on given criteria. In the case where researcher finds an outcome to submit for review, a `Submission` record will be generated and will be submitted to the `Journal`. 

Journal will judge the submitted `Submission` based on the criteria defined in its `Selection Strategy` routine. If accepted, `Journal` adds the submission to its publication lists for further analysis.

![Figure 5. Steps involving publishing a research](/figures/publish-research.png)
