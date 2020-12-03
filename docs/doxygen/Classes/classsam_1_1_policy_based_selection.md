---
title: sam::PolicyBasedSelection
summary: Policy-based Selection Strategy.  

---

# sam::PolicyBasedSelection


**Module:** **[Selection Strategies](/doxygen/Modules/group___selection_strategies/)**

Policy-based Selection Strategy.  [More...](#detailed-description)


`#include <SelectionStrategy.h>`


Inherits from SelectionStrategy



## Public Classes

|                | Name           |
| -------------- | -------------- |
| struct | **[Parameters](/doxygen/Classes/structsam_1_1_policy_based_selection_1_1_parameters/)**  |








## Public Functions

|                | Name           |
| -------------- | -------------- |
|  | **[PolicyBasedSelection](/doxygen/Classes/classsam_1_1_policy_based_selection/#function-policybasedselection)**([Parameters](/doxygen/Classes/structsam_1_1_policy_based_selection_1_1_parameters/) & p)  |
| virtual bool | **[review](/doxygen/Classes/classsam_1_1_policy_based_selection/#function-review)**(const [Submission](/doxygen/Classes/classsam_1_1_submission/) & s) override  |


## Public Attributes

|                | Name           |
| -------------- | -------------- |
| [Parameters](/doxygen/Classes/structsam_1_1_policy_based_selection_1_1_parameters/) | **[params](/doxygen/Classes/classsam_1_1_policy_based_selection/#variable-params)**  |
| [PolicyChain](/doxygen/Classes/structsam_1_1_policy_chain/) | **[selection_policy](/doxygen/Classes/classsam_1_1_policy_based_selection/#variable-selection_policy)**  |






## Detailed Description

```cpp
class sam::PolicyBasedSelection;
```

Policy-based Selection Strategy. 


























Policy-based selection strategy accepts a submission if it passes a criteria specified in `selection_policy_defs`. In addition to the output of selection policy, a submission might get rejected based on journal's acceptance rate, and publication bias rate. 









## Public Functions Documentation

### function PolicyBasedSelection

```cpp
inline PolicyBasedSelection(
    Parameters & p
)
```





























### function review

```cpp
virtual bool review(
    const Submission & s
) override
```



























Check wheter the selection_policy passes, if so, and a random draw from U(0, 1) is true, then the submission will be accepted; otherwise, it will be rejected 




## Public Attributes Documentation

### variable params

```cpp
Parameters params;
```





























### variable selection_policy

```cpp
PolicyChain selection_policy;
```

































-------------------------------

Updated on  3 December 2020 at 12:37:29 CET