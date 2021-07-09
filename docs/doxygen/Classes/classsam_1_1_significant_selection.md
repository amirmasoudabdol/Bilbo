---
title: sam::SignificantSelection
summary: Significant-based Selection Strategy. 

---

# sam::SignificantSelection

**Module:** **[Review Strategies](/doxygen/Modules/group___review_strategies/)**



Significant-based Selection Strategy.  [More...](#detailed-description)


`#include <ReviewStrategy.h>`

Inherits from ReviewStrategy

## Public Classes

|                | Name           |
| -------------- | -------------- |
| struct | **[Parameters](/doxygen/Classes/structsam_1_1_significant_selection_1_1_parameters/)**  |

## Public Functions

|                | Name           |
| -------------- | -------------- |
| | **[SignificantSelection](/doxygen/Classes/classsam_1_1_significant_selection/#function-significantselection)**(const [Parameters](/doxygen/Classes/structsam_1_1_significant_selection_1_1_parameters/) & p) |
| bool | **[review](/doxygen/Classes/classsam_1_1_significant_selection/#function-review)**(const std::vector< [Submission](/doxygen/Classes/classsam_1_1_submission/) > & s) override |
| bool | **[review](/doxygen/Classes/classsam_1_1_significant_selection/#function-review)**(const [Experiment](/doxygen/Classes/classsam_1_1_experiment/) & expr) override |

## Public Attributes

|                | Name           |
| -------------- | -------------- |
| [Parameters](/doxygen/Classes/structsam_1_1_significant_selection_1_1_parameters/) | **[params](/doxygen/Classes/classsam_1_1_significant_selection/#variable-params)**  |

## Detailed Description

```cpp
class sam::SignificantSelection;
```

Significant-based Selection Strategy. 



```
        Significant-based review strategy accepts a publication if the
        given *p*-value is significant. Certain degree of *publication
        bias*, can be specified. In this case, a Submission has a chance
        of being published even if the statistics is not significant.
        Moreover, the SignificantSelection can be tailored toward either
        positive or negative effect. In this case, the Journal will only
        accept Submissions with larger or smaller effects.
```

## Public Functions Documentation

### function SignificantSelection

```cpp
inline explicit SignificantSelection(
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

  * **s** A reference to the [Submission](/doxygen/Classes/classsam_1_1_submission/)


**Return**: a boolean indicating whether the [Submission](/doxygen/Classes/classsam_1_1_submission/) is accepted. 

Check if the _p_-value of any of the Submissions are less than the specified \(\alpha\). If true, it will accept the submission, if not, a random number decide whether or not the submission is going to be accepted. The drawn random number, \(r\) will be compared to `pub_bias_rate` of the journal.


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

Updated on 29 June 2021 at 16:13:48 CEST