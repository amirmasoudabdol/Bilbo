---
title: sam::PolicyBasedSelection::Parameters
summary: Parameters of the Policy-based Selection. 

---

# sam::PolicyBasedSelection::Parameters

**Module:** **[Parameters of Review Strategies](/doxygen/Modules/group___review_strategies_parameters/)**



[Parameters]() of the Policy-based Selection. 
`#include <ReviewStrategy.h>`

## Public Functions

|                | Name           |
| -------------- | -------------- |
| | **[NLOHMANN_DEFINE_TYPE_INTRUSIVE](/doxygen/Classes/structsam_1_1_policy_based_selection_1_1_parameters/#function-nlohmann_define_type_intrusive)**([PolicyBasedSelection::Parameters](/doxygen/Classes/structsam_1_1_policy_based_selection_1_1_parameters/) , name , [pub_bias_rate](/doxygen/Classes/structsam_1_1_policy_based_selection_1_1_parameters/#variable-pub_bias_rate) , [acceptance_rate](/doxygen/Classes/structsam_1_1_policy_based_selection_1_1_parameters/#variable-acceptance_rate) , [selection_policy_defs](/doxygen/Classes/structsam_1_1_policy_based_selection_1_1_parameters/#variable-selection_policy_defs) ) |

## Public Attributes

|                | Name           |
| -------------- | -------------- |
| [SelectionMethod](/doxygen/Namespaces/namespacesam/#enum-selectionmethod) | **[name](/doxygen/Classes/structsam_1_1_policy_based_selection_1_1_parameters/#variable-name)**  |
| double | **[pub_bias_rate](/doxygen/Classes/structsam_1_1_policy_based_selection_1_1_parameters/#variable-pub_bias_rate)** <br>Publication Bias Rate.  |
| double | **[acceptance_rate](/doxygen/Classes/structsam_1_1_policy_based_selection_1_1_parameters/#variable-acceptance_rate)** <br>Acceptance Rate.  |
| std::vector< std::string > | **[selection_policy_defs](/doxygen/Classes/structsam_1_1_policy_based_selection_1_1_parameters/#variable-selection_policy_defs)**  |

## Public Functions Documentation

### function NLOHMANN_DEFINE_TYPE_INTRUSIVE

```cpp
NLOHMANN_DEFINE_TYPE_INTRUSIVE(
    PolicyBasedSelection::Parameters ,
    name ,
    pub_bias_rate ,
    acceptance_rate ,
    selection_policy_defs 
)
```


## Public Attributes Documentation

### variable name

```cpp
SelectionMethod name = SelectionMethod::PolicyBasedSelection;
```


### variable pub_bias_rate

```cpp
double pub_bias_rate {};
```

Publication Bias Rate. 

### variable acceptance_rate

```cpp
double acceptance_rate {};
```

Acceptance Rate. 

### variable selection_policy_defs

```cpp
std::vector< std::string > selection_policy_defs {};
```


Definition of the selection policy used by [Journal](/doxygen/Classes/classsam_1_1_journal/) to evaluate a given submission 


-------------------------------

Updated on  7 June 2021 at 12:00:21 CEST