---
title: sam::FalsifyingData::Parameters


---

# sam::FalsifyingData::Parameters


**Module:** **[Hacking Strategies Parameters](/doxygen/Modules/group___hacking_strategies_parameters/)**

 [More...](#detailed-description)


`#include <HackingStrategy.h>`















## Public Attributes

|                | Name           |
| -------------- | -------------- |
| HackingMethod | **[name](/doxygen/Classes/structsam_1_1_falsifying_data_1_1_parameters/#variable-name)**  |
| std::string | **[approach](/doxygen/Classes/structsam_1_1_falsifying_data_1_1_parameters/#variable-approach)**  |
| std::string | **[switching_direction](/doxygen/Classes/structsam_1_1_falsifying_data_1_1_parameters/#variable-switching_direction)**  |
| std::string | **[selection_method](/doxygen/Classes/structsam_1_1_falsifying_data_1_1_parameters/#variable-selection_method)**  |
| HackingTarget | **[target](/doxygen/Classes/structsam_1_1_falsifying_data_1_1_parameters/#variable-target)**  |
| int | **[n_attempts](/doxygen/Classes/structsam_1_1_falsifying_data_1_1_parameters/#variable-n_attempts)** <br>Number of trials.  |
| size_t | **[num](/doxygen/Classes/structsam_1_1_falsifying_data_1_1_parameters/#variable-num)** <br>Number of observations to be purturbed.  |
| std::optional< Distribution > | **[noise_dist](/doxygen/Classes/structsam_1_1_falsifying_data_1_1_parameters/#variable-noise_dist)** <br>Distribution of noise.  |
| std::vector< std::string > | **[stopping_cond_defs](/doxygen/Classes/structsam_1_1_falsifying_data_1_1_parameters/#variable-stopping_cond_defs)** <br>Stopping condition [PolicyChain]() definitions.  |
| double | **[defensibility](/doxygen/Classes/structsam_1_1_falsifying_data_1_1_parameters/#variable-defensibility)**  |
| double | **[prevalence](/doxygen/Classes/structsam_1_1_falsifying_data_1_1_parameters/#variable-prevalence)**  |
| HackingStage | **[stage](/doxygen/Classes/structsam_1_1_falsifying_data_1_1_parameters/#variable-stage)**  |






## Detailed Description

```cpp
struct sam::FalsifyingData::Parameters;
```



























Falsifying Data [Parameters](/doxygen/Classes/structsam_1_1_falsifying_data_1_1_parameters/)

Example usage: 

```cpp
{
  "name": "FalsifyingData",
}
```

_Filename: .json_











## Public Attributes Documentation

### variable name

```cpp
HackingMethod name = HackingMethod::FalsifyingData;
```





























### variable approach

```cpp
std::string approach {"perturbation"};
```



























Falsification approach. We've discussed two possible way of doing this

* perturbation, perturbing a value
* group swapping, swapping values between groups
* group switching, moving values between groups 


### variable switching_direction

```cpp
std::string switching_direction {"control-to-treatment"};
```



























Switching direction

* control-to-treatment
* treatment-to-control 


### variable selection_method

```cpp
std::string selection_method {"random"};
```



























Swapping Method

* random
* smart 


### variable target

```cpp
HackingTarget target {HackingTarget::Both};
```



























Indicates which outcome variables are going to be targeted,

* control
* treatment
* both 


### variable n_attempts

```cpp
int n_attempts {1};
```

Number of trials. 















**Todo**: To be implemented 











Indicates a set of rule that is going to be used to select the target group 


### variable num

```cpp
size_t num {5};
```

Number of observations to be purturbed. 




























### variable noise_dist

```cpp
std::optional< Distribution > noise_dist = make_distribution({
      {"dist", "normal_distribution"},
      {"mean", 0},
      {"stddev", 0.1}
    });
```

Distribution of noise. 




























### variable stopping_cond_defs

```cpp
std::vector< std::string > stopping_cond_defs;
```

Stopping condition [PolicyChain]() definitions. 




























### variable defensibility

```cpp
double defensibility {0.05};
```





























### variable prevalence

```cpp
double prevalence {0.1};
```





























### variable stage

```cpp
HackingStage stage {HackingStage::PostProcessing};
```

































-------------------------------

Updated on  3 December 2020 at 12:37:29 CET