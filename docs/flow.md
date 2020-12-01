# Execution Flow

SAM simulates the process of producing a scientific research through several subprocesses as depicted in Figure 1. Each rounded rectangle describes a process, that either performs entirely by one of the components or through the collaboration between different ones. This chapter describes each process in more details.

In this section, we expand each process to their sub-processes and describe the overall execution flow of a simulation.

![<b>Figure 1.</b> Overall Execution Flow of SAM](/figures/main-routine.png)

!!! info
	In the this and following sections, we will heavily use flowchart digrams to visualize and express processes and algorithms. If you are not familiar with general syntax of flowcharts, please read out the Wikipedia article on [Flowcharts](https://en.wikipedia.org/wiki/Flowchart#Building_blocks).

## Initialization

During the initialization phase, SAMs loads a configuration file and initializes many of its compartments based on the given parameters. 

![<b>Figure 2.</b> Initialization Routine.](/figures/initialization.png)

By the end of the initialization step, Researcher knos his Experiment Setup, his overall plan for conducting the research and has decided on his arsenal of possible questionable research practices. Additionally, Journal will be initialized and be ready to review Researcher's submissions.

<!-- After reading user parameters, SAM proceeds with initializing each of its components. Initialization mainly prepares the internal specifications of each compartment. At the end of the initialization stage, Researcher is aware of all parameters and is ready to conduct the — already established — Experiment. -->

## Preparing the Research

The preparation of research is the first step of the simulation. At this stage, Researcher uses the information provided within Experiment Setup and collect data points for each group/condition/dv. 


![<b>Figure 3.</b> Preparing the Research.](/figures/prepare-research.png)


By the end of this stage, Experiment is populated with data points and Researcher is ready to conduct his research as prescribed within the configuration file.

## Performing the Research

At this stage, Researcher uses Test Strategy to run the test and populates relevant variables, e.g., `statistic`, `pvalue`, `sig`, `side`. Similarly, Effect Strategy will be used to calculate effect sizes, and populate `effect` variable.

The next step is to check whether Researcher is satisfied with test results. This is being done by passing the Experiment to Decision Strategy. Researcher relies on decision strategy's verdict to decide on whether to proceed with the current Submission, or continue applying one or more of the hacking strategies before submitting the study for the review. This process will be discussed in more details in [Research Workflow](/research-workflow.md), and *[Decision Strategy](/decision-strategies.md)* section.


![Figure 4. Steps involving performing the research](/figures/perform-research.png)

By the end of this stage, Researcher is concluded his research and is ready to prepare his Submission, ie., manuscript.

## Publishing the Research

This last stage resembles the preperation process of the final manuscript and consequently sending it to the Journal for review.

After finalizing the research and applying any of QRPs (if necessary), Researcher prepares his **final** Submission. This is being done through the logic coded within the Decision Strategy module. In the case where Researcher finds an outcome, a Submission record will be created and will be submitted/sent to the Journal. If Researcher is not satisfied with any of the available outcome, he discards the Experiment, and skips the rest of this stage.

Journal will evaluates the submitted Submission based on the criteria definedby Selection Strategy module. If accepted, Journal adds the submission to its publications list for further analysis.

![Figure 5. Steps involving publishing a research](/figures/publish-research.png)

Despites what happens to Experiment and Submission (ie., discardment, rejection or acceptance by Journal), Researcher is done by the current Experiment and initializes a new Experiment.