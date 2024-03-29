---
title: sam::SubjectiveOutlierRemoval::Parameters
summary: SubjectiveOutlierRemoval's parameters. 

---

# sam::SubjectiveOutlierRemoval::Parameters

**Module:** **[Parameters of Hacking Strategies](/doxygen/Modules/group___hacking_strategies_parameters/)**



[SubjectiveOutlierRemoval](/doxygen/Classes/classsam_1_1_subjective_outlier_removal/)'s parameters.  [More...](#detailed-description)


`#include <HackingStrategy.h>`

## Public Attributes

|                | Name           |
| -------------- | -------------- |
| HackingMethod | **[name](/doxygen/Classes/structsam_1_1_subjective_outlier_removal_1_1_parameters/#variable-name)** <br>A placeholder for the name.  |
| HackingTarget | **[target](/doxygen/Classes/structsam_1_1_subjective_outlier_removal_1_1_parameters/#variable-target)**  |
| std::vector< int > | **[range](/doxygen/Classes/structsam_1_1_subjective_outlier_removal_1_1_parameters/#variable-range)** <br>A vector of `{min, max}`, defining the range of `K`.  |
| float | **[step_size](/doxygen/Classes/structsam_1_1_subjective_outlier_removal_1_1_parameters/#variable-step_size)** <br>Indicates the step size of walking through K's.  |
| int | **[min_observations](/doxygen/Classes/structsam_1_1_subjective_outlier_removal_1_1_parameters/#variable-min_observations)** <br>Indicates minimum number of observations.  |
| std::vector< std::string > | **[stopping_cond_defs](/doxygen/Classes/structsam_1_1_subjective_outlier_removal_1_1_parameters/#variable-stopping_cond_defs)** <br>Stopping condition [PolicyChain]() definitions.  |
| std::optional< float > | **[prevalence](/doxygen/Classes/structsam_1_1_subjective_outlier_removal_1_1_parameters/#variable-prevalence)** <br>The prevalence factor of the strategy.  |
| std::optional< float > | **[defensibility](/doxygen/Classes/structsam_1_1_subjective_outlier_removal_1_1_parameters/#variable-defensibility)** <br>The defensibility factor of the strategy.  |
| HackingStage | **[stage](/doxygen/Classes/structsam_1_1_subjective_outlier_removal_1_1_parameters/#variable-stage)**  |

## Detailed Description

```cpp
struct sam::SubjectiveOutlierRemoval::Parameters;
```

[SubjectiveOutlierRemoval](/doxygen/Classes/classsam_1_1_subjective_outlier_removal/)'s parameters. 

These are parameters specific to this hacking strategy. You can set them either pragmatically when you are constructing a new [SubjectiveOutlierRemoval](/doxygen/Classes/classsam_1_1_subjective_outlier_removal/), e.g., `[SubjectiveOutlierRemoval](/doxygen/Classes/classsam_1_1_subjective_outlier_removal/) sor{<name>, {min, max}, ssize};`.

Or, when you are using `SAMrun` to run your simulation. In this case, your JSON variable must comply with the name and type of parameters here. For example, the following JSON defines the default subjective outliers removal.



```cpp
{
   "name": "SubjectiveOutlierRemoval",
   "range": [2, 4],
   "step_size": 0.1,
   "min_observations": 5
}
```

_Filename: .json_

## Public Attributes Documentation

### variable name

```cpp
HackingMethod name = HackingMethod::SubjectiveOutlierRemoval;
```

A placeholder for the name. 

### variable target

```cpp
HackingTarget target {HackingTarget::Both};
```


**Todo**: TO BE IMPLEMENTED 

### variable range

```cpp
std::vector< int > range;
```

A vector of `{min, max}`, defining the range of `K`. 

### variable step_size

```cpp
float step_size;
```

Indicates the step size of walking through K's. 

### variable min_observations

```cpp
int min_observations;
```

Indicates minimum number of observations. 

### variable stopping_cond_defs

```cpp
std::vector< std::string > stopping_cond_defs {{"sig"}};
```

Stopping condition [PolicyChain]() definitions. 

### variable prevalence

```cpp
std::optional< float > prevalence;
```

The prevalence factor of the strategy. 

### variable defensibility

```cpp
std::optional< float > defensibility;
```

The defensibility factor of the strategy. 

### variable stage

```cpp
HackingStage stage {HackingStage::PostProcessing};
```


-------------------------------

Updated on 29 June 2021 at 16:13:47 CEST