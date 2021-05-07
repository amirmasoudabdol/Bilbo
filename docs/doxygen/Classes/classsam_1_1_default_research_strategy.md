---
title: sam::DefaultResearchStrategy
summary: The deceleration of the default research strategy. 

---

# sam::DefaultResearchStrategy

**Module:** **[Research Strategies](/doxygen/Modules/group___research_strategies/)**



The deceleration of the default research strategy.  [More...](#detailed-description)


`#include <ResearchStrategy.h>`

Inherits from [sam::ResearchStrategy](/doxygen/Classes/classsam_1_1_research_strategy/)

## Public Classes

|                | Name           |
| -------------- | -------------- |
| struct | **[Parameters](/doxygen/Classes/structsam_1_1_default_research_strategy_1_1_parameters/)** <br>The parameters of the strategy.  |

## Public Functions

|                | Name           |
| -------------- | -------------- |
| | **[DefaultResearchStrategy](/doxygen/Classes/classsam_1_1_default_research_strategy/#function-defaultresearchstrategy)**(const [Parameters](/doxygen/Classes/structsam_1_1_default_research_strategy_1_1_parameters/) & p) |
| virtual std::optional< SubmissionPool > | **[selectOutcomeFromExperiment](/doxygen/Classes/classsam_1_1_default_research_strategy/#function-selectoutcomefromexperiment)**([Experiment](/doxygen/Classes/classsam_1_1_experiment/) * experiment, [PolicyChainSet](/doxygen/Classes/structsam_1_1_policy_chain_set/) & pchain_set) override<br>Returns the result of applying the policy chain set on the [Experiment](/doxygen/Classes/classsam_1_1_experiment/).  |
| virtual std::optional< SubmissionPool > | **[selectOutcomeFromPool](/doxygen/Classes/classsam_1_1_default_research_strategy/#function-selectoutcomefrompool)**(SubmissionPool & spool, [PolicyChainSet](/doxygen/Classes/structsam_1_1_policy_chain_set/) & pchain_set) override |
| virtual bool | **[willStartHacking](/doxygen/Classes/classsam_1_1_default_research_strategy/#function-willstarthacking)**(std::optional< SubmissionPool > & subs) override |
| virtual bool | **[willContinueHacking](/doxygen/Classes/classsam_1_1_default_research_strategy/#function-willcontinuehacking)**([Experiment](/doxygen/Classes/classsam_1_1_experiment/) * experiment, [PolicyChain](/doxygen/Classes/structsam_1_1_policy_chain/) & pchain) override<br>Determines whether or not the researcher is going to continue hacking.  |
| virtual bool | **[willContinueHacking](/doxygen/Classes/classsam_1_1_default_research_strategy/#function-willcontinuehacking)**(std::optional< SubmissionPool > & subs, [PolicyChain](/doxygen/Classes/structsam_1_1_policy_chain/) & pchain) override<br>Determines whether or not the researcher is going to continue hacking.  |
| virtual bool | **[willContinueReplicating](/doxygen/Classes/classsam_1_1_default_research_strategy/#function-willcontinuereplicating)**(SubmissionPool & subs) override<br>Determines whether or not the replication procedure is going to place.  |

## Public Attributes

|                | Name           |
| -------------- | -------------- |
| [Parameters](/doxygen/Classes/structsam_1_1_default_research_strategy_1_1_parameters/) | **[params](/doxygen/Classes/classsam_1_1_default_research_strategy/#variable-params)**  |

## Additional inherited members

**Public Functions inherited from [sam::ResearchStrategy](/doxygen/Classes/classsam_1_1_research_strategy/)**

|                | Name           |
| -------------- | -------------- |
| virtual | **[~ResearchStrategy](/doxygen/Classes/classsam_1_1_research_strategy/#function-~researchstrategy)**() =0 |
| | **[ResearchStrategy](/doxygen/Classes/classsam_1_1_research_strategy/#function-researchstrategy)**() |
| bool | **[willBeSubmitting](/doxygen/Classes/classsam_1_1_research_strategy/#function-willbesubmitting)**(const std::optional< SubmissionPool > & sub, [PolicyChain](/doxygen/Classes/structsam_1_1_policy_chain/) & pchain) |
| void | **[reset](/doxygen/Classes/classsam_1_1_research_strategy/#function-reset)**()<br>Resets the internal state of the research strategy.  |
| std::optional< SubmissionPool > | **[stashedSubmissions](/doxygen/Classes/classsam_1_1_research_strategy/#function-stashedsubmissions)**()<br>Returns a copy of the [stashed_submissions](/doxygen/Classes/classsam_1_1_research_strategy/#variable-stashed_submissions).  |
| void | **[saveOutcomes](/doxygen/Classes/classsam_1_1_research_strategy/#function-saveoutcomes)**([Experiment](/doxygen/Classes/classsam_1_1_experiment/) & experiment, [PolicyChain](/doxygen/Classes/structsam_1_1_policy_chain/) & pchain) |
| std::optional< SubmissionPool > | **[selectOutcome](/doxygen/Classes/classsam_1_1_research_strategy/#function-selectoutcome)**([Experiment](/doxygen/Classes/classsam_1_1_experiment/) & experiment, [PolicyChainSet](/doxygen/Classes/structsam_1_1_policy_chain_set/) & pchain_set)<br>Returns the result of applying the [PolicyChainSet](/doxygen/Classes/structsam_1_1_policy_chain_set/) on the [Experiment](/doxygen/Classes/classsam_1_1_experiment/).  |
| std::optional< SubmissionPool > | **[selectBetweenSubmissions](/doxygen/Classes/classsam_1_1_research_strategy/#function-selectbetweensubmissions)**(SubmissionPool & spool, [PolicyChainSet](/doxygen/Classes/structsam_1_1_policy_chain_set/) & pchain_set)<br>Returns the result of applying the [PolicyChainSet](/doxygen/Classes/structsam_1_1_policy_chain_set/) on the submission pool.  |
| std::unique_ptr< [ResearchStrategy](/doxygen/Classes/classsam_1_1_research_strategy/) > | **[build](/doxygen/Classes/classsam_1_1_research_strategy/#function-build)**(json & research_strategy_config)<br>[ResearchStrategy](/doxygen/Classes/classsam_1_1_research_strategy/) factory method.  |

**Public Attributes inherited from [sam::ResearchStrategy](/doxygen/Classes/classsam_1_1_research_strategy/)**

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

**Protected Attributes inherited from [sam::ResearchStrategy](/doxygen/Classes/classsam_1_1_research_strategy/)**

|                | Name           |
| -------------- | -------------- |
| std::optional< SubmissionPool > | **[submission_candidates](/doxygen/Classes/classsam_1_1_research_strategy/#variable-submission_candidates)**  |
| SubmissionPool | **[stashed_submissions](/doxygen/Classes/classsam_1_1_research_strategy/#variable-stashed_submissions)**  |


## Detailed Description

```cpp
class sam::DefaultResearchStrategy;
```

The deceleration of the default research strategy. 

**See**: [Researcher::research()](/doxygen/Classes/classsam_1_1_researcher/#function-research)

**Note**: [Researcher](/doxygen/Classes/classsam_1_1_researcher/) is in charge of research strategy and it executes its command personally.



```
        The default research strategy is the only available strategy at
        the moment. It is designed to use all the policies explicitly
        and do not intervene with the given logic. Therefore, it has a
        very linear flow.
```

## Public Functions Documentation

### function DefaultResearchStrategy

```cpp
inline explicit DefaultResearchStrategy(
    const Parameters & p
)
```


### function selectOutcomeFromExperiment

```cpp
virtual std::optional< SubmissionPool > selectOutcomeFromExperiment(
    Experiment * experiment,
    PolicyChainSet & pchain_set
) override
```

Returns the result of applying the policy chain set on the [Experiment](/doxygen/Classes/classsam_1_1_experiment/). 

**Parameters**: 

  * **experiment** The experiment 
  * **pchain_set** The policy chain set


**Return**: Returns a list of submissions, if any. 

**Reimplements**: [sam::ResearchStrategy::selectOutcomeFromExperiment](/doxygen/Classes/classsam_1_1_research_strategy/#function-selectoutcomefromexperiment)


If necessasry (ie., if stashing_policy is specified), it stashes some submissions from the experiment and also it returns the result of applying policy chain set on the experiment, if any.


TodoCheck if you can implement this a bit nicer 


### function selectOutcomeFromPool

```cpp
virtual std::optional< SubmissionPool > selectOutcomeFromPool(
    SubmissionPool & spool,
    PolicyChainSet & pchain_set
) override
```


**Parameters**: 

  * **spool** The submission pool 
  * **pchain_set** The policy chain set


**Return**: Returns a list of submissions, if any. 

**Reimplements**: [sam::ResearchStrategy::selectOutcomeFromPool](/doxygen/Classes/classsam_1_1_research_strategy/#function-selectoutcomefrompool)


Returns the results of applying the policy chain set on the list of submissions


### function willStartHacking

```cpp
virtual bool willStartHacking(
    std::optional< SubmissionPool > & subs
) override
```


**Parameters**: 

  * **subs** A list of submission candidates


**Return**: Returns true if the researcher has to proceed with the hacking strategies. 

**Note**: Basically, if _at least_ one of the submissions satisfy all of the criteria, the researcher will not commit to the hacking.

**Reimplements**: [sam::ResearchStrategy::willStartHacking](/doxygen/Classes/classsam_1_1_research_strategy/#function-willstarthacking)


Determines whether or not the researcher is going to starting the hacking / procedure

In this case, researcher checks if the list of current submissions complies with `will_not_start_hacking_decision_policies`; if so, it will NOT start hacking; otherwise, it WILL start the hacking procedure, and proceed to either stashing or replicating.


### function willContinueHacking

```cpp
virtual bool willContinueHacking(
    Experiment * experiment,
    PolicyChain & pchain
) override
```

Determines whether or not the researcher is going to continue hacking. 

**Parameters**: 

  * **pchain** a reference to the given policy chain


**Return**: Retruns `true` is the researcher should proceed with the next hacking strategy 

**Reimplements**: [sam::ResearchStrategy::willContinueHacking](/doxygen/Classes/classsam_1_1_research_strategy/#function-willcontinuehacking)


Similar to the [willStartHacking()](/doxygen/Classes/classsam_1_1_default_research_strategy/#function-willstarthacking) checks whether any of the dependent variables are satisfying all `pchain` policies.


### function willContinueHacking

```cpp
virtual bool willContinueHacking(
    std::optional< SubmissionPool > & subs,
    PolicyChain & pchain
) override
```

Determines whether or not the researcher is going to continue hacking. 

**Parameters**: 

  * **subs** The list of submissions, if any 
  * **pchain** The policy chain


**Return**: Retruns `true` if the researcher should proceed with the next hacking strategy 

**Reimplements**: [sam::ResearchStrategy::willContinueHacking](/doxygen/Classes/classsam_1_1_research_strategy/#function-willcontinuehacking)


Overload of the [willContinueHacking()](/doxygen/Classes/classsam_1_1_default_research_strategy/#function-willcontinuehacking) that operates on a list of submissions instead of an experiment.


### function willContinueReplicating

```cpp
virtual bool willContinueReplicating(
    SubmissionPool & subs
) override
```

Determines whether or not the replication procedure is going to place. 

**Parameters**: 

  * **subs** A list of submission candidates


**Return**: Retruns true if the researcher has to continue the replication procedure 

**Reimplements**: [sam::ResearchStrategy::willContinueReplicating](/doxygen/Classes/classsam_1_1_research_strategy/#function-willcontinuereplicating)


Similar to the [willContinueHacking()](/doxygen/Classes/classsam_1_1_default_research_strategy/#function-willcontinuehacking), but uses `will_not_continue_replicating_decision_policy` instead.


## Public Attributes Documentation

### variable params

```cpp
Parameters params;
```


-------------------------------

Updated on  7 May 2021 at 14:51:32 CEST