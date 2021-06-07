---
title: sam::FreeSelection
summary: FreeSelection doesn't pose any restriction on the submission and all submissions will be accepted. 

---

# sam::FreeSelection

**Module:** **[Review Strategies](/doxygen/Modules/group___review_strategies/)**



[FreeSelection]() doesn't pose any restriction on the submission and all submissions will be accepted. 
`#include <ReviewStrategy.h>`

Inherits from ReviewStrategy

## Public Classes

|                | Name           |
| -------------- | -------------- |
| struct | **[Parameters](/doxygen/Classes/structsam_1_1_free_selection_1_1_parameters/)** <br>[Parameters]() of free selection.  |

## Public Functions

|                | Name           |
| -------------- | -------------- |
| | **[FreeSelection](/doxygen/Classes/classsam_1_1_free_selection/#function-freeselection)**() =default |
| bool | **[review](/doxygen/Classes/classsam_1_1_free_selection/#function-review)**(const std::vector< [Submission](/doxygen/Classes/classsam_1_1_submission/) > & s) override<br>It accepts everything.  |
| bool | **[review](/doxygen/Classes/classsam_1_1_free_selection/#function-review)**(const [Experiment](/doxygen/Classes/classsam_1_1_experiment/) & expr) override<br>It accepts everything.  |

## Public Attributes

|                | Name           |
| -------------- | -------------- |
| [Parameters](/doxygen/Classes/structsam_1_1_free_selection_1_1_parameters/) | **[params](/doxygen/Classes/classsam_1_1_free_selection/#variable-params)**  |

## Public Functions Documentation

### function FreeSelection

```cpp
FreeSelection() =default
```


### function review

```cpp
inline bool review(
    const std::vector< Submission > & s
) override
```

It accepts everything. 

### function review

```cpp
inline bool review(
    const Experiment & expr
) override
```

It accepts everything. 

## Public Attributes Documentation

### variable params

```cpp
Parameters params;
```


-------------------------------

Updated on  7 June 2021 at 12:00:21 CEST