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
|  | **[OptionalStopping](/doxygen/Classes/classsam_1_1_optional_stopping/#function-optionalstopping)**() =default  |
|  | **[OptionalStopping](/doxygen/Classes/classsam_1_1_optional_stopping/#function-optionalstopping)**(const [Parameters](/doxygen/Classes/structsam_1_1_optional_stopping_1_1_parameters/) & p)  |
| void | **[addObservations](/doxygen/Classes/classsam_1_1_optional_stopping/#function-addobservations)**([Experiment](/doxygen/Classes/classsam_1_1_experiment/) * experiment, const int n)  |
| void | **[addObservations](/doxygen/Classes/classsam_1_1_optional_stopping/#function-addobservations)**([Experiment](/doxygen/Classes/classsam_1_1_experiment/) * experiment, const arma::Row< int > ns)  |


## Public Attributes

|                | Name           |
| -------------- | -------------- |
| [Parameters](/doxygen/Classes/structsam_1_1_optional_stopping_1_1_parameters/) | **[params](/doxygen/Classes/classsam_1_1_optional_stopping/#variable-params)**  |
| [PolicyChain](/doxygen/Classes/structsam_1_1_policy_chain/) | **[stopping_condition](/doxygen/Classes/classsam_1_1_optional_stopping/#variable-stopping_condition)**  |




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





## Detailed Description

```cpp
class sam::OptionalStopping;
```



























Declartion of [OptionalStopping](/doxygen/Classes/classsam_1_1_optional_stopping/) hacking strategy 









## Public Functions Documentation

### function OptionalStopping

```cpp
OptionalStopping() =default
```





























### function OptionalStopping

```cpp
inline OptionalStopping(
    const Parameters & p
)
```





























### function addObservations

```cpp
void addObservations(
    Experiment * experiment,
    const int n
)
```


**Parameters**: 

  * **experiment** A pointer to the experiment 
  * **n** number of new observations to be added 


























Adds `n` observations to all groups


### function addObservations

```cpp
void addObservations(
    Experiment * experiment,
    const arma::Row< int > ns
)
```


**Parameters**: 

  * **experiment** A pointer to an experiment 
  * **ns** An array indicating how many new items should be added to each group 


























Adds `ns[i]` new items to `i`th group




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

Updated on  3 December 2020 at 12:37:29 CET