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
| | **[ConditionDropping](/doxygen/Classes/classsam_1_1_condition_dropping/#function-conditiondropping)**(const [Parameters](/doxygen/Classes/structsam_1_1_condition_dropping_1_1_parameters/) & p) |
| | **[ConditionDropping](/doxygen/Classes/classsam_1_1_condition_dropping/#function-conditiondropping)**() |

## Public Attributes

|                | Name           |
| -------------- | -------------- |
| [Parameters](/doxygen/Classes/structsam_1_1_condition_dropping_1_1_parameters/) | **[params](/doxygen/Classes/classsam_1_1_condition_dropping/#variable-params)**  |

## Additional inherited members

**Public Functions inherited from [sam::HackingStrategy](/doxygen/Classes/classsam_1_1_hacking_strategy/)**

|                | Name           |
| -------------- | -------------- |
| virtual | **[~HackingStrategy](/doxygen/Classes/classsam_1_1_hacking_strategy/#function-~hackingstrategy)**() =0<br>Pure destructor of the Base class. This is important for proper deconstruction of Derived classes.  |
| | **[HackingStrategy](/doxygen/Classes/classsam_1_1_hacking_strategy/#function-hackingstrategy)**() |
| void | **[operator()](/doxygen/Classes/classsam_1_1_hacking_strategy/#function-operator())**([Experiment](/doxygen/Classes/classsam_1_1_experiment/) * experiment) |
| float | **[defensibility](/doxygen/Classes/classsam_1_1_hacking_strategy/#function-defensibility)**() const |
| float | **[prevalence](/doxygen/Classes/classsam_1_1_hacking_strategy/#function-prevalence)**() const |
| HackingStage | **[stage](/doxygen/Classes/classsam_1_1_hacking_strategy/#function-stage)**() const |
| HackingTarget | **[target](/doxygen/Classes/classsam_1_1_hacking_strategy/#function-target)**() const |
| std::unique_ptr< [HackingStrategy](/doxygen/Classes/classsam_1_1_hacking_strategy/) > | **[build](/doxygen/Classes/classsam_1_1_hacking_strategy/#function-build)**(json & hacking_strategy_config)<br>Factory method for building a [HackingStrategy](/doxygen/Classes/classsam_1_1_hacking_strategy/).  |

**Public Attributes inherited from [sam::HackingStrategy](/doxygen/Classes/classsam_1_1_hacking_strategy/)**

|                | Name           |
| -------------- | -------------- |
| sol::state | **[lua](/doxygen/Classes/classsam_1_1_hacking_strategy/#variable-lua)**  |
| std::optional< float > | **[defensibility_](/doxygen/Classes/classsam_1_1_hacking_strategy/#variable-defensibility_)**  |
| std::optional< float > | **[prevalence_](/doxygen/Classes/classsam_1_1_hacking_strategy/#variable-prevalence_)**  |
| HackingStage | **[stage_](/doxygen/Classes/classsam_1_1_hacking_strategy/#variable-stage_)**  |
| HackingTarget | **[target_](/doxygen/Classes/classsam_1_1_hacking_strategy/#variable-target_)**  |


## Public Functions Documentation

### function ConditionDropping

```cpp
inline explicit ConditionDropping(
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

Updated on 29 June 2021 at 16:13:46 CEST