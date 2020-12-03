---
title: sam::SignificantSelection::Parameters


---

# sam::SignificantSelection::Parameters




 [More...](#detailed-description)


`#include <SelectionStrategy.h>`













## Public Functions

|                | Name           |
| -------------- | -------------- |
|  | **[NLOHMANN_DEFINE_TYPE_INTRUSIVE](/doxygen/Classes/structsam_1_1_significant_selection_1_1_parameters/#function-nlohmann_define_type_intrusive)**([SignificantSelection::Parameters](/doxygen/Classes/structsam_1_1_significant_selection_1_1_parameters/) , [name](/doxygen/Classes/structsam_1_1_significant_selection_1_1_parameters/#variable-name) , [alpha](/doxygen/Classes/structsam_1_1_significant_selection_1_1_parameters/#variable-alpha) , [pub_bias](/doxygen/Classes/structsam_1_1_significant_selection_1_1_parameters/#variable-pub_bias) , [side](/doxygen/Classes/structsam_1_1_significant_selection_1_1_parameters/#variable-side) )  |


## Public Attributes

|                | Name           |
| -------------- | -------------- |
| SelectionMethod | **[name](/doxygen/Classes/structsam_1_1_significant_selection_1_1_parameters/#variable-name)** <br>Selection strategy name.  |
| double | **[alpha](/doxygen/Classes/structsam_1_1_significant_selection_1_1_parameters/#variable-alpha)**  |
| double | **[pub_bias](/doxygen/Classes/structsam_1_1_significant_selection_1_1_parameters/#variable-pub_bias)** <br>Publication bias rate.  |
| int | **[side](/doxygen/Classes/structsam_1_1_significant_selection_1_1_parameters/#variable-side)**  |






## Detailed Description

```cpp
struct sam::SignificantSelection::Parameters;
```



























A type keeping the parameters of the Significat Seleciton strategy. 









## Public Functions Documentation

### function NLOHMANN_DEFINE_TYPE_INTRUSIVE

```cpp
NLOHMANN_DEFINE_TYPE_INTRUSIVE(
    SignificantSelection::Parameters ,
    name ,
    alpha ,
    pub_bias ,
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
double alpha {0.05};
```



























The \alpha at which the _selection strategy_ decides the significance of a publication 


### variable pub_bias

```cpp
double pub_bias {0.5};
```

Publication bias rate. 




























### variable side

```cpp
int side {1};
```



























Indicates the _selection stratgy_'s preference toward positive, `1`, or negative, `-1` effect. If `0`, [Journal](/doxygen/Classes/classsam_1_1_journal/) doesn't have any preferences. 






-------------------------------

Updated on  3 December 2020 at 12:37:29 CET