---
title: sam::Researcher
summary: This class describes a researcher. 

---

# sam::Researcher



This class describes a researcher.  [More...](#detailed-description)


`#include <Researcher.h>`

## Public Functions

|                | Name           |
| -------------- | -------------- |
| | **[Researcher](/doxygen/Classes/classsam_1_1_researcher/#function-researcher)**() =default |
| void | **[preProcessData](/doxygen/Classes/classsam_1_1_researcher/#function-preprocessdata)**()<br>Applies the pro-processing methods on the [Experiment](/doxygen/Classes/classsam_1_1_experiment/).  |
| bool | **[isHacker](/doxygen/Classes/classsam_1_1_researcher/#function-ishacker)**()<br>Determines whether the [Researcher](/doxygen/Classes/classsam_1_1_researcher/) is a hacker.  |
| bool | **[isCommittingToTheHack](/doxygen/Classes/classsam_1_1_researcher/#function-iscommittingtothehack)**([HackingStrategy](/doxygen/Classes/classsam_1_1_hacking_strategy/) * hs)<br>Determines whether the [Researcher](/doxygen/Classes/classsam_1_1_researcher/) will commit to the given hack.  |
| void | **[research](/doxygen/Classes/classsam_1_1_researcher/#function-research)**()<br>Perform the Research.  |
| std::optional< SubmissionPool > | **[hackTheResearch](/doxygen/Classes/classsam_1_1_researcher/#function-hacktheresearch)**()<br>Applies the HackingWorkflow on the [Experiment](/doxygen/Classes/classsam_1_1_experiment/).  |
| void | **[randomizeHackingStrategies](/doxygen/Classes/classsam_1_1_researcher/#function-randomizehackingstrategies)**()<br>Randomizes the internal state of the [Researcher](/doxygen/Classes/classsam_1_1_researcher/).  |
| void | **[submitTheResearch](/doxygen/Classes/classsam_1_1_researcher/#function-submittheresearch)**(const std::optional< std::vector< [Submission](/doxygen/Classes/classsam_1_1_submission/) >> & subs)<br>Evaluating the candidates and submitting them to the [Journal](/doxygen/Classes/classsam_1_1_journal/).  |
| void | **[computeStuff](/doxygen/Classes/classsam_1_1_researcher/#function-computestuff)**() const<br>A helper function for re-computing all statistics at once.  |
| void | **[reset](/doxygen/Classes/classsam_1_1_researcher/#function-reset)**()<br>Resets the internal state of the [Researcher](/doxygen/Classes/classsam_1_1_researcher/).  |
| [ResearcherBuilder](/doxygen/Classes/classsam_1_1_researcher_builder/) | **[create](/doxygen/Classes/classsam_1_1_researcher/#function-create)**(std::string name) |

## Public Attributes

|                | Name           |
| -------------- | -------------- |
| std::vector< std::unique_ptr< [HackingStrategy](/doxygen/Classes/classsam_1_1_hacking_strategy/) > > | **[pre_processing_methods](/doxygen/Classes/classsam_1_1_researcher/#variable-pre_processing_methods)**  |
| std::unique_ptr< [Experiment](/doxygen/Classes/classsam_1_1_experiment/) > | **[experiment](/doxygen/Classes/classsam_1_1_researcher/#variable-experiment)** <br>[Researcher](/doxygen/Classes/classsam_1_1_researcher/)'s [Experiment](/doxygen/Classes/classsam_1_1_experiment/).  |
| std::shared_ptr< [Journal](/doxygen/Classes/classsam_1_1_journal/) > | **[journal](/doxygen/Classes/classsam_1_1_researcher/#variable-journal)** <br>[Researcher](/doxygen/Classes/classsam_1_1_researcher/)'s [Journal](/doxygen/Classes/classsam_1_1_journal/) of choice!  |
| std::unique_ptr< [ResearchStrategy](/doxygen/Classes/classsam_1_1_research_strategy/) > | **[research_strategy](/doxygen/Classes/classsam_1_1_researcher/#variable-research_strategy)** <br>[Researcher](/doxygen/Classes/classsam_1_1_researcher/)'s Research Strategy.  |
| [HackingWorkflow](/doxygen/Modules/group___policies/#using-hackingworkflow) | **[original_workflow](/doxygen/Classes/classsam_1_1_researcher/#variable-original_workflow)** <br>Original set of hacking strategies and their Selection→Decision sequences.  |
| [HackingWorkflow](/doxygen/Modules/group___policies/#using-hackingworkflow) | **[hacking_workflow](/doxygen/Classes/classsam_1_1_researcher/#variable-hacking_workflow)**  |

## Friends

|                | Name           |
| -------------- | -------------- |
| class | **[ResearcherBuilder](/doxygen/Classes/classsam_1_1_researcher/#friend-researcherbuilder)**  |

## Detailed Description

```cpp
class sam::Researcher;
```

This class describes a researcher. 

[Researcher](/doxygen/Classes/classsam_1_1_researcher/) is the main player of the game. It has access to _almost_ everything and it works with several other components to conduct and evaluate the research, and prepare it to be submitted to the [Journal](/doxygen/Classes/classsam_1_1_journal/). 

## Public Functions Documentation

### function Researcher

```cpp
Researcher() =default
```


This doesn't do anything! But it should! At the moment, I'm relying on the [ResearcherBuilder](/doxygen/Classes/classsam_1_1_researcher_builder/) to construct the [Researcher](/doxygen/Classes/classsam_1_1_researcher/) but this has to change 


### function preProcessData

```cpp
void preProcessData()
```

Applies the pro-processing methods on the [Experiment](/doxygen/Classes/classsam_1_1_experiment/). 

**Note**: This has a very similar implementation to the `[hackTheResearch()](/doxygen/Classes/classsam_1_1_researcher/#function-hacktheresearch)` but it doesn't perform any of the secondary checks, and it does not incorporates any of the selection → decision sequences. 

Iterating over the registered [pre_processing_methods](/doxygen/Classes/classsam_1_1_researcher/#variable-pre_processing_methods), this applies all of the them to the current experiment. Keep in mind that the pre-processing is done before any of the decision/hacking stages, and right after data generation.


### function isHacker

```cpp
bool isHacker()
```

Determines whether the [Researcher](/doxygen/Classes/classsam_1_1_researcher/) is a hacker. 

**Note**: Note that the #probability_of_being_a_hacker is called through it's call operator(). This guarantees that its value is being randomized _only if_ it contains a distribution. 

This technically invokes the #probability_of_being_a_hacker, and returns the outcome. The value then will be cast-ed to a boolean to determine whether the [Researcher](/doxygen/Classes/classsam_1_1_researcher/) is going to start the hacking procedure or not, ie., calling or skipping the [hackTheResearch()](/doxygen/Classes/classsam_1_1_researcher/#function-hacktheresearch).


### function isCommittingToTheHack

```cpp
bool isCommittingToTheHack(
    HackingStrategy * hs
)
```

Determines whether the [Researcher](/doxygen/Classes/classsam_1_1_researcher/) will commit to the given hack. 

Similar to the [isHacker()](/doxygen/Classes/classsam_1_1_researcher/#function-ishacker) method, this returns a boolean indicating whether or not the [Researcher](/doxygen/Classes/classsam_1_1_researcher/) will commit to the given hacking method. The probability of commitment to a hacking strategy is being calculated from the value of #probability_of_committing_a_hack. 


### function research

```cpp
void research()
```

Perform the Research. 

This is the main routine of the [Researcher](/doxygen/Classes/classsam_1_1_researcher/). It is responsible for a few things:



* Randomizing the [Experiment](/doxygen/Classes/classsam_1_1_experiment/), if necessary
* Initializing the [Experiment](/doxygen/Classes/classsam_1_1_experiment/)
* Performing the research by:
    * Generating the data
    * Pre-processing the Data, if necessary
    * Calculating the statistics
    * Deciding whether to hack or not
        * Perform the hack, if necessary
    * Deciding whether to replicate the research
        * Perform the replication, if necessary
    * Evaluate the list of final submissions
    * Submit the final submissions to the [Journal](/doxygen/Classes/classsam_1_1_journal/), or discard the [Experiment](/doxygen/Classes/classsam_1_1_experiment/)
    * Clean up everything, and start a get ready for a new run
The internal of the method is based on sequential application of selection → decision sequences on the experiment. Throughout the process, the researcher keeps the list of candidate submissions, #candidate_submissions, up-to-date. This starts by the initial selection, and following though with the hacking, and stashing selection. At the end of each replication, if any, researcher collects the last submission candidate and head to perform a new experiment. After performing all the replications (or skipping some), researcher perform a final selection → decision on the list of #replicated_submissions and select her final submission to be submitted to the [Journal](/doxygen/Classes/classsam_1_1_journal/). 


### function hackTheResearch

```cpp
std::optional< SubmissionPool > hackTheResearch()
```

Applies the HackingWorkflow on the [Experiment](/doxygen/Classes/classsam_1_1_experiment/). 

**Return**: Returns `true` if any of the decision steps passes, it returns `false` indicating that none of the selection → decisions were successful. 

This uses HackingWorkflow to sequentially apply sets of hacking → selection → decision on the available [Experiment](/doxygen/Classes/classsam_1_1_experiment/). Before applying each hacking strategy, researcher asks [isCommittingToTheHack()](/doxygen/Classes/classsam_1_1_researcher/#function-iscommittingtothehack) to decide on whether or not it is going to commit to a hack, if not, the rest of the set will be ignored, and researcher continues with the next set, if available.


### function randomizeHackingStrategies

```cpp
void randomizeHackingStrategies()
```

Randomizes the internal state of the [Researcher](/doxygen/Classes/classsam_1_1_researcher/). 

**Note**: It worth mentioning that, this method doesn't randomize the internal parameters of individual hacking strategies. Hacking strategies parameters can be randomized only if their parameters are set to be a Parameter<T>. 

Based on the provided settings, this re-selects, re-arranges, and shuffles the list of hacking strategies, and their corresponding parameters.


### function submitTheResearch

```cpp
void submitTheResearch(
    const std::optional< std::vector< Submission >> & subs
)
```

Evaluating the candidates and submitting them to the [Journal](/doxygen/Classes/classsam_1_1_journal/). 

This checks whether there is any submissions at all, if so, it checks whether `submission_decision_policies` have any hits, if so, it gives a green light to [Researcher](/doxygen/Classes/classsam_1_1_researcher/) to submit the list of submissions; otherwise, it discards the list. 


### function computeStuff

```cpp
inline void computeStuff() const
```

A helper function for re-computing all statistics at once. 

### function reset

```cpp
inline void reset()
```

Resets the internal state of the [Researcher](/doxygen/Classes/classsam_1_1_researcher/). 

### function create

```cpp
static ResearcherBuilder create(
    std::string name
)
```


**Parameters**: 

  * **name** The researcher name 


**Return**: An instance of [ResearcherBuilder](/doxygen/Classes/classsam_1_1_researcher_builder/). 

Starts the [Researcher](/doxygen/Classes/classsam_1_1_researcher/) build process. Use this to build a new instance of the [Researcher](/doxygen/Classes/classsam_1_1_researcher/).


## Public Attributes Documentation

### variable pre_processing_methods

```cpp
std::vector< std::unique_ptr< HackingStrategy > > pre_processing_methods;
```


List of hacking strategies that are going to be applied on the experiment during the pre-processing stage 


### variable experiment

```cpp
std::unique_ptr< Experiment > experiment;
```

[Researcher](/doxygen/Classes/classsam_1_1_researcher/)'s [Experiment](/doxygen/Classes/classsam_1_1_experiment/). 

### variable journal

```cpp
std::shared_ptr< Journal > journal;
```

[Researcher](/doxygen/Classes/classsam_1_1_researcher/)'s [Journal](/doxygen/Classes/classsam_1_1_journal/) of choice! 

### variable research_strategy

```cpp
std::unique_ptr< ResearchStrategy > research_strategy;
```

[Researcher](/doxygen/Classes/classsam_1_1_researcher/)'s Research Strategy. 

### variable original_workflow

```cpp
HackingWorkflow original_workflow;
```

Original set of hacking strategies and their Selection→Decision sequences. 

### variable hacking_workflow

```cpp
HackingWorkflow hacking_workflow;
```


[Researcher](/doxygen/Classes/classsam_1_1_researcher/)'s hacking workflow. This is a subset of the [original_workflow](/doxygen/Classes/classsam_1_1_researcher/#variable-original_workflow), as it is being filtered and rearranged by various factors during the initialization. 


## Friends

### friend ResearcherBuilder

```cpp
friend class ResearcherBuilder(
    ResearcherBuilder 
);
```


-------------------------------

Updated on 29 June 2021 at 16:13:46 CEST