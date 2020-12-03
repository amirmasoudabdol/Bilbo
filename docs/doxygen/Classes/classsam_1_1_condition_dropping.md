---
title: sam::ConditionDropping


---

# sam::ConditionDropping








Inherits from [sam::HackingStrategy](/doxygen/Classes/classsam_1_1_hacking_strategy/)



## Public Classes

|                | Name           |
| -------------- | -------------- |
| struct | **[Parameters](/doxygen/Classes/structsam_1_1_condition_dropping_1_1_parameters/)**  |








## Public Functions

|                | Name           |
| -------------- | -------------- |
|  | **[ConditionDropping](/doxygen/Classes/classsam_1_1_condition_dropping/#function-conditiondropping)**(const [Parameters](/doxygen/Classes/structsam_1_1_condition_dropping_1_1_parameters/) & p)  |
|  | **[ConditionDropping](/doxygen/Classes/classsam_1_1_condition_dropping/#function-conditiondropping)**()  |


## Public Attributes

|                | Name           |
| -------------- | -------------- |
| [Parameters](/doxygen/Classes/structsam_1_1_condition_dropping_1_1_parameters/) | **[params](/doxygen/Classes/classsam_1_1_condition_dropping/#variable-params)**  |




## Additional inherited members










**Public Functions inherited from [sam::HackingStrategy](/doxygen/Classes/classsam_1_1_hacking_strategy/)**

|                | Name           |
| -------------- | -------------- |
| virtual  | **[~HackingStrategy](/doxygen/Classes/classsam_1_1_hacking_strategy/#function-~hackingstrategy)**() =0 <br>Pure deconstuctor of the Base calss. This is important for proper deconstruction of Derived classes.  |
|  | **[HackingStrategy](/doxygen/Classes/classsam_1_1_hacking_strategy/#function-hackingstrategy)**()  |
| void | **[operator()](/doxygen/Classes/classsam_1_1_hacking_strategy/#function-operator())**([Experiment](/doxygen/Classes/classsam_1_1_experiment/) * experiment)  |
| double | **[defensibility](/doxygen/Classes/classsam_1_1_hacking_strategy/#function-defensibility)**() const  |
| double | **[prevalence](/doxygen/Classes/classsam_1_1_hacking_strategy/#function-prevalence)**() const  |
| HackingStage | **[stage](/doxygen/Classes/classsam_1_1_hacking_strategy/#function-stage)**() const  |
| HackingTarget | **[target](/doxygen/Classes/classsam_1_1_hacking_strategy/#function-target)**() const  |
| std::unique_ptr< [HackingStrategy](/doxygen/Classes/classsam_1_1_hacking_strategy/) > | **[build](/doxygen/Classes/classsam_1_1_hacking_strategy/#function-build)**(json & hacking_strategy_config) <br>Factory method for building a [HackingStrategy](/doxygen/Classes/classsam_1_1_hacking_strategy/).  |
| std::unique_ptr< [HackingStrategy](/doxygen/Classes/classsam_1_1_hacking_strategy/) > | **[build](/doxygen/Classes/classsam_1_1_hacking_strategy/#function-build)**(HackingMethod method)  |


**Public Attributes inherited from [sam::HackingStrategy](/doxygen/Classes/classsam_1_1_hacking_strategy/)**

|                | Name           |
| -------------- | -------------- |
| sol::state | **[lua](/doxygen/Classes/classsam_1_1_hacking_strategy/#variable-lua)**  |
| double | **[defensibility_](/doxygen/Classes/classsam_1_1_hacking_strategy/#variable-defensibility_)**  |
| double | **[prevalence_](/doxygen/Classes/classsam_1_1_hacking_strategy/#variable-prevalence_)**  |
| HackingStage | **[stage_](/doxygen/Classes/classsam_1_1_hacking_strategy/#variable-stage_)**  |
| HackingTarget | **[target_](/doxygen/Classes/classsam_1_1_hacking_strategy/#variable-target_)**  |













## Public Functions Documentation

### function ConditionDropping

```cpp
inline ConditionDropping(
    const Parameters & p
)
```





























### function ConditionDropping

```cpp
inline ConditionDropping()
```































## Public Attributes Documentation

### variable params

```cpp
Parameters params;
```

































-------------------------------

Updated on  3 December 2020 at 12:37:28 CET