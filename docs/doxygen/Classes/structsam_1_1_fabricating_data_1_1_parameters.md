---
title: sam::FabricatingData::Parameters

---

# sam::FabricatingData::Parameters

**Module:** **[Parameters of Hacking Strategies](/doxygen/Modules/group___hacking_strategies_parameters/)**



 [More...](#detailed-description)


`#include <HackingStrategy.h>`

## Public Attributes

|                | Name           |
| -------------- | -------------- |
| HackingMethod | **[name](/doxygen/Classes/structsam_1_1_fabricating_data_1_1_parameters/#variable-name)**  |
| std::string | **[approach](/doxygen/Classes/structsam_1_1_fabricating_data_1_1_parameters/#variable-approach)**  |
| HackingTarget | **[target](/doxygen/Classes/structsam_1_1_fabricating_data_1_1_parameters/#variable-target)**  |
| int | **[n_attempts](/doxygen/Classes/structsam_1_1_fabricating_data_1_1_parameters/#variable-n_attempts)** <br>Number of trials.  |
| int | **[num](/doxygen/Classes/structsam_1_1_fabricating_data_1_1_parameters/#variable-num)** <br>Number of observations to be perturbed.  |
| std::optional< UnivariateDistribution > | **[dist](/doxygen/Classes/structsam_1_1_fabricating_data_1_1_parameters/#variable-dist)**  |
| std::vector< std::string > | **[stopping_cond_defs](/doxygen/Classes/structsam_1_1_fabricating_data_1_1_parameters/#variable-stopping_cond_defs)** <br>Stopping condition [PolicyChain]() definitions.  |
| std::optional< float > | **[defensibility](/doxygen/Classes/structsam_1_1_fabricating_data_1_1_parameters/#variable-defensibility)** <br>The defensibility factor of the strategy  |
| std::optional< float > | **[prevalence](/doxygen/Classes/structsam_1_1_fabricating_data_1_1_parameters/#variable-prevalence)** <br>The prevalence factor of the strategy.  |
| HackingStage | **[stage](/doxygen/Classes/structsam_1_1_fabricating_data_1_1_parameters/#variable-stage)**  |

## Detailed Description

```cpp
struct sam::FabricatingData::Parameters;
```


Fabricating Data [Parameters](/doxygen/Classes/structsam_1_1_fabricating_data_1_1_parameters/)

Example usage: 

```cpp
{
  "name": "FabricatingData",
}
```

_Filename: .json_

## Public Attributes Documentation

### variable name

```cpp
HackingMethod name = HackingMethod::FabricatingData;
```


### variable approach

```cpp
std::string approach {"generating"};
```


Falsification approach. We've discussed two possible way of doing this

* generating, perturbing a value
* duplicating, swapping values between groups 


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
int num;
```

Number of observations to be perturbed. 

### variable dist

```cpp
std::optional< UnivariateDistribution > dist;
```


**Todo**: Check if this is even necessary, I think in most cases, we can probably just use the data_strategy and get over it 

Distribution of fabricated data 


### variable stopping_cond_defs

```cpp
std::vector< std::string > stopping_cond_defs;
```

Stopping condition [PolicyChain]() definitions. 

### variable defensibility

```cpp
std::optional< float > defensibility;
```

The defensibility factor of the strategy 

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