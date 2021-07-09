---
title: sam::SignificantSelection::Parameters

---

# sam::SignificantSelection::Parameters

**Module:** **[Parameters of Review Strategies](/doxygen/Modules/group___review_strategies_parameters/)**



 [More...](#detailed-description)


`#include <ReviewStrategy.h>`

## Public Functions

|                | Name           |
| -------------- | -------------- |
| | **[NLOHMANN_DEFINE_TYPE_INTRUSIVE](/doxygen/Classes/structsam_1_1_significant_selection_1_1_parameters/#function-nlohmann_define_type_intrusive)**([SignificantSelection::Parameters](/doxygen/Classes/structsam_1_1_significant_selection_1_1_parameters/) , [name](/doxygen/Classes/structsam_1_1_significant_selection_1_1_parameters/#variable-name) , [alpha](/doxygen/Classes/structsam_1_1_significant_selection_1_1_parameters/#variable-alpha) , [pub_bias_rate](/doxygen/Classes/structsam_1_1_significant_selection_1_1_parameters/#variable-pub_bias_rate) , [side](/doxygen/Classes/structsam_1_1_significant_selection_1_1_parameters/#variable-side) ) |

## Public Attributes

|                | Name           |
| -------------- | -------------- |
| [SelectionMethod](/doxygen/Namespaces/namespacesam/#enum-selectionmethod) | **[name](/doxygen/Classes/structsam_1_1_significant_selection_1_1_parameters/#variable-name)** <br>Selection strategy name.  |
| float | **[alpha](/doxygen/Classes/structsam_1_1_significant_selection_1_1_parameters/#variable-alpha)**  |
| float | **[pub_bias_rate](/doxygen/Classes/structsam_1_1_significant_selection_1_1_parameters/#variable-pub_bias_rate)** <br>Publication bias rate.  |
| int | **[side](/doxygen/Classes/structsam_1_1_significant_selection_1_1_parameters/#variable-side)**  |

## Detailed Description

```cpp
struct sam::SignificantSelection::Parameters;
```


A type keeping the parameters of the Significant Selection strategy. 

## Public Functions Documentation

### function NLOHMANN_DEFINE_TYPE_INTRUSIVE

```cpp
NLOHMANN_DEFINE_TYPE_INTRUSIVE(
    SignificantSelection::Parameters ,
    name ,
    alpha ,
    pub_bias_rate ,
    side 
)
```


## Public Attributes Documentation

### variable name

```cpp
SelectionMethod name = SelectionMethod::SignificantSelection;
```

Selection strategy name. 

### variable alpha

```cpp
float alpha {};
```


The \alpha at which the _review strategy_ decides the significance of a publication 


### variable pub_bias_rate

```cpp
float pub_bias_rate {};
```

Publication bias rate. 

### variable side

```cpp
int side {1};
```


Indicates the _selection strategy_'s preference toward positive, `1`, or negative, `-1` effect. If `0`, [Journal](/doxygen/Classes/classsam_1_1_journal/) doesn't have any preferences. 


-------------------------------

Updated on 29 June 2021 at 16:13:48 CEST