# Execution Flow

SAM simulates the process of producing scientific research through several sub-processes as depicted in Figure 1. Each rounded rectangle describes a process that is either performed entirely by one of the components or through a collaboration between different ones. This chapter describes each process in more details.

In this section, we expand each process to their sub-processes and describe the overall execution flow of a simulation.

![<b>Figure 1.</b> Overall Execution Flow of SAM](/figures/main-routine.png)

!!! info
	In the this and following sections, we will use flowchart diagrams to visualize and express processes and algorithms. If you are not familiar with general syntax of flowcharts, please read the Wikipedia article on [Flowcharts](https://en.wikipedia.org/wiki/Flowchart#Building_blocks).

## Initialization

During the initialization phase, SAMs loads a configuration file and initializes many of its compartments based on the given parameters. 

![<b>Figure 2.</b> Initialization Routine.](/figures/initialization.png)

By the end of the initialization step, the Researcher knows his Experiment Setup, his overall plan for conducting the research and has decided on his arsenal of possible questionable research practices. Additionally, the Journal is initialized and ready to review Researcher's submissions.

<!-- After reading user parameters, SAM proceeds with initializing each of its components. Initialization mainly prepares the internal specifications of each compartment. At the end of the initialization stage, Researcher is aware of all parameters and is ready to conduct the — already established — Experiment. -->

## Preparing the Research

The preparation of research is the first step of the simulation. At this stage, The Researcher uses the information provided within the Experiment Setup and collects data points for each group and dependent variable. 


![<b>Figure 3.</b> Preparing the Research.](/figures/prepare-research.png)


By the end of this stage, the Experiment is populated with data points and the Researcher is ready to conduct his research as prescribed within the configuration file.

## Performing the Research

At this stage, the Researcher uses the Test Strategy to run the test and populate relevant variables, e.g., `statistic`, `pvalue`, `sig`, `side`. Similarly, Effect Strategy will be used to calculate effect sizes, and populate `effect` variable.

The next step is to check whether the Researcher is satisfied with the test results. This is done by passing the Experiment to the Decision Strategy. The Researcher relies on decision strategy's verdict to decide on whether to proceed with the current Submission, or continue applying one or more of the hacking strategies before submitting the study for the review. This process will be discussed in more details in [Research Workflow](research-workflow.md) and *[Decision Strategy](decision-strategies.md)*.


![Figure 4. Steps involved in performing the research](/figures/perform-research.png)

By the end of this stage, the Researcher has finished his research and is ready to prepare his Submission, ie., manuscript.

## Publishing the Research

This last stage simulates the preparation process of the final manuscript and consequently sending it to the Journal for review.

After finalizing the research and applying any of QRPs (if necessary), the Researcher prepares his **final** Submission. This is done through the logic coded within the Decision Strategy module. In the case where the Researcher finds an outcome, a Submission record will be created and submitted/sent to the Journal. If the Researcher is not satisfied with any of the available outcome, he discards the Experiment, and skips the rest of this stage.

The Journal evaluates the received Submission based on the criteria defined by the Selection Strategy module. If accepted, the Journal adds the submission to its publications list for further analysis.

![Figure 5. Steps involving publishing a research](/figures/publish-research.png)

Despite what happens to the Experiment and Submission (ie., discardment, rejection or acceptance by the Journal), the Researcher is done by the current Experiment and initializes a new Experiment.