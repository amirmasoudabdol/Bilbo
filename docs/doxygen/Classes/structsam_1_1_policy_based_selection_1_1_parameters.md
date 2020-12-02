---
title: sam::PolicyBasedSelection::Parameters


---

# sam::PolicyBasedSelection::Parameters



















## Public Functions

|                | Name           |
| -------------- | -------------- |
|  | **[NLOHMANN_DEFINE_TYPE_INTRUSIVE](/doxygen/Classes/structsam_1_1_policy_based_selection_1_1_parameters/#function-nlohmann_define_type_intrusive)**([PolicyBasedSelection::Parameters](/doxygen/Classes/structsam_1_1_policy_based_selection_1_1_parameters/) , name , [pub_bias](/doxygen/Classes/structsam_1_1_policy_based_selection_1_1_parameters/#variable-pub_bias) , [pub_chance](/doxygen/Classes/structsam_1_1_policy_based_selection_1_1_parameters/#variable-pub_chance) , [selection_policy_defs](/doxygen/Classes/structsam_1_1_policy_based_selection_1_1_parameters/#variable-selection_policy_defs) )  |


## Public Attributes

|                | Name           |
| -------------- | -------------- |
| SelectionMethod | **[name](/doxygen/Classes/structsam_1_1_policy_based_selection_1_1_parameters/#variable-name)**  |
| double | **[pub_bias](/doxygen/Classes/structsam_1_1_policy_based_selection_1_1_parameters/#variable-pub_bias)** <br>Publication Bias Rate.  |
| double | **[pub_chance](/doxygen/Classes/structsam_1_1_policy_based_selection_1_1_parameters/#variable-pub_chance)** <br>Acceptance Rate.  |
| std::vector< std::string > | **[selection_policy_defs](/doxygen/Classes/structsam_1_1_policy_based_selection_1_1_parameters/#variable-selection_policy_defs)** <br>Definition of the selection policy used by [Journal](/doxygen/Classes/classsam_1_1_journal/) to evaluate a given submission.  |














## Public Functions Documentation

### function NLOHMANN_DEFINE_TYPE_INTRUSIVE

```cpp
NLOHMANN_DEFINE_TYPE_INTRUSIVE(
    PolicyBasedSelection::Parameters ,
    name ,
    pub_bias ,
    pub_chance ,
    selection_policy_defs 
)
```































## Public Attributes Documentation

### variable name

```cpp
SelectionMethod name = SelectionMethod::PolicyBasedSelection;
```





























### variable pub_bias

```cpp
double pub_bias {0.5};
```

Publication Bias Rate. 




























### variable pub_chance

```cpp
double pub_chance {0.5};
```

Acceptance Rate. 




























### variable selection_policy_defs

```cpp
std::vector< std::string > selection_policy_defs {"sig"};
```

Definition of the selection policy used by [Journal](/doxygen/Classes/classsam_1_1_journal/) to evaluate a given submission. 
































-------------------------------

Updated on  2 December 2020 at 14:48:55 CET