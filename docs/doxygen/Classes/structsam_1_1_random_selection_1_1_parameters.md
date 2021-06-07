---
title: sam::RandomSelection::Parameters
summary: Parameter of Random Selection review strategy. 

---

# sam::RandomSelection::Parameters

**Module:** **[Parameters of Review Strategies](/doxygen/Modules/group___review_strategies_parameters/)**



[Parameter](/doxygen/Classes/classsam_1_1_parameter/) of _Random Selection_ review strategy. 
`#include <ReviewStrategy.h>`

## Public Functions

|                | Name           |
| -------------- | -------------- |
| | **[NLOHMANN_DEFINE_TYPE_INTRUSIVE](/doxygen/Classes/structsam_1_1_random_selection_1_1_parameters/#function-nlohmann_define_type_intrusive)**([RandomSelection::Parameters](/doxygen/Classes/structsam_1_1_random_selection_1_1_parameters/) , name , [acceptance_rate](/doxygen/Classes/structsam_1_1_random_selection_1_1_parameters/#variable-acceptance_rate) ) |

## Public Attributes

|                | Name           |
| -------------- | -------------- |
| [SelectionMethod](/doxygen/Namespaces/namespacesam/#enum-selectionmethod) | **[name](/doxygen/Classes/structsam_1_1_random_selection_1_1_parameters/#variable-name)**  |
| double | **[acceptance_rate](/doxygen/Classes/structsam_1_1_random_selection_1_1_parameters/#variable-acceptance_rate)** <br>Indicates the acceptance rate of the [Journal](/doxygen/Classes/classsam_1_1_journal/).  |

## Public Functions Documentation

### function NLOHMANN_DEFINE_TYPE_INTRUSIVE

```cpp
NLOHMANN_DEFINE_TYPE_INTRUSIVE(
    RandomSelection::Parameters ,
    name ,
    acceptance_rate 
)
```


## Public Attributes Documentation

### variable name

```cpp
SelectionMethod name = SelectionMethod::RandomSelection;
```


### variable acceptance_rate

```cpp
double acceptance_rate {};
```

Indicates the acceptance rate of the [Journal](/doxygen/Classes/classsam_1_1_journal/). 

-------------------------------

Updated on  7 June 2021 at 12:00:21 CEST