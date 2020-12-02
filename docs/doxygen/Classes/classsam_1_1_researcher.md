---
title: sam::Researcher


---

# sam::Researcher



















## Public Functions

|                | Name           |
| -------------- | -------------- |
|  | **[Researcher](/doxygen/Classes/classsam_1_1_researcher/#function-researcher)**() =default  |
| bool | **[isHacker](/doxygen/Classes/classsam_1_1_researcher/#function-ishacker)**()  |
| bool | **[isCommittingToTheHack](/doxygen/Classes/classsam_1_1_researcher/#function-iscommittingtothehack)**([HackingStrategy](/doxygen/Classes/classsam_1_1_hacking_strategy/) * hs)  |
| void | **[preProcessData](/doxygen/Classes/classsam_1_1_researcher/#function-preprocessdata)**()  |
| void | **[research](/doxygen/Classes/classsam_1_1_researcher/#function-research)**() <br>Executing the research workflow.  |
| void | **[letTheHackBegin](/doxygen/Classes/classsam_1_1_researcher/#function-letthehackbegin)**()  |
| void | **[randomizeParameters](/doxygen/Classes/classsam_1_1_researcher/#function-randomizeparameters)**()  |
| void | **[reorderHackingStrategies](/doxygen/Classes/classsam_1_1_researcher/#function-reorderhackingstrategies)**(HackingWorkflow & hw, std::string priority) <br>Re-order the hacking strategies according the priority.  |
| void | **[checkAndsubmitTheResearch](/doxygen/Classes/classsam_1_1_researcher/#function-checkandsubmittheresearch)**(const std::optional< [Submission](/doxygen/Classes/classsam_1_1_submission/) > & sub) <br>Checking the final submission and submitting it to the [Journal](/doxygen/Classes/classsam_1_1_journal/).  |
| void | **[computeStuff](/doxygen/Classes/classsam_1_1_researcher/#function-computestuff)**()  |
| void | **[setDecisionStrategy](/doxygen/Classes/classsam_1_1_researcher/#function-setdecisionstrategy)**(std::unique_ptr< [DecisionStrategy](/doxygen/Classes/classsam_1_1_decision_strategy/) > ds)  |
| [ResearcherBuilder](/doxygen/Classes/classsam_1_1_researcher_builder/) | **[create](/doxygen/Classes/classsam_1_1_researcher/#function-create)**(std::string name)  |


## Public Attributes

|                | Name           |
| -------------- | -------------- |
| std::unique_ptr< [Experiment](/doxygen/Classes/classsam_1_1_experiment/) > | **[experiment](/doxygen/Classes/classsam_1_1_researcher/#variable-experiment)**  |
| std::shared_ptr< [Journal](/doxygen/Classes/classsam_1_1_journal/) > | **[journal](/doxygen/Classes/classsam_1_1_researcher/#variable-journal)**  |
| std::unique_ptr< [DecisionStrategy](/doxygen/Classes/classsam_1_1_decision_strategy/) > | **[decision_strategy](/doxygen/Classes/classsam_1_1_researcher/#variable-decision_strategy)**  |
| std::vector< std::vector< std::unique_ptr< [HackingStrategy](/doxygen/Classes/classsam_1_1_hacking_strategy/) > > > | **[hacking_strategies](/doxygen/Classes/classsam_1_1_researcher/#variable-hacking_strategies)**  |
| bool | **[is_pre_processing](/doxygen/Classes/classsam_1_1_researcher/#variable-is_pre_processing)**  |
| std::vector< std::unique_ptr< [HackingStrategy](/doxygen/Classes/classsam_1_1_hacking_strategy/) > > | **[pre_processing_methods](/doxygen/Classes/classsam_1_1_researcher/#variable-pre_processing_methods)**  |
| size_t | **[n_hacks](/doxygen/Classes/classsam_1_1_researcher/#variable-n_hacks)** <br>Number of hacking strategies to be choosen from the given list of strategies.  |
| bool | **[reselect_hacking_strategies_after_every_simulation](/doxygen/Classes/classsam_1_1_researcher/#variable-reselect_hacking_strategies_after_every_simulation)**  |
| std::string | **[hacking_selection_priority](/doxygen/Classes/classsam_1_1_researcher/#variable-hacking_selection_priority)**  |
| std::string | **[hacking_execution_order](/doxygen/Classes/classsam_1_1_researcher/#variable-hacking_execution_order)** <br>Indicates the execution order of selected/given hacking strategies.  |
| [Parameter](/doxygen/Classes/classsam_1_1_parameter/)< double > | **[probability_of_being_a_hacker](/doxygen/Classes/classsam_1_1_researcher/#variable-probability_of_being_a_hacker)** <br>Indicates the probablity of a [Researcher](/doxygen/Classes/classsam_1_1_researcher/)_deciding_ to go for hacking an [Experiment](/doxygen/Classes/classsam_1_1_experiment/).  |
| std::variant< double, std::string, Distribution, std::unique_ptr< [HackingProbabilityStrategy](/doxygen/Classes/classsam_1_1_hacking_probability_strategy/) > > | **[probability_of_committing_a_hack](/doxygen/Classes/classsam_1_1_researcher/#variable-probability_of_committing_a_hack)** <br>Indicates the probablity of a [Researcher](/doxygen/Classes/classsam_1_1_researcher/)_actally applying_ a choosen hacking strategy.  |
| double | **[submission_probability](/doxygen/Classes/classsam_1_1_researcher/#variable-submission_probability)**  |
| SubmissionPool | **[submissions_from_reps](/doxygen/Classes/classsam_1_1_researcher/#variable-submissions_from_reps)** <br>A [Submission]() record that [Researcher](/doxygen/Classes/classsam_1_1_researcher/) is going to submit to the [Journal](/doxygen/Classes/classsam_1_1_journal/).  |
| HackingWorkflow | **[original_workflow](/doxygen/Classes/classsam_1_1_researcher/#variable-original_workflow)**  |
| HackingWorkflow | **[h_workflow](/doxygen/Classes/classsam_1_1_researcher/#variable-h_workflow)**  |


## Friends

|                | Name           |
| -------------- | -------------- |
| class | **[ResearcherBuilder](/doxygen/Classes/classsam_1_1_researcher/#friend-researcherbuilder)**  |












## Public Functions Documentation

### function Researcher

```cpp
Researcher() =default
```













**Note**: This is defined `private` because I want force the user to use the `create(name)` method and therefore delegate the construction to the [ResearcherBuilder](/doxygen/Classes/classsam_1_1_researcher_builder/). 














Default constructor of the [Researcher](/doxygen/Classes/classsam_1_1_researcher/).


### function isHacker

```cpp
bool isHacker()
```
















**Todo**: this should not draw a new value every time, and should draw once and keep reporting that one. \updated Should it thought? 













### function isCommittingToTheHack

```cpp
bool isCommittingToTheHack(
    HackingStrategy * hs
)
```





























### function preProcessData

```cpp
void preProcessData()
```













**Note**: This has a very similar implemention to the `hack()` but it doesn't perform any of the secondary checks. 














Iterating over the registrated methods and run them on the current experiment.


### function research

```cpp
void research()
```

Executing the research workflow. 


























This is the main routine that the [Researcher](/doxygen/Classes/classsam_1_1_researcher/) execute. 

Preparing the experiment for a new Research



------------------


 Initial SELECTION



------------------


 WillBeHacking DECISION

If we are a hacker, and we decide to start hacking — based on the current submission —, then, we are going to the hacking procedure!



------------------


 BetweenHackedOutcome SELECTION

If the pool of viable submissions is not empty, then we have to choose between them! Otherwise, we don't have to look into the pile!



------------------


 Replication Stashings

If we have a submittable candidate, then we collect it



------------------


 Will Continue Replicating DECISION

BetweenReplications SELECTION

If we have done more than one replication, then we have to select between them

If we did only one replication, then if there is anything, that's our final submission

### function letTheHackBegin

```cpp
void letTheHackBegin()
```




























TodoDoes this copy even make any sense! I don't think so! 

This is a handy flag for propogating the information out of the std::visit.

TodoNow that I have a set, I don't really need the has_commited variable! 

In each step, we either run a hack or a policy

Performing a Hack

If we are not committed to the method, then, we just leave the entire set behind

Performing a Selection With [PolicyChainSet](/doxygen/Classes/structsam_1_1_policy_chain_set/) we can look for different results

Performing a Decision With [PolicyChain](/doxygen/Classes/structsam_1_1_policy_chain/), we can only validate if a submission passes all the criteria

Since I'm going to continue hacking, I'm going to reset the candidate because it should be evaluated again, and I've already performed a selection, I'm going to reset the selected submission. Bug, this could possibly cause some confusion! In cases where I only have one strategy and wants to be done after it, this role discard the last selection. @workaround, the current workaround is to select from the stash using between_hacking_selection 

We leave the workflow when we have a submission, and it also passes the decision policy

### function randomizeParameters

```cpp
void randomizeParameters()
```




























Clearing the list

Shuffling the original list

Sorting based on the given selection criteria

Reordering based on the given execution order

Then I need a for-loop to randomize each strategy

* I think this might not be necessary as [Parameter](/doxygen/Classes/classsam_1_1_parameter/) handles the randomization automatically

### function reorderHackingStrategies

```cpp
void reorderHackingStrategies(
    HackingWorkflow & hw,
    std::string priority
)
```

Re-order the hacking strategies according the priority. 




























### function checkAndsubmitTheResearch

```cpp
void checkAndsubmitTheResearch(
    const std::optional< Submission > & sub
)
```

Checking the final submission and submitting it to the [Journal](/doxygen/Classes/classsam_1_1_journal/). 















**Todo**: Maybe I should pass the `final_submission` to this, and don't rely on it reading it from the `decision_strategy`













### function computeStuff

```cpp
inline void computeStuff()
```





























### function setDecisionStrategy

```cpp
inline void setDecisionStrategy(
    std::unique_ptr< DecisionStrategy > ds
)
```


**Parameters**: 

  * **d** The pointer to a Decision Strategy












**Note**: [Researcher](/doxygen/Classes/classsam_1_1_researcher/) owns its decision strategy that's why I move the pointer.



**Todo**: I think I need to do the `std::move` when I'm calling the function not inside it 











Set the decisionStrategy of the researcher.


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

### variable experiment

```cpp
std::unique_ptr< Experiment > experiment;
```





























### variable journal

```cpp
std::shared_ptr< Journal > journal;
```





























### variable decision_strategy

```cpp
std::unique_ptr< DecisionStrategy > decision_strategy;
```





























### variable hacking_strategies

```cpp
std::vector< std::vector< std::unique_ptr< HackingStrategy > > > hacking_strategies;
```





























### variable is_pre_processing

```cpp
bool is_pre_processing {false};
```





























### variable pre_processing_methods

```cpp
std::vector< std::unique_ptr< HackingStrategy > > pre_processing_methods;
```





























### variable n_hacks

```cpp
size_t n_hacks;
```

Number of hacking strategies to be choosen from the given list of strategies. 




























### variable reselect_hacking_strategies_after_every_simulation

```cpp
bool reselect_hacking_strategies_after_every_simulation {false};
```





























### variable hacking_selection_priority

```cpp
std::string hacking_selection_priority;
```



























Indicates order in which hacking strategies are going to be selected from the list of given hacking strategies if the [Researcher](/doxygen/Classes/classsam_1_1_researcher/) decides has to apply a fewer number than the given list 


### variable hacking_execution_order

```cpp
std::string hacking_execution_order;
```

Indicates the execution order of selected/given hacking strategies. 




























### variable probability_of_being_a_hacker

```cpp
Parameter< double > probability_of_being_a_hacker;
```

Indicates the probablity of a [Researcher](/doxygen/Classes/classsam_1_1_researcher/)_deciding_ to go for hacking an [Experiment](/doxygen/Classes/classsam_1_1_experiment/). 




























### variable probability_of_committing_a_hack

```cpp
std::variant< double, std::string, Distribution, std::unique_ptr< HackingProbabilityStrategy > > probability_of_committing_a_hack;
```

Indicates the probablity of a [Researcher](/doxygen/Classes/classsam_1_1_researcher/)_actally applying_ a choosen hacking strategy. 




























### variable submission_probability

```cpp
double submission_probability {1};
```





























### variable submissions_from_reps

```cpp
SubmissionPool submissions_from_reps;
```

A [Submission]() record that [Researcher](/doxygen/Classes/classsam_1_1_researcher/) is going to submit to the [Journal](/doxygen/Classes/classsam_1_1_journal/). 




























### variable original_workflow

```cpp
HackingWorkflow original_workflow;
```





























### variable h_workflow

```cpp
HackingWorkflow h_workflow;
```































## Friends

### friend ResearcherBuilder

```cpp
friend class ResearcherBuilder;
```































-------------------------------

Updated on  2 December 2020 at 14:48:54 CET