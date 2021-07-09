---
title: sam::ResearchStrategy
summary: Abstract class for different research strategies. 

---

# sam::ResearchStrategy



Abstract class for different research strategies.  [More...](#detailed-description)


`#include <ResearchStrategy.h>`

Inherited by [sam::DefaultResearchStrategy](/doxygen/Classes/classsam_1_1_default_research_strategy/)

## Public Functions

|                | Name           |
| -------------- | -------------- |
| virtual | **[~ResearchStrategy](/doxygen/Classes/classsam_1_1_research_strategy/#function-~researchstrategy)**() =0 |
| | **[ResearchStrategy](/doxygen/Classes/classsam_1_1_research_strategy/#function-researchstrategy)**() |
| virtual bool | **[willStartHacking](/doxygen/Classes/classsam_1_1_research_strategy/#function-willstarthacking)**(std::optional< SubmissionPool > & subs)<br>Indicates whether the researcher will start going to the hacking procedure.  |
| virtual bool | **[willContinueHacking](/doxygen/Classes/classsam_1_1_research_strategy/#function-willcontinuehacking)**([Experiment](/doxygen/Classes/classsam_1_1_experiment/) * experiment, [PolicyChain](/doxygen/Classes/structsam_1_1_policy_chain/) & pchain)<br>Indicates whether the researcher will continue the hacking procedure.  |
| virtual bool | **[willContinueHacking](/doxygen/Classes/classsam_1_1_research_strategy/#function-willcontinuehacking)**(std::optional< SubmissionPool > & sub, [PolicyChain](/doxygen/Classes/structsam_1_1_policy_chain/) & pchain) |
| bool | **[willBeSubmitting](/doxygen/Classes/classsam_1_1_research_strategy/#function-willbesubmitting)**(const std::optional< SubmissionPool > & sub, [PolicyChain](/doxygen/Classes/structsam_1_1_policy_chain/) & pchain) |
| virtual bool | **[willContinueReplicating](/doxygen/Classes/classsam_1_1_research_strategy/#function-willcontinuereplicating)**(SubmissionPool & subs)<br>Decides whether the researcher is going to continue the replication process or not.  |
| void | **[reset](/doxygen/Classes/classsam_1_1_research_strategy/#function-reset)**()<br>Resets the internal state of the research strategy.  |
| std::optional< SubmissionPool > | **[stashedSubmissions](/doxygen/Classes/classsam_1_1_research_strategy/#function-stashedsubmissions)**()<br>Returns a copy of the [stashed_submissions](/doxygen/Classes/classsam_1_1_research_strategy/#variable-stashed_submissions).  |
| virtual std::optional< SubmissionPool > | **[selectOutcomeFromExperiment](/doxygen/Classes/classsam_1_1_research_strategy/#function-selectoutcomefromexperiment)**([Experiment](/doxygen/Classes/classsam_1_1_experiment/) * experiment, [PolicyChainSet](/doxygen/Classes/structsam_1_1_policy_chain_set/) & pchain_set) =0<br>Returns an optional result of applying the [PolicyChainSet](/doxygen/Classes/structsam_1_1_policy_chain_set/) on the given [Experiment](/doxygen/Classes/classsam_1_1_experiment/).  |
| virtual std::optional< SubmissionPool > | **[selectOutcomeFromPool](/doxygen/Classes/classsam_1_1_research_strategy/#function-selectoutcomefrompool)**(SubmissionPool & spool, [PolicyChainSet](/doxygen/Classes/structsam_1_1_policy_chain_set/) & pchain_set) =0<br>Returns an optional result of applying the [PolicyChainSet](/doxygen/Classes/structsam_1_1_policy_chain_set/) on the given list of submissions.  |
| void | **[saveOutcomes](/doxygen/Classes/classsam_1_1_research_strategy/#function-saveoutcomes)**([Experiment](/doxygen/Classes/classsam_1_1_experiment/) & experiment, [PolicyChain](/doxygen/Classes/structsam_1_1_policy_chain/) & pchain) |
| std::optional< SubmissionPool > | **[selectOutcome](/doxygen/Classes/classsam_1_1_research_strategy/#function-selectoutcome)**([Experiment](/doxygen/Classes/classsam_1_1_experiment/) & experiment, [PolicyChainSet](/doxygen/Classes/structsam_1_1_policy_chain_set/) & pchain_set)<br>Returns the result of applying the [PolicyChainSet](/doxygen/Classes/structsam_1_1_policy_chain_set/) on the [Experiment](/doxygen/Classes/classsam_1_1_experiment/).  |
| std::optional< SubmissionPool > | **[selectBetweenSubmissions](/doxygen/Classes/classsam_1_1_research_strategy/#function-selectbetweensubmissions)**(SubmissionPool & spool, [PolicyChainSet](/doxygen/Classes/structsam_1_1_policy_chain_set/) & pchain_set)<br>Returns the result of applying the [PolicyChainSet](/doxygen/Classes/structsam_1_1_policy_chain_set/) on the submission pool.  |
| std::unique_ptr< [ResearchStrategy](/doxygen/Classes/classsam_1_1_research_strategy/) > | **[build](/doxygen/Classes/classsam_1_1_research_strategy/#function-build)**(json & research_strategy_config)<br>[ResearchStrategy](/doxygen/Classes/classsam_1_1_research_strategy/) factory method.  |

## Public Attributes

|                | Name           |
| -------------- | -------------- |
| sol::state | **[lua](/doxygen/Classes/classsam_1_1_research_strategy/#variable-lua)**  |
| [PolicyChainSet](/doxygen/Classes/structsam_1_1_policy_chain_set/) | **[initial_selection_policies](/doxygen/Classes/classsam_1_1_research_strategy/#variable-initial_selection_policies)**  |
| [PolicyChain](/doxygen/Classes/structsam_1_1_policy_chain/) | **[submission_decision_policies](/doxygen/Classes/classsam_1_1_research_strategy/#variable-submission_decision_policies)**  |
| [PolicyChainSet](/doxygen/Classes/structsam_1_1_policy_chain_set/) | **[between_stashed_selection_policies](/doxygen/Classes/classsam_1_1_research_strategy/#variable-between_stashed_selection_policies)**  |
| [PolicyChainSet](/doxygen/Classes/structsam_1_1_policy_chain_set/) | **[between_reps_policies](/doxygen/Classes/classsam_1_1_research_strategy/#variable-between_reps_policies)**  |
| [PolicyChain](/doxygen/Classes/structsam_1_1_policy_chain/) | **[will_not_start_hacking_decision_policies](/doxygen/Classes/classsam_1_1_research_strategy/#variable-will_not_start_hacking_decision_policies)**  |
| [PolicyChain](/doxygen/Classes/structsam_1_1_policy_chain/) | **[will_not_continue_replicating_decision_policy](/doxygen/Classes/classsam_1_1_research_strategy/#variable-will_not_continue_replicating_decision_policy)**  |
| [PolicyChain](/doxygen/Classes/structsam_1_1_policy_chain/) | **[stashing_policy](/doxygen/Classes/classsam_1_1_research_strategy/#variable-stashing_policy)**  |

## Protected Attributes

|                | Name           |
| -------------- | -------------- |
| std::optional< SubmissionPool > | **[submission_candidates](/doxygen/Classes/classsam_1_1_research_strategy/#variable-submission_candidates)**  |
| SubmissionPool | **[stashed_submissions](/doxygen/Classes/classsam_1_1_research_strategy/#variable-stashed_submissions)**  |

## Detailed Description

```cpp
class sam::ResearchStrategy;
```

Abstract class for different research strategies. 

**Note**: This is being implemented as abstract class due to historical reasons. There is only one research strategy at the moment, but I'm considering the possibility of adding more and maybe redesigning this again. 
## Public Functions Documentation

### function ~ResearchStrategy

```cpp
virtual ~ResearchStrategy() =0
```


Pure destructors of [ResearchStrategy](/doxygen/Classes/classsam_1_1_research_strategy/). This is necessary for proper deconstruction of derived classes. 


### function ResearchStrategy

```cpp
ResearchStrategy()
```


Besides constructing the base class, it also registers the [Submission](/doxygen/Classes/classsam_1_1_submission/) and [DependentVariable](/doxygen/Classes/classsam_1_1_dependent_variable/) in Lua for later use of the derived classes, e.g., [DefaultResearchStrategy](/doxygen/Classes/classsam_1_1_default_research_strategy/)


### function willStartHacking

```cpp
inline virtual bool willStartHacking(
    std::optional< SubmissionPool > & subs
)
```

Indicates whether the researcher will start going to the hacking procedure. 

**Parameters**: 

  * **subs** The subs


**Return**: Returns `true` if researcher is going to start the hacking procedure 

**Reimplemented by**: [sam::DefaultResearchStrategy::willStartHacking](/doxygen/Classes/classsam_1_1_default_research_strategy/#function-willstarthacking)


The default here is to not go for hacking if we already have one candidate; but this can be overridden in different research strategies


### function willContinueHacking

```cpp
inline virtual bool willContinueHacking(
    Experiment * experiment,
    PolicyChain & pchain
)
```

Indicates whether the researcher will continue the hacking procedure. 

**Parameters**: 

  * **experiment** A reference to the experiment 


**Reimplemented by**: [sam::DefaultResearchStrategy::willContinueHacking](/doxygen/Classes/classsam_1_1_default_research_strategy/#function-willcontinuehacking)


This will be used by `hackTheResearch` and uses the decision policy to decide whether the next hacking strategy is going to be executed !


### function willContinueHacking

```cpp
inline virtual bool willContinueHacking(
    std::optional< SubmissionPool > & sub,
    PolicyChain & pchain
)
```


**Reimplemented by**: [sam::DefaultResearchStrategy::willContinueHacking](/doxygen/Classes/classsam_1_1_default_research_strategy/#function-willcontinuehacking)


### function willBeSubmitting

```cpp
bool willBeSubmitting(
    const std::optional< SubmissionPool > & sub,
    PolicyChain & pchain
)
```


**Parameters**: 

  * **subs** A list of Submission(s) 
  * **pchain** A policy chain


**Return**: returns `true` if submission should be submitted to the [Journal](/doxygen/Classes/classsam_1_1_journal/). 

Indicates whether the [Researcher](/doxygen/Classes/classsam_1_1_researcher/) is going to submit the given set of submissions or not.

Usually `submission_decision_policies` will be used to evaluate the quality of the submission pool. This checks if _at least one_ of the submissions satisfy all of the given policies.


### function willContinueReplicating

```cpp
inline virtual bool willContinueReplicating(
    SubmissionPool & subs
)
```

Decides whether the researcher is going to continue the replication process or not. 

**Parameters**: 

  * **subs** A list of submissions


**Return**: Returns `true` if the replication procedure should continue 

**Reimplemented by**: [sam::DefaultResearchStrategy::willContinueReplicating](/doxygen/Classes/classsam_1_1_default_research_strategy/#function-willcontinuereplicating)


### function reset

```cpp
inline void reset()
```

Resets the internal state of the research strategy. 

### function stashedSubmissions

```cpp
inline std::optional< SubmissionPool > stashedSubmissions()
```

Returns a copy of the [stashed_submissions](/doxygen/Classes/classsam_1_1_research_strategy/#variable-stashed_submissions). 

**Return**: Returns an optional containing a copy of stashed_submissions 

**Todo**: this can be improved

### function selectOutcomeFromExperiment

```cpp
virtual std::optional< SubmissionPool > selectOutcomeFromExperiment(
    Experiment * experiment,
    PolicyChainSet & pchain_set
) =0
```

Returns an optional result of applying the [PolicyChainSet](/doxygen/Classes/structsam_1_1_policy_chain_set/) on the given [Experiment](/doxygen/Classes/classsam_1_1_experiment/). 

**Parameters**: 

  * **experiment** The experiment 
  * **pchain_set** The policy chain set


**Return**: Returns a list of submissions, if any. 

**Reimplemented by**: [sam::DefaultResearchStrategy::selectOutcomeFromExperiment](/doxygen/Classes/classsam_1_1_default_research_strategy/#function-selectoutcomefromexperiment)


### function selectOutcomeFromPool

```cpp
virtual std::optional< SubmissionPool > selectOutcomeFromPool(
    SubmissionPool & spool,
    PolicyChainSet & pchain_set
) =0
```

Returns an optional result of applying the [PolicyChainSet](/doxygen/Classes/structsam_1_1_policy_chain_set/) on the given list of submissions. 

**Parameters**: 

  * **spool** The submission pool 
  * **pchain_set** The policy chain set


**Return**: Returns a list of submissions, if any. 

**Reimplemented by**: [sam::DefaultResearchStrategy::selectOutcomeFromPool](/doxygen/Classes/classsam_1_1_default_research_strategy/#function-selectoutcomefrompool)


### function saveOutcomes

```cpp
void saveOutcomes(
    Experiment & experiment,
    PolicyChain & pchain
)
```


**Parameters**: 

  * **experiment** a reference to the experiment 
  * **pchain** a policy chain, usually #stashing_policy
  * **experiment** a reference to the experiment 
  * **pchain** a policy chain, usually stored in `stashing_policy` in the config file 


Creates and save all possible submissions from an experiment, if they pass the given policy predicate


Create and save all possible submissions from an experiment, if the satisfy all of the given policies in the pchain.


### function selectOutcome

```cpp
std::optional< SubmissionPool > selectOutcome(
    Experiment & experiment,
    PolicyChainSet & pchain_set
)
```

Returns the result of applying the [PolicyChainSet](/doxygen/Classes/structsam_1_1_policy_chain_set/) on the [Experiment](/doxygen/Classes/classsam_1_1_experiment/). 

**Parameters**: 

  * **experiment** The experiment 
  * **pchain_set** The policy chain set.
  * **experiment** a reference to an experiment 
  * **pchain_set** a reference to a policy chain set


**Return**: 

  * Returns a list of submissions, if any.
  * A list of submissions, if any. 



Select an unique outcome from an experiment, if at some point, a [PolicyChain](/doxygen/Classes/structsam_1_1_policy_chain/) finds a group of outcomes instead of a unique outcome, the selection will be saved and the will await for processing in a different stages.

We check all available PolicyChains in the given chain set, and will stop as soon as any chain returns **something**!


### function selectBetweenSubmissions

```cpp
std::optional< SubmissionPool > selectBetweenSubmissions(
    SubmissionPool & spool,
    PolicyChainSet & pchain_set
)
```

Returns the result of applying the [PolicyChainSet](/doxygen/Classes/structsam_1_1_policy_chain_set/) on the submission pool. 

**Parameters**: 

  * **spool** The spool 
  * **pchain_set** The policy chain set
  * **spool** a collection of submissions collected in previous stages, e.g., selectOutcome 
  * **pchain_set** a set of policy chains


**Return**: 

  * Returns a list of submissions, if any.
  * A list of submissions, if any. 


**Note**: If submission_candidate is empty to this point, and we cannot find anything here, we'll continue with nothing, and the current experiment will most likely be discarded.


Select a unique submission from the given pool of submissions. If none of the submissions satisfies all the policies, we just return, and submission_candidate will not be rewritten.


If any of the pchains return something, we ignore the rest, and leave!


### function build

```cpp
static std::unique_ptr< ResearchStrategy > build(
    json & research_strategy_config
)
```

[ResearchStrategy](/doxygen/Classes/classsam_1_1_research_strategy/) factory method. 

**Parameters**: 

  * **research_strategy_config** A JSON object containing information about each research strategy.


**Return**: Returns a unique pointer to the newly build [ResearchStrategy](/doxygen/Classes/classsam_1_1_research_strategy/). 

## Public Attributes Documentation

### variable lua

```cpp
sol::state lua;
```


### variable initial_selection_policies

```cpp
PolicyChainSet initial_selection_policies;
```


**Todo**: These guys should move to their own class, I don't have to keep everything here! 

### variable submission_decision_policies

```cpp
PolicyChain submission_decision_policies;
```


### variable between_stashed_selection_policies

```cpp
PolicyChainSet between_stashed_selection_policies;
```


### variable between_reps_policies

```cpp
PolicyChainSet between_reps_policies;
```


### variable will_not_start_hacking_decision_policies

```cpp
PolicyChain will_not_start_hacking_decision_policies;
```


### variable will_not_continue_replicating_decision_policy

```cpp
PolicyChain will_not_continue_replicating_decision_policy;
```


### variable stashing_policy

```cpp
PolicyChain stashing_policy;
```


## Protected Attributes Documentation

### variable submission_candidates

```cpp
std::optional< SubmissionPool > submission_candidates;
```


### variable stashed_submissions

```cpp
SubmissionPool stashed_submissions;
```


List of selected submissions collected by the researcher using the stashing_policy 


-------------------------------

Updated on 29 June 2021 at 16:13:46 CEST