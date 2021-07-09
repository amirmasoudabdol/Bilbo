---
title: sam::OptionalStopping

---

# sam::OptionalStopping

**Module:** **[Hacking Strategies](/doxygen/Modules/group___hacking_strategies/)**



 [More...](#detailed-description)


`#include <HackingStrategy.h>`

Inherits from [sam::HackingStrategy](/doxygen/Classes/classsam_1_1_hacking_strategy/)

## Public Classes

|                | Name           |
| -------------- | -------------- |
| struct | **[Parameters](/doxygen/Classes/structsam_1_1_optional_stopping_1_1_parameters/)**  |

## Public Functions

|                | Name           |
| -------------- | -------------- |
| | **[OptionalStopping](/doxygen/Classes/classsam_1_1_optional_stopping/#function-optionalstopping)**() =default |
| | **[OptionalStopping](/doxygen/Classes/classsam_1_1_optional_stopping/#function-optionalstopping)**(const [Parameters](/doxygen/Classes/structsam_1_1_optional_stopping_1_1_parameters/) & p) |
| void | **[addObservations](/doxygen/Classes/classsam_1_1_optional_stopping/#function-addobservations)**([Experiment](/doxygen/Classes/classsam_1_1_experiment/) * experiment, const arma::Row< int > & ns)<br>Adds new observations to each group.  |

## Public Attributes

|                | Name           |
| -------------- | -------------- |
| [Parameters](/doxygen/Classes/structsam_1_1_optional_stopping_1_1_parameters/) | **[params](/doxygen/Classes/classsam_1_1_optional_stopping/#variable-params)**  |
| [PolicyChain](/doxygen/Classes/structsam_1_1_policy_chain/) | **[stopping_condition](/doxygen/Classes/classsam_1_1_optional_stopping/#variable-stopping_condition)**  |

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


## Detailed Description

```cpp
class sam::OptionalStopping;
```


Declaration of [OptionalStopping](/doxygen/Classes/classsam_1_1_optional_stopping/) hacking strategy 

## Public Functions Documentation

### function OptionalStopping

```cpp
OptionalStopping() =default
```


### function OptionalStopping

```cpp
inline explicit OptionalStopping(
    const Parameters & p
)
```


### function addObservations

```cpp
void addObservations(
    Experiment * experiment,
    const arma::Row< int > & ns
)
```

Adds new observations to each group. 

**Parameters**: 

  * **experiment** The pointer to the [Experiment](/doxygen/Classes/classsam_1_1_experiment/)
  * **ns** Indicates the number of new observations to be added to each group. 


Adds new observations to every group.


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

Updated on 29 June 2021 at 16:13:47 CEST