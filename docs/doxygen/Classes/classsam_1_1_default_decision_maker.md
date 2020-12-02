---
title: sam::DefaultDecisionMaker


---

# sam::DefaultDecisionMaker


**Module:** **[Decision Strategies](/doxygen/Modules/group___decision_strategies/)**





Inherits from [sam::DecisionStrategy](/doxygen/Classes/classsam_1_1_decision_strategy/)



## Public Classes

|                | Name           |
| -------------- | -------------- |
| struct | **[Parameters](/doxygen/Classes/structsam_1_1_default_decision_maker_1_1_parameters/)**  |








## Public Functions

|                | Name           |
| -------------- | -------------- |
|  | **[DefaultDecisionMaker](/doxygen/Classes/classsam_1_1_default_decision_maker/#function-defaultdecisionmaker)**(const [Parameters](/doxygen/Classes/structsam_1_1_default_decision_maker_1_1_parameters/) & p)  |
| virtual [DecisionStrategy](/doxygen/Classes/classsam_1_1_decision_strategy/) & | **[selectOutcomeFromExperiment](/doxygen/Classes/classsam_1_1_default_decision_maker/#function-selectoutcomefromexperiment)**([Experiment](/doxygen/Classes/classsam_1_1_experiment/) * experiment, [PolicyChainSet](/doxygen/Classes/structsam_1_1_policy_chain_set/) & pchain_set) override <br>Implementation of decision-making procedure.  |
| virtual [DecisionStrategy](/doxygen/Classes/classsam_1_1_decision_strategy/) & | **[selectOutcomeFromPool](/doxygen/Classes/classsam_1_1_default_decision_maker/#function-selectoutcomefrompool)**(SubmissionPool & spool, [PolicyChainSet](/doxygen/Classes/structsam_1_1_policy_chain_set/) & pchain_set) override  |
| virtual bool | **[willStartHacking](/doxygen/Classes/classsam_1_1_default_decision_maker/#function-willstarthacking)**() override <br>Decides whether we are going to start hacking. In this canse, we only check if the `current_submission` complies with `will_start_hacking_decision_policies` roles; if yes, we will start hacking if no, then we will not continue to the hacking procedure.  |
| virtual bool | **[willContinueHacking](/doxygen/Classes/classsam_1_1_default_decision_maker/#function-willcontinuehacking)**([Experiment](/doxygen/Classes/classsam_1_1_experiment/) * experiment, [PolicyChain](/doxygen/Classes/structsam_1_1_policy_chain/) & pchain) override  |
| virtual bool | **[willContinueReplicating](/doxygen/Classes/classsam_1_1_default_decision_maker/#function-willcontinuereplicating)**([PolicyChain](/doxygen/Classes/structsam_1_1_policy_chain/) & pchain) override  |


## Public Attributes

|                | Name           |
| -------------- | -------------- |
| [Parameters](/doxygen/Classes/structsam_1_1_default_decision_maker_1_1_parameters/) | **[params](/doxygen/Classes/classsam_1_1_default_decision_maker/#variable-params)**  |




## Additional inherited members










**Public Functions inherited from [sam::DecisionStrategy](/doxygen/Classes/classsam_1_1_decision_strategy/)**

|                | Name           |
| -------------- | -------------- |
| virtual  | **[~DecisionStrategy](/doxygen/Classes/classsam_1_1_decision_strategy/#function-~decisionstrategy)**() =0  |
|  | **[DecisionStrategy](/doxygen/Classes/classsam_1_1_decision_strategy/#function-decisionstrategy)**()  |
| bool | **[willBeSubmitting](/doxygen/Classes/classsam_1_1_decision_strategy/#function-willbesubmitting)**(const std::optional< [Submission](/doxygen/Classes/classsam_1_1_submission/) > & sub, [PolicyChain](/doxygen/Classes/structsam_1_1_policy_chain/) & pchain) <br>[Submission]().  |
| void | **[clear](/doxygen/Classes/classsam_1_1_decision_strategy/#function-clear)**()  |
| void | **[reset](/doxygen/Classes/classsam_1_1_decision_strategy/#function-reset)**()  |
| void | **[saveEveryOutcome](/doxygen/Classes/classsam_1_1_decision_strategy/#function-saveeveryoutcome)**([Experiment](/doxygen/Classes/classsam_1_1_experiment/) & experiment)  |
| void | **[saveOutcomes](/doxygen/Classes/classsam_1_1_decision_strategy/#function-saveoutcomes)**([Experiment](/doxygen/Classes/classsam_1_1_experiment/) & experiment, [PolicyChain](/doxygen/Classes/structsam_1_1_policy_chain/) & pchain)  |
| std::unique_ptr< [DecisionStrategy](/doxygen/Classes/classsam_1_1_decision_strategy/) > | **[build](/doxygen/Classes/classsam_1_1_decision_strategy/#function-build)**(json & decision_strategy_config)  |

**Protected Functions inherited from [sam::DecisionStrategy](/doxygen/Classes/classsam_1_1_decision_strategy/)**

|                | Name           |
| -------------- | -------------- |
| void | **[saveCurrentSubmissionCandidate](/doxygen/Classes/classsam_1_1_decision_strategy/#function-savecurrentsubmissioncandidate)**()  |
| void | **[selectOutcome](/doxygen/Classes/classsam_1_1_decision_strategy/#function-selectoutcome)**([Experiment](/doxygen/Classes/classsam_1_1_experiment/) & experiment, [PolicyChainSet](/doxygen/Classes/structsam_1_1_policy_chain_set/) & pchain_set)  |
| void | **[selectBetweenSubmissions](/doxygen/Classes/classsam_1_1_decision_strategy/#function-selectbetweensubmissions)**(SubmissionPool & spool, [PolicyChainSet](/doxygen/Classes/structsam_1_1_policy_chain_set/) & pchain_set)  |

**Public Attributes inherited from [sam::DecisionStrategy](/doxygen/Classes/classsam_1_1_decision_strategy/)**

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

### function DefaultDecisionMaker

```cpp
inline explicit DefaultDecisionMaker(
    const Parameters & p
)
```





























### function selectOutcomeFromExperiment

```cpp
virtual DecisionStrategy & selectOutcomeFromExperiment(
    Experiment * experiment,
    PolicyChainSet & pchain_set
) override
```

Implementation of decision-making procedure. 

























**Reimplements**: [sam::DecisionStrategy::selectOutcomeFromExperiment](/doxygen/Classes/classsam_1_1_decision_strategy/#function-selectoutcomefromexperiment)




### function selectOutcomeFromPool

```cpp
virtual DecisionStrategy & selectOutcomeFromPool(
    SubmissionPool & spool,
    PolicyChainSet & pchain_set
) override
```


























**Reimplements**: [sam::DecisionStrategy::selectOutcomeFromPool](/doxygen/Classes/classsam_1_1_decision_strategy/#function-selectoutcomefrompool)




### function willStartHacking

```cpp
virtual bool willStartHacking() override
```

Decides whether we are going to start hacking. In this canse, we only check if the `current_submission` complies with `will_start_hacking_decision_policies` roles; if yes, we will start hacking if no, then we will not continue to the hacking procedure. 

























**Reimplements**: [sam::DecisionStrategy::willStartHacking](/doxygen/Classes/classsam_1_1_decision_strategy/#function-willstarthacking)



Todothis can be replaced by Policy->oprator() 

### function willContinueHacking

```cpp
virtual bool willContinueHacking(
    Experiment * experiment,
    PolicyChain & pchain
) override
```


**Parameters**: 

  * **pchain** a reference to the given policy chain 












**Note**: The important difference between this and `willBeSubmitting` is the fact that, the latter will check if **all** of the rules are passing.



**Todo**: This probably needs to be replaced by something inside the [PolicyChain](/doxygen/Classes/structsam_1_1_policy_chain/)










**Reimplements**: [sam::DecisionStrategy::willContinueHacking](/doxygen/Classes/classsam_1_1_decision_strategy/#function-willcontinuehacking)


Determines whether the `final_submission_candidates` complies with **any** of the given policies.


### function willContinueReplicating

```cpp
virtual bool willContinueReplicating(
    PolicyChain & pchain
) override
```


























**Reimplements**: [sam::DecisionStrategy::willContinueReplicating](/doxygen/Classes/classsam_1_1_decision_strategy/#function-willcontinuereplicating)






## Public Attributes Documentation

### variable params

```cpp
Parameters params;
```

































-------------------------------

Updated on 23 November 2020 at 14:03:44 CET