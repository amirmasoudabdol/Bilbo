---
title: sam::RandomSelection
summary: Random Selection Strategy. 

---

# sam::RandomSelection

**Module:** **[Review Strategies](/doxygen/Modules/group___review_strategies/)**



Random Selection Strategy.  [More...](#detailed-description)


`#include <ReviewStrategy.h>`

Inherits from ReviewStrategy

## Public Classes

|                | Name           |
| -------------- | -------------- |
| struct | **[Parameters](/doxygen/Classes/structsam_1_1_random_selection_1_1_parameters/)** <br>[Parameter](/doxygen/Classes/classsam_1_1_parameter/) of _Random Selection_ review strategy.  |

## Public Functions

|                | Name           |
| -------------- | -------------- |
| | **[RandomSelection](/doxygen/Classes/classsam_1_1_random_selection/#function-randomselection)**(const [Parameters](/doxygen/Classes/structsam_1_1_random_selection_1_1_parameters/) & p) |
| bool | **[review](/doxygen/Classes/classsam_1_1_random_selection/#function-review)**(const std::vector< [Submission](/doxygen/Classes/classsam_1_1_submission/) > & s) override |
| bool | **[review](/doxygen/Classes/classsam_1_1_random_selection/#function-review)**(const [Experiment](/doxygen/Classes/classsam_1_1_experiment/) & expr) override |

## Public Attributes

|                | Name           |
| -------------- | -------------- |
| [Parameters](/doxygen/Classes/structsam_1_1_random_selection_1_1_parameters/) | **[params](/doxygen/Classes/classsam_1_1_random_selection/#variable-params)**  |

## Detailed Description

```cpp
class sam::RandomSelection;
```

Random Selection Strategy. 



```
        In this method, Journal does not check any criteria for
        accepting or rejecting a submission. The `acceptance_rate` will
        decide the acceptance or rejection of a list of submissions.
```

## Public Functions Documentation

### function RandomSelection

```cpp
inline explicit RandomSelection(
    const Parameters & p
)
```


### function review

```cpp
bool review(
    const std::vector< Submission > & s
) override
```


**Parameters**: 

  * **s** corresponding submission 


**Return**: a boolean indicating whether the [Submission](/doxygen/Classes/classsam_1_1_submission/) is accepted. 

Based on a draw from \( r \in [0, 1] \), it accepts the submission if \(r\) < `acceptance_rate`.


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


-------------------------------

Updated on  7 June 2021 at 12:00:21 CEST