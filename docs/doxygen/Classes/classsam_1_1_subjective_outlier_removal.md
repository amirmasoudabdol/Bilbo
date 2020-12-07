---
title: sam::SubjectiveOutlierRemoval
summary: The subjective outlier removal refers to a type of outliers removal where the researcher continiously lowers the threshold of identifying an outlier, k, until it finds a significant (or satisfactory) result.  

---

# sam::SubjectiveOutlierRemoval


**Module:** **[Hacking Strategies](/doxygen/Modules/group___hacking_strategies/)**

The subjective outlier removal refers to a type of outliers removal where the researcher continiously lowers the threshold of identifying an outlier, `k`, until it finds a significant (or satisfactory) result.  [More...](#detailed-description)


`#include <HackingStrategy.h>`


Inherits from [sam::HackingStrategy](/doxygen/Classes/classsam_1_1_hacking_strategy/)



## Public Classes

|                | Name           |
| -------------- | -------------- |
| struct | **[Parameters](/doxygen/Classes/structsam_1_1_subjective_outlier_removal_1_1_parameters/)** <br>[SubjectiveOutlierRemoval](/doxygen/Classes/classsam_1_1_subjective_outlier_removal/)'s parameters.  |








## Public Functions

|                | Name           |
| -------------- | -------------- |
|  | **[SubjectiveOutlierRemoval](/doxygen/Classes/classsam_1_1_subjective_outlier_removal/#function-subjectiveoutlierremoval)**() =default  |
|  | **[SubjectiveOutlierRemoval](/doxygen/Classes/classsam_1_1_subjective_outlier_removal/#function-subjectiveoutlierremoval)**(const [Parameters](/doxygen/Classes/structsam_1_1_subjective_outlier_removal_1_1_parameters/) & p)  |


## Public Attributes

|                | Name           |
| -------------- | -------------- |
| [Parameters](/doxygen/Classes/structsam_1_1_subjective_outlier_removal_1_1_parameters/) | **[params](/doxygen/Classes/classsam_1_1_subjective_outlier_removal/#variable-params)**  |
| [PolicyChain](/doxygen/Classes/structsam_1_1_policy_chain/) | **[stopping_condition](/doxygen/Classes/classsam_1_1_subjective_outlier_removal/#variable-stopping_condition)**  |




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
class sam::SubjectiveOutlierRemoval;
```

The subjective outlier removal refers to a type of outliers removal where the researcher continiously lowers the threshold of identifying an outlier, `k`, until it finds a significant (or satisfactory) result. 






**See**: [DecisionStrategy](/doxygen/Classes/classsam_1_1_decision_strategy/)





























## Public Functions Documentation

### function `SubjectiveOutlierRemoval`

```cpp
SubjectiveOutlierRemoval() =default
```





























### function `SubjectiveOutlierRemoval`

```cpp
inline SubjectiveOutlierRemoval(
    const Parameters & p
)
```































## Public Attributes Documentation

### variable `params`

```cpp
Parameters params;
```





























### variable `stopping_condition`

```cpp
PolicyChain stopping_condition;
```

































