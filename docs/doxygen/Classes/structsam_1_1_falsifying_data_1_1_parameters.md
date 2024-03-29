---
title: sam::FalsifyingData::Parameters

---

# sam::FalsifyingData::Parameters

**Module:** **[Parameters of Hacking Strategies](/doxygen/Modules/group___hacking_strategies_parameters/)**



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
| size_t | **[num](/doxygen/Classes/structsam_1_1_falsifying_data_1_1_parameters/#variable-num)** <br>Number of observations to be perturbed.  |
| std::optional< UnivariateDistribution > | **[noise_dist](/doxygen/Classes/structsam_1_1_falsifying_data_1_1_parameters/#variable-noise_dist)** <br>Distribution of noise.  |
| std::vector< std::string > | **[stopping_cond_defs](/doxygen/Classes/structsam_1_1_falsifying_data_1_1_parameters/#variable-stopping_cond_defs)** <br>Stopping condition [PolicyChain]() definitions.  |
| std::optional< float > | **[defensibility](/doxygen/Classes/structsam_1_1_falsifying_data_1_1_parameters/#variable-defensibility)** <br>The defensibility factor of the strategy.  |
| std::optional< float > | **[prevalence](/doxygen/Classes/structsam_1_1_falsifying_data_1_1_parameters/#variable-prevalence)** <br>The prevalence factor of the strategy.  |
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
size_t num;
```

Number of observations to be perturbed. 

### variable noise_dist

```cpp
std::optional< UnivariateDistribution > noise_dist = [makeUnivariateDistribution](/doxygen/Files/_distributions_8h/#function-makeunivariatedistribution)({
      {"dist", "normal_distribution"},
      {"mean", 0},
      {"stddev", 1}
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
std::optional< float > defensibility;
```

The defensibility factor of the strategy. 

### variable prevalence

```cpp
std::optional< float > prevalence;
```

The prevalence factor of the strategy. 

### variable stage

```cpp
HackingStage stage {HackingStage::PostProcessing};
```


-------------------------------

Updated on 29 June 2021 at 16:13:47 CEST