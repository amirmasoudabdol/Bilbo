---
title: sam::PeekingOutliersRemoval::Parameters

---

# sam::PeekingOutliersRemoval::Parameters

**Module:** **[Parameters of Hacking Strategies](/doxygen/Modules/group___hacking_strategies_parameters/)**



 [More...](#detailed-description)


`#include <HackingStrategy.h>`

## Public Attributes

|                | Name           |
| -------------- | -------------- |
| HackingMethod | **[name](/doxygen/Classes/structsam_1_1_peeking_outliers_removal_1_1_parameters/#variable-name)**  |
| HackingTarget | **[target](/doxygen/Classes/structsam_1_1_peeking_outliers_removal_1_1_parameters/#variable-target)** <br>TO BE IMPLEMENTED!  |
| std::string | **[order](/doxygen/Classes/structsam_1_1_peeking_outliers_removal_1_1_parameters/#variable-order)**  |
| int | **[num](/doxygen/Classes/structsam_1_1_peeking_outliers_removal_1_1_parameters/#variable-num)** <br>Indicates the number of outliers to be removed in each iteration.  |
| int | **[n_attempts](/doxygen/Classes/structsam_1_1_peeking_outliers_removal_1_1_parameters/#variable-n_attempts)**  |
| int | **[min_observations](/doxygen/Classes/structsam_1_1_peeking_outliers_removal_1_1_parameters/#variable-min_observations)** <br>Indicates the minimum number of observations allowed during the process.  |
| std::vector< float > | **[multipliers](/doxygen/Classes/structsam_1_1_peeking_outliers_removal_1_1_parameters/#variable-multipliers)** <br>A list of standard deviation multipliers for identifying outliers.  |
| std::vector< std::string > | **[stopping_cond_defs](/doxygen/Classes/structsam_1_1_peeking_outliers_removal_1_1_parameters/#variable-stopping_cond_defs)** <br>Stopping condition [PolicyChain]() definitions.  |
| std::vector< std::string > | **[whether_to_save_cond_defs](/doxygen/Classes/structsam_1_1_peeking_outliers_removal_1_1_parameters/#variable-whether_to_save_cond_defs)** <br>Removing if.  |
| std::optional< float > | **[prevalence](/doxygen/Classes/structsam_1_1_peeking_outliers_removal_1_1_parameters/#variable-prevalence)** <br>The prevalence factor of the strategy.  |
| std::optional< float > | **[defensibility](/doxygen/Classes/structsam_1_1_peeking_outliers_removal_1_1_parameters/#variable-defensibility)** <br>The defensibility factor of the strategy.  |
| HackingStage | **[stage](/doxygen/Classes/structsam_1_1_peeking_outliers_removal_1_1_parameters/#variable-stage)**  |

## Detailed Description

```cpp
struct sam::PeekingOutliersRemoval::Parameters;
```


Peaking Outliers Removal [Parameters](/doxygen/Classes/structsam_1_1_peeking_outliers_removal_1_1_parameters/)

Example usage: 

```cpp
{
  "name": "PeekingOutliersRemoval",
   "level": "dv",
   "min_observations": 10,
   "multipliers": [
       0.5
   ],
   "n_attempts": 1000,
   "num": 1000,
   "order": "random"
}
```

_Filename: .json_

## Public Attributes Documentation

### variable name

```cpp
HackingMethod name = HackingMethod::PeekingOutliersRemoval;
```


### variable target

```cpp
HackingTarget target {HackingTarget::Both};
```

TO BE IMPLEMENTED! 

### variable order

```cpp
std::string order {"max first"};
```


Indicates the order where outliers are going to be removed from the experiment. 

* `max first`, removes the biggest outlier first 
* `random`, removes the first outlier first, this is as a random outlier is being removed 


### variable num

```cpp
int num;
```

Indicates the number of outliers to be removed in each iteration. 

### variable n_attempts

```cpp
int n_attempts {1};
```


Indicates the total number of attempts, i.e., _iterations_, to remove outliers 


### variable min_observations

```cpp
int min_observations;
```

Indicates the minimum number of observations allowed during the process. 

### variable multipliers

```cpp
std::vector< float > multipliers;
```

A list of standard deviation multipliers for identifying outliers. 

### variable stopping_cond_defs

```cpp
std::vector< std::string > stopping_cond_defs;
```

Stopping condition [PolicyChain]() definitions. 

### variable whether_to_save_cond_defs

```cpp
std::vector< std::string > whether_to_save_cond_defs;
```

Removing if. 

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