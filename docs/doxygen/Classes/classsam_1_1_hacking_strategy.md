---
title: sam::HackingStrategy
summary: Abstract Class of Hacking Strategies.  

---

# sam::HackingStrategy


**Module:** **[Hacking Strategies](/doxygen/Modules/group___hacking_strategies/)**

Abstract Class of Hacking Strategies.  [More...](#detailed-description)


`#include <HackingStrategy.h>`



Inherited by [sam::ConditionDropping](/doxygen/Classes/classsam_1_1_condition_dropping/), [sam::FabricatingData](/doxygen/Classes/classsam_1_1_fabricating_data/), [sam::FalsifyingData](/doxygen/Classes/classsam_1_1_falsifying_data/), [sam::GroupPooling](/doxygen/Classes/classsam_1_1_group_pooling/), [sam::NoHack](/doxygen/Classes/classsam_1_1_no_hack/), [sam::OptionalStopping](/doxygen/Classes/classsam_1_1_optional_stopping/), [sam::OutliersRemoval](/doxygen/Classes/classsam_1_1_outliers_removal/), [sam::PeekingOutliersRemoval](/doxygen/Classes/classsam_1_1_peeking_outliers_removal/), [sam::QuestionableRounding](/doxygen/Classes/classsam_1_1_questionable_rounding/), [sam::StoppingDataCollection](/doxygen/Classes/classsam_1_1_stopping_data_collection/), [sam::SubjectiveOutlierRemoval](/doxygen/Classes/classsam_1_1_subjective_outlier_removal/)










## Public Functions

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


## Public Attributes

|                | Name           |
| -------------- | -------------- |
| sol::state | **[lua](/doxygen/Classes/classsam_1_1_hacking_strategy/#variable-lua)**  |
| double | **[defensibility_](/doxygen/Classes/classsam_1_1_hacking_strategy/#variable-defensibility_)**  |
| double | **[prevalence_](/doxygen/Classes/classsam_1_1_hacking_strategy/#variable-prevalence_)**  |
| HackingStage | **[stage_](/doxygen/Classes/classsam_1_1_hacking_strategy/#variable-stage_)**  |
| HackingTarget | **[target_](/doxygen/Classes/classsam_1_1_hacking_strategy/#variable-target_)**  |






## Detailed Description

```cpp
class sam::HackingStrategy;
```

Abstract Class of Hacking Strategies. 


























Each [HackingStrategy](/doxygen/Classes/classsam_1_1_hacking_strategy/) should provide a `perform()` method. The `perform()` method will take over a pointer to an [Experiment](/doxygen/Classes/classsam_1_1_experiment/) and apply the implemented hacking on it. [Researcher](/doxygen/Classes/classsam_1_1_researcher/) decides if this is a pointer to a _fresh_ copy of the [Experiment](/doxygen/Classes/classsam_1_1_experiment/) or a pointer to a previously "hacked" [Experiment](/doxygen/Classes/classsam_1_1_experiment/). 









## Public Functions Documentation

### function ~HackingStrategy

```cpp
virtual ~HackingStrategy() =0
```

Pure deconstuctor of the Base calss. This is important for proper deconstruction of Derived classes. 




























### function HackingStrategy

```cpp
HackingStrategy()
```





























### function operator()

```cpp
inline void operator()(
    Experiment * experiment
)
```





























### function defensibility

```cpp
inline double defensibility() const
```





























### function prevalence

```cpp
inline double prevalence() const
```





























### function stage

```cpp
inline HackingStage stage() const
```





























### function target

```cpp
inline HackingTarget target() const
```





























### function build

```cpp
static std::unique_ptr< HackingStrategy > build(
    json & hacking_strategy_config
)
```

Factory method for building a [HackingStrategy](/doxygen/Classes/classsam_1_1_hacking_strategy/). 

**Parameters**: 

  * **config** A reference to an item of the "json[&ndash;hacking-strategy']`. Researcher::Builder is responsible for passing this object correctly.
  * **config** A JSON object defining a hacking strategy, and its parameters 







**Return**: 

  * A new [HackingStrategy](/doxygen/Classes/classsam_1_1_hacking_strategy/)
  * Pointer to a [HackingStrategy](/doxygen/Classes/classsam_1_1_hacking_strategy/)





















A Factory method for building hacking strategies


### function build

```cpp
static std::unique_ptr< HackingStrategy > build(
    HackingMethod method
)
```































## Public Attributes Documentation

### variable lua

```cpp
sol::state lua;
```





























### variable defensibility_

```cpp
double defensibility_;
```





























### variable prevalence_

```cpp
double prevalence_;
```





























### variable stage_

```cpp
HackingStage stage_;
```





























### variable target_

```cpp
HackingTarget target_;
```

































-------------------------------

Updated on  7 December 2020 at 13:20:09 CET