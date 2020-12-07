---
title: sam::DecisionStrategy
summary: Abstract class for different decision strategies.  

---

# sam::DecisionStrategy




Abstract class for different decision strategies. 

`#include <DecisionStrategy.h>`



Inherited by [sam::DefaultDecisionMaker](/doxygen/Classes/classsam_1_1_default_decision_maker/)










## Public Functions

|                | Name           |
| -------------- | -------------- |
| virtual  | **[~DecisionStrategy](/doxygen/Classes/classsam_1_1_decision_strategy/#function-~decisionstrategy)**() =0  |
|  | **[DecisionStrategy](/doxygen/Classes/classsam_1_1_decision_strategy/#function-decisionstrategy)**()  |
| virtual bool | **[willStartHacking](/doxygen/Classes/classsam_1_1_decision_strategy/#function-willstarthacking)**() <br>Indicates whether the researcher will start going to the hacking procedure. The default here is to not go for hacking if we already have one candidate; but this can be overridden in different decision strategies.  |
| virtual bool | **[willContinueHacking](/doxygen/Classes/classsam_1_1_decision_strategy/#function-willcontinuehacking)**([Experiment](/doxygen/Classes/classsam_1_1_experiment/) * experiment, [PolicyChain](/doxygen/Classes/structsam_1_1_policy_chain/) & pchain) <br>This will be used by `letTheHackBegin` and uses the decision policy to decide whether the next hacking strategy is going to be executed !  |
| bool | **[willBeSubmitting](/doxygen/Classes/classsam_1_1_decision_strategy/#function-willbesubmitting)**(const std::optional< [Submission](/doxygen/Classes/classsam_1_1_submission/) > & sub, [PolicyChain](/doxygen/Classes/structsam_1_1_policy_chain/) & pchain) <br>[Submission]().  |
| virtual bool | **[willContinueReplicating](/doxygen/Classes/classsam_1_1_decision_strategy/#function-willcontinuereplicating)**([PolicyChain](/doxygen/Classes/structsam_1_1_policy_chain/) & pchain)  |
| void | **[clear](/doxygen/Classes/classsam_1_1_decision_strategy/#function-clear)**()  |
| void | **[reset](/doxygen/Classes/classsam_1_1_decision_strategy/#function-reset)**()  |
| virtual [DecisionStrategy](/doxygen/Classes/classsam_1_1_decision_strategy/) & | **[selectOutcomeFromExperiment](/doxygen/Classes/classsam_1_1_decision_strategy/#function-selectoutcomefromexperiment)**([Experiment](/doxygen/Classes/classsam_1_1_experiment/) * experiment, [PolicyChainSet](/doxygen/Classes/structsam_1_1_policy_chain_set/) & pchain_set) =0 <br>Implementation of decision-making procedure.  |
| virtual [DecisionStrategy](/doxygen/Classes/classsam_1_1_decision_strategy/) & | **[selectOutcomeFromPool](/doxygen/Classes/classsam_1_1_decision_strategy/#function-selectoutcomefrompool)**(SubmissionPool & spool, [PolicyChainSet](/doxygen/Classes/structsam_1_1_policy_chain_set/) & pchain_set) =0  |
| void | **[saveEveryOutcome](/doxygen/Classes/classsam_1_1_decision_strategy/#function-saveeveryoutcome)**([Experiment](/doxygen/Classes/classsam_1_1_experiment/) & experiment)  |
| void | **[saveOutcomes](/doxygen/Classes/classsam_1_1_decision_strategy/#function-saveoutcomes)**([Experiment](/doxygen/Classes/classsam_1_1_experiment/) & experiment, [PolicyChain](/doxygen/Classes/structsam_1_1_policy_chain/) & pchain)  |
| std::unique_ptr< [DecisionStrategy](/doxygen/Classes/classsam_1_1_decision_strategy/) > | **[build](/doxygen/Classes/classsam_1_1_decision_strategy/#function-build)**(json & decision_strategy_config)  |

## Protected Functions

|                | Name           |
| -------------- | -------------- |
| void | **[saveCurrentSubmissionCandidate](/doxygen/Classes/classsam_1_1_decision_strategy/#function-savecurrentsubmissioncandidate)**()  |
| void | **[selectOutcome](/doxygen/Classes/classsam_1_1_decision_strategy/#function-selectoutcome)**([Experiment](/doxygen/Classes/classsam_1_1_experiment/) & experiment, [PolicyChainSet](/doxygen/Classes/structsam_1_1_policy_chain_set/) & pchain_set)  |
| void | **[selectBetweenSubmissions](/doxygen/Classes/classsam_1_1_decision_strategy/#function-selectbetweensubmissions)**(SubmissionPool & spool, [PolicyChainSet](/doxygen/Classes/structsam_1_1_policy_chain_set/) & pchain_set)  |

## Public Attributes

|                | Name           |
| -------------- | -------------- |
| sol::state | **[lua](/doxygen/Classes/classsam_1_1_decision_strategy/#variable-lua)**  |
| json | **[config_](/doxygen/Classes/classsam_1_1_decision_strategy/#variable-config_)**  |
| std::optional< [Submission](/doxygen/Classes/classsam_1_1_submission/) > | **[submission_candidate](/doxygen/Classes/classsam_1_1_decision_strategy/#variable-submission_candidate)**  |
| SubmissionPool | **[submissions_pool](/doxygen/Classes/classsam_1_1_decision_strategy/#variable-submissions_pool)** <br>List of selected [Submission]() by the researcher, during the hacking procedure.  |
| [PolicyChainSet](/doxygen/Classes/structsam_1_1_policy_chain_set/) | **[initial_selection_policies](/doxygen/Classes/classsam_1_1_decision_strategy/#variable-initial_selection_policies)**  |
| [PolicyChain](/doxygen/Classes/structsam_1_1_policy_chain/) | **[submission_decision_policies](/doxygen/Classes/classsam_1_1_decision_strategy/#variable-submission_decision_policies)**  |
| [PolicyChainSet](/doxygen/Classes/structsam_1_1_policy_chain_set/) | **[between_hacks_selection_policies](/doxygen/Classes/classsam_1_1_decision_strategy/#variable-between_hacks_selection_policies)**  |
| [PolicyChainSet](/doxygen/Classes/structsam_1_1_policy_chain_set/) | **[between_reps_policies](/doxygen/Classes/classsam_1_1_decision_strategy/#variable-between_reps_policies)**  |
| [PolicyChain](/doxygen/Classes/structsam_1_1_policy_chain/) | **[will_start_hacking_decision_policies](/doxygen/Classes/classsam_1_1_decision_strategy/#variable-will_start_hacking_decision_policies)**  |
| [PolicyChain](/doxygen/Classes/structsam_1_1_policy_chain/) | **[will_continue_replicating_decision_policy](/doxygen/Classes/classsam_1_1_decision_strategy/#variable-will_continue_replicating_decision_policy)**  |
| [PolicyChain](/doxygen/Classes/structsam_1_1_policy_chain/) | **[stashing_policy](/doxygen/Classes/classsam_1_1_decision_strategy/#variable-stashing_policy)**  |














## Public Functions Documentation

### function ~DecisionStrategy

```cpp
virtual ~DecisionStrategy() =0
```



























Pure deconstructor of [DecisionStrategy](/doxygen/Classes/classsam_1_1_decision_strategy/). This is necessary for proper deconstruction of derived classes. 


### function DecisionStrategy

```cpp
DecisionStrategy()
```





























### function willStartHacking

```cpp
inline virtual bool willStartHacking()
```

Indicates whether the researcher will start going to the hacking procedure. The default here is to not go for hacking if we already have one candidate; but this can be overridden in different decision strategies. 

























**Reimplemented by**: [sam::DefaultDecisionMaker::willStartHacking](/doxygen/Classes/classsam_1_1_default_decision_maker/#function-willstarthacking)




### function willContinueHacking

```cpp
inline virtual bool willContinueHacking(
    Experiment * experiment,
    PolicyChain & pchain
)
```

This will be used by `letTheHackBegin` and uses the decision policy to decide whether the next hacking strategy is going to be executed ! 

**Parameters**: 

  * **experiment** A reference to the experiment 

























**Reimplemented by**: [sam::DefaultDecisionMaker::willContinueHacking](/doxygen/Classes/classsam_1_1_default_decision_maker/#function-willcontinuehacking)




### function willBeSubmitting

```cpp
bool willBeSubmitting(
    const std::optional< Submission > & sub,
    PolicyChain & pchain
)
```

[Submission](). 




























### function willContinueReplicating

```cpp
inline virtual bool willContinueReplicating(
    PolicyChain & pchain
)
```


























**Reimplemented by**: [sam::DefaultDecisionMaker::willContinueReplicating](/doxygen/Classes/classsam_1_1_default_decision_maker/#function-willcontinuereplicating)




### function clear

```cpp
inline void clear()
```



























Clear the contents of the decision strategy, this include the submission pools or other collected information by the decision strategy. 


### function reset

```cpp
inline void reset()
```
















**Todo**: : This needs to be private but currently, I don't have a good place to put it. The verdict system is broken, and if reset it after the selectionBetweenSubmission, it's werid and I cannot just call it in any other methods because then it's hidden













Reset the internal state of the decision strategy 


### function selectOutcomeFromExperiment

```cpp
virtual DecisionStrategy & selectOutcomeFromExperiment(
    Experiment * experiment,
    PolicyChainSet & pchain_set
) =0
```

Implementation of decision-making procedure. 

























**Reimplemented by**: [sam::DefaultDecisionMaker::selectOutcomeFromExperiment](/doxygen/Classes/classsam_1_1_default_decision_maker/#function-selectoutcomefromexperiment)




### function selectOutcomeFromPool

```cpp
virtual DecisionStrategy & selectOutcomeFromPool(
    SubmissionPool & spool,
    PolicyChainSet & pchain_set
) =0
```


























**Reimplemented by**: [sam::DefaultDecisionMaker::selectOutcomeFromPool](/doxygen/Classes/classsam_1_1_default_decision_maker/#function-selectoutcomefrompool)




### function saveEveryOutcome

```cpp
inline void saveEveryOutcome(
    Experiment & experiment
)
```





























### function saveOutcomes

```cpp
void saveOutcomes(
    Experiment & experiment,
    PolicyChain & pchain
)
```


**Parameters**: 

  * **experiment** a reference to the experiment 
  * **pchain** a policy chain, usually stored in `stashing_policy` in the config file
  * **experiment** a reference to the experiment 
  * **pchain** a policy chain, usually stored in `stashing_policy` in the config file 


























Create and save all possible submissions from an experiment, if they pass the given policy predicate


Create and save all possible submissions from an experiment, if the satisfy all of the given policies in the pchain.


### function build

```cpp
static std::unique_ptr< DecisionStrategy > build(
    json & decision_strategy_config
)
```


**Parameters**: 

  * **decision_strategy_config** A JSON object containing information about each decision strategy. 


























[DecisionStrategy](/doxygen/Classes/classsam_1_1_decision_strategy/) factory method.



## Protected Functions Documentation

### function saveCurrentSubmissionCandidate

```cpp
inline void saveCurrentSubmissionCandidate()
```



























A helper method to save the current submission. This needs to be called after verdict. 


### function selectOutcome

```cpp
void selectOutcome(
    Experiment & experiment,
    PolicyChainSet & pchain_set
)
```


**Parameters**: 

  * **experiment** a reference to an experiment 
  * **pchain_set** a reference to a policy chain set 


























Select an unique outcome from an experiment, if at some point, a [PolicyChain](/doxygen/Classes/structsam_1_1_policy_chain/) finds a group of outcomes instread of a unique outcome, the selection will be saved and the will await for processing in a different stages.

We check all available PolicyChains in the given chain set, and will stop as soon as any chain returns **something**!

TodoI probably should check this somewhere else, and don't throw here! 

If we find many, we just collect them, and quit update: I think this is actually an incorrect behavior. I think I was confusing this with stashing! I think I designed pchain operator to be able to return more than one outcome but didn't test for it

### function selectBetweenSubmissions

```cpp
void selectBetweenSubmissions(
    SubmissionPool & spool,
    PolicyChainSet & pchain_set
)
```


**Parameters**: 

  * **spool** a collection of submissions collected in previous stages, e.g., selectOutcome 
  * **pchain_set** a set of policy chains 












!!! note "Note"
    If submission_candidate is empty to this point, and we cannot find anything here, we'll continue with nothing, and the current experiment will most likely be discarded.














Select a unique submission from the given pool of submissions. If none of the submissions satisfies all the policies, we just return, and submission_candidate will not be rewritten.

TodoCheck what this actually means! 

TodoThis is the same issue as it was in selectOutcome, if I return here, I'll not go through the rest of then chain 


## Public Attributes Documentation

### variable lua

```cpp
sol::state lua;
```





























### variable config_

```cpp
json config_;
```





























### variable submission_candidate

```cpp
std::optional< Submission > submission_candidate;
```





























### variable submissions_pool

```cpp
SubmissionPool submissions_pool;
```

List of selected [Submission]() by the researcher, during the hacking procedure. 




























### variable initial_selection_policies

```cpp
PolicyChainSet initial_selection_policies;
```
















**Todo**: : These guys should move to their own class, I don't have to keep everything here! 













### variable submission_decision_policies

```cpp
PolicyChain submission_decision_policies;
```





























### variable between_hacks_selection_policies

```cpp
PolicyChainSet between_hacks_selection_policies;
```





























### variable between_reps_policies

```cpp
PolicyChainSet between_reps_policies;
```





























### variable will_start_hacking_decision_policies

```cpp
PolicyChain will_start_hacking_decision_policies;
```





























### variable will_continue_replicating_decision_policy

```cpp
PolicyChain will_continue_replicating_decision_policy;
```





























### variable stashing_policy

```cpp
PolicyChain stashing_policy;
```

































-------------------------------

Updated on  7 December 2020 at 13:20:07 CET