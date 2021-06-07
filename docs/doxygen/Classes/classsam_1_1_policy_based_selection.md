---
title: sam::PolicyBasedSelection
summary: Policy-based Selection Strategy. 

---

# sam::PolicyBasedSelection

**Module:** **[Review Strategies](/doxygen/Modules/group___review_strategies/)**



Policy-based Selection Strategy.  [More...](#detailed-description)


`#include <ReviewStrategy.h>`

Inherits from ReviewStrategy

## Public Classes

|                | Name           |
| -------------- | -------------- |
| struct | **[Parameters](/doxygen/Classes/structsam_1_1_policy_based_selection_1_1_parameters/)** <br>[Parameters]() of the Policy-based Selection.  |

## Public Functions

|                | Name           |
| -------------- | -------------- |
| | **[PolicyBasedSelection](/doxygen/Classes/classsam_1_1_policy_based_selection/#function-policybasedselection)**([Parameters](/doxygen/Classes/structsam_1_1_policy_based_selection_1_1_parameters/) & p) |
| bool | **[review](/doxygen/Classes/classsam_1_1_policy_based_selection/#function-review)**(const std::vector< [Submission](/doxygen/Classes/classsam_1_1_submission/) > & s) override |
| bool | **[review](/doxygen/Classes/classsam_1_1_policy_based_selection/#function-review)**(const [Experiment](/doxygen/Classes/classsam_1_1_experiment/) & expr) override |

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

**Note**: This is a very flexible method, and it can technically be used to setup wide variety of review strategies, including traditional publication biased journal. 



```
        Policy-based review strategy accepts a submission if any of the
        submissions pass all the criteria specified by the
        `selection_policy_defs`. In addition to the output of selection
        policy, a submission might get rejected based on journal's
        acceptance rate, and publication bias rate.
```

## Public Functions Documentation

### function PolicyBasedSelection

```cpp
inline explicit PolicyBasedSelection(
    Parameters & p
)
```


### function review

```cpp
bool review(
    const std::vector< Submission > & s
) override
```


Reviews the list of submissions based on the user-defined policy

Check whether at least one of the submissions passes all criteria of the selection_policy, if so, a random number decides whether the publication bias will affect the decision. If not, a random draw from U(0, 1) decides whether the acceptance rate affects the decision, and if not, submissions will be accepted. 


Checks selection policy returns anything TodoI don't really like the const_cast here, maybe I need to find a way to remove it! 


### function review

```cpp
inline bool review(
    const Experiment & expr
) override
```


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

Updated on  7 June 2021 at 12:00:21 CEST