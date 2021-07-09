---
title: Policy-related Modules
summary: List of available policy-related modules. 

---

# Policy-related Modules

List of available policy-related modules. ## Classes

|                | Name           |
| -------------- | -------------- |
| struct | **[sam::Policy](/doxygen/Classes/structsam_1_1_policy/)** <br>Implementation of the [Policy]() class.  |
| struct | **[sam::PolicyChain](/doxygen/Classes/structsam_1_1_policy_chain/)** <br>Implementation of the [PolicyChain]() class.  |
| struct | **[sam::PolicyChainSet](/doxygen/Classes/structsam_1_1_policy_chain_set/)**  |

## Types

|                | Name           |
| -------------- | -------------- |
| enum int | **[PolicyType](/doxygen/Modules/group___policies/#enum-policytype)** { Min, Max, Comp, Random, First, Last, All}<br>Indicates the type of the [Policy](/doxygen/Classes/structsam_1_1_policy/).  |
| enum int | **[PolicyChainType](/doxygen/Modules/group___policies/#enum-policychaintype)** { Selection, Decision}<br>Indicates the type of the [PolicyChain](/doxygen/Classes/structsam_1_1_policy_chain/).  |
| using std::vector< std::vector< std::variant< std::shared_ptr< HackingStrategy >, PolicyChain, PolicyChainSet > >> | **[HackingWorkflow](/doxygen/Modules/group___policies/#using-hackingworkflow)**  |

## Types Documentation

### enum PolicyType

| Enumerator | Value | Description |
| ---------- | ----- | ----------- |
| Min | |   |
| Max | |   |
| Comp | |   |
| Random | |   |
| First | |   |
| Last | |   |
| All | |   |



Indicates the type of the [Policy](/doxygen/Classes/structsam_1_1_policy/). 

This is mainly being used by [Policy](/doxygen/Classes/structsam_1_1_policy/) to decide which type of formula it's dealing with. 


### enum PolicyChainType

| Enumerator | Value | Description |
| ---------- | ----- | ----------- |
| Selection | |   |
| Decision | |   |



Indicates the type of the [PolicyChain](/doxygen/Classes/structsam_1_1_policy_chain/). 

A [PolicyChain](/doxygen/Classes/structsam_1_1_policy_chain/) can either be used to perform _selection_, or a _decision_. The main difference between them being that the `::Selection` chains could include a function call, e.g., `min`, while the `::Decision` chains cannot. 


### using HackingWorkflow

```cpp
using sam::HackingWorkflow = typedef std::vector< std::vector< std::variant<std::shared_ptr<HackingStrategy>, PolicyChain, PolicyChainSet> >>;
```


**See**: [Researcher::hackTheResearch()](/doxygen/Classes/classsam_1_1_researcher/#function-hacktheresearch)

The representation of the Hacking Workflow

This is defined to capture a sequence of _hacking → selection → decision_. While it looks rather strange, it allows for some nice and flexible setup using the std::visit().







-------------------------------

Updated on 29 June 2021 at 16:13:48 CEST