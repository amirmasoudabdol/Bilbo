---
title: sam::OutliersRemoval
summary: Declaration of Outlier Removal hacking method based on items' distance from their sample mean. 

---

# sam::OutliersRemoval

**Module:** **[Hacking Strategies](/doxygen/Modules/group___hacking_strategies/)**



Declaration of Outlier Removal hacking method based on items' distance from their sample mean. 
`#include <HackingStrategy.h>`

Inherits from [sam::HackingStrategy](/doxygen/Classes/classsam_1_1_hacking_strategy/)

## Public Classes

|                | Name           |
| -------------- | -------------- |
| struct | **[Parameters](/doxygen/Classes/structsam_1_1_outliers_removal_1_1_parameters/)**  |

## Public Functions

|                | Name           |
| -------------- | -------------- |
| | **[OutliersRemoval](/doxygen/Classes/classsam_1_1_outliers_removal/#function-outliersremoval)**() =default |
| | **[OutliersRemoval](/doxygen/Classes/classsam_1_1_outliers_removal/#function-outliersremoval)**(const [Parameters](/doxygen/Classes/structsam_1_1_outliers_removal_1_1_parameters/) & p) |
| virtual void | **[perform](/doxygen/Classes/classsam_1_1_outliers_removal/#function-perform)**([Experiment](/doxygen/Classes/classsam_1_1_experiment/) * experiment) override<br>Implementation of Outliers Removal based on an item's distance from the \mu.  |

## Public Attributes

|                | Name           |
| -------------- | -------------- |
| [Parameters](/doxygen/Classes/structsam_1_1_outliers_removal_1_1_parameters/) | **[params](/doxygen/Classes/classsam_1_1_outliers_removal/#variable-params)**  |
| [PolicyChain](/doxygen/Classes/structsam_1_1_policy_chain/) | **[stopping_condition](/doxygen/Classes/classsam_1_1_outliers_removal/#variable-stopping_condition)**  |

## Additional inherited members

**Public Functions inherited from [sam::HackingStrategy](/doxygen/Classes/classsam_1_1_hacking_strategy/)**

|                | Name           |
| -------------- | -------------- |
| virtual | **[~HackingStrategy](/doxygen/Classes/classsam_1_1_hacking_strategy/#function-~hackingstrategy)**() =0<br>Pure destructor of the Base class. This is important for proper deconstruction of Derived classes.  |
| | **[HackingStrategy](/doxygen/Classes/classsam_1_1_hacking_strategy/#function-hackingstrategy)**() |
| void | **[operator()](/doxygen/Classes/classsam_1_1_hacking_strategy/#function-operator())**([Experiment](/doxygen/Classes/classsam_1_1_experiment/) * experiment) |
| double | **[defensibility](/doxygen/Classes/classsam_1_1_hacking_strategy/#function-defensibility)**() const |
| double | **[prevalence](/doxygen/Classes/classsam_1_1_hacking_strategy/#function-prevalence)**() const |
| HackingStage | **[stage](/doxygen/Classes/classsam_1_1_hacking_strategy/#function-stage)**() const |
| HackingTarget | **[target](/doxygen/Classes/classsam_1_1_hacking_strategy/#function-target)**() const |
| std::unique_ptr< [HackingStrategy](/doxygen/Classes/classsam_1_1_hacking_strategy/) > | **[build](/doxygen/Classes/classsam_1_1_hacking_strategy/#function-build)**(json & hacking_strategy_config)<br>Factory method for building a [HackingStrategy](/doxygen/Classes/classsam_1_1_hacking_strategy/).  |

**Public Attributes inherited from [sam::HackingStrategy](/doxygen/Classes/classsam_1_1_hacking_strategy/)**

|                | Name           |
| -------------- | -------------- |
| sol::state | **[lua](/doxygen/Classes/classsam_1_1_hacking_strategy/#variable-lua)**  |
| double | **[defensibility_](/doxygen/Classes/classsam_1_1_hacking_strategy/#variable-defensibility_)**  |
| double | **[prevalence_](/doxygen/Classes/classsam_1_1_hacking_strategy/#variable-prevalence_)**  |
| HackingStage | **[stage_](/doxygen/Classes/classsam_1_1_hacking_strategy/#variable-stage_)**  |
| HackingTarget | **[target_](/doxygen/Classes/classsam_1_1_hacking_strategy/#variable-target_)**  |


## Public Functions Documentation

### function OutliersRemoval

```cpp
OutliersRemoval() =default
```


### function OutliersRemoval

```cpp
inline OutliersRemoval(
    const Parameters & p
)
```


### function perform

```cpp
virtual void perform(
    Experiment * experiment
) override
```

Implementation of Outliers Removal based on an item's distance from the \mu. 

**Reimplements**: [sam::HackingStrategy::perform](/doxygen/Classes/classsam_1_1_hacking_strategy/#function-perform)


Removing outliers `n` at a time, for the total of `n_attempts` It'll stop either when n_attempts are exhausted, or there is no more observations left to be removed


## Public Attributes Documentation

### variable params

```cpp
Parameters params;
```


### variable stopping_condition

```cpp
PolicyChain stopping_condition;
```


-------------------------------

Updated on  7 June 2021 at 12:00:21 CEST