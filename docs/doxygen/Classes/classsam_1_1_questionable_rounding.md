---
title: sam::QuestionableRounding


---

# sam::QuestionableRounding


**Module:** **[Hacking Strategies](/doxygen/Modules/group___hacking_strategies/)**

 [More...](#detailed-description)


`#include <HackingStrategy.h>`


Inherits from [sam::HackingStrategy](/doxygen/Classes/classsam_1_1_hacking_strategy/)



## Public Classes

|                | Name           |
| -------------- | -------------- |
| struct | **[Parameters](/doxygen/Classes/structsam_1_1_questionable_rounding_1_1_parameters/)**  |








## Public Functions

|                | Name           |
| -------------- | -------------- |
|  | **[QuestionableRounding](/doxygen/Classes/classsam_1_1_questionable_rounding/#function-questionablerounding)**() =default  |
|  | **[QuestionableRounding](/doxygen/Classes/classsam_1_1_questionable_rounding/#function-questionablerounding)**(const [Parameters](/doxygen/Classes/structsam_1_1_questionable_rounding_1_1_parameters/) & p)  |
| virtual void | **[perform](/doxygen/Classes/classsam_1_1_questionable_rounding/#function-perform)**([Experiment](/doxygen/Classes/classsam_1_1_experiment/) * experiment) override <br>Applies the hacking method on the [Experiment](/doxygen/Classes/classsam_1_1_experiment/).  |


## Public Attributes

|                | Name           |
| -------------- | -------------- |
| [Parameters](/doxygen/Classes/structsam_1_1_questionable_rounding_1_1_parameters/) | **[params](/doxygen/Classes/classsam_1_1_questionable_rounding/#variable-params)**  |




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
class sam::QuestionableRounding;
```



























[QuestionableRounding](/doxygen/Classes/classsam_1_1_questionable_rounding/) Hacking Strategy

Questionable rounding strategy mimics the behavior of a researcher who might hack its way to significace by aggressively rounding the pvalue and ignoring everything else. 









## Public Functions Documentation

### function `QuestionableRounding`

```cpp
QuestionableRounding() =default
```





























### function `QuestionableRounding`

```cpp
inline QuestionableRounding(
    const Parameters & p
)
```





























### function `perform`

```cpp
virtual void perform(
    Experiment * experiment
) override
```

Applies the hacking method on the [Experiment](/doxygen/Classes/classsam_1_1_experiment/). 

**Parameters**: 

  * **`experiment`** A pointer to an [Experiment](/doxygen/Classes/classsam_1_1_experiment/). 

























**Reimplements**: [sam::HackingStrategy::perform](/doxygen/Classes/classsam_1_1_hacking_strategy/#function-perform)



Checking whether the outcome is significant, if not, we check whether it's close enough to be a hacked, if so, we either set the pvalue to `alpha` or the difference between pvalue and threshorld



## Public Attributes Documentation

### variable `params`

```cpp
Parameters params;
```

































