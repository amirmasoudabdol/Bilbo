---
title: sam::OutliersRemoval::Parameters


---

# sam::OutliersRemoval::Parameters


**Module:** **[Parameters of Hacking Strategies](/doxygen/Modules/group___hacking_strategies_parameters/)**

 [More...](#detailed-description)


`#include <HackingStrategy.h>`















## Public Attributes

|                | Name           |
| -------------- | -------------- |
| HackingMethod | **[name](/doxygen/Classes/structsam_1_1_outliers_removal_1_1_parameters/#variable-name)**  |
| HackingTarget | **[target](/doxygen/Classes/structsam_1_1_outliers_removal_1_1_parameters/#variable-target)** <br>TO BE IMPLEMENTED!  |
| std::string | **[order](/doxygen/Classes/structsam_1_1_outliers_removal_1_1_parameters/#variable-order)**  |
| int | **[num](/doxygen/Classes/structsam_1_1_outliers_removal_1_1_parameters/#variable-num)** <br>Indicates the number of outliers to be removed in each iteration.  |
| int | **[n_attempts](/doxygen/Classes/structsam_1_1_outliers_removal_1_1_parameters/#variable-n_attempts)**  |
| int | **[min_observations](/doxygen/Classes/structsam_1_1_outliers_removal_1_1_parameters/#variable-min_observations)** <br>Indicates the minimum number of observations allowed during the process.  |
| std::vector< double > | **[multipliers](/doxygen/Classes/structsam_1_1_outliers_removal_1_1_parameters/#variable-multipliers)** <br>A list of standard deviation multipliers for identidying outliers.  |
| std::vector< std::string > | **[stopping_cond_defs](/doxygen/Classes/structsam_1_1_outliers_removal_1_1_parameters/#variable-stopping_cond_defs)** <br>Stopping condition [PolicyChain]() definitions.  |
| double | **[defensibility](/doxygen/Classes/structsam_1_1_outliers_removal_1_1_parameters/#variable-defensibility)**  |
| double | **[prevalence](/doxygen/Classes/structsam_1_1_outliers_removal_1_1_parameters/#variable-prevalence)**  |
| HackingStage | **[stage](/doxygen/Classes/structsam_1_1_outliers_removal_1_1_parameters/#variable-stage)**  |






## Detailed Description

```cpp
struct sam::OutliersRemoval::Parameters;
```



























[Parameters](/doxygen/Classes/structsam_1_1_outliers_removal_1_1_parameters/) of Outliers Removal Strategy



```cpp
{
    "name": "OutliersRemoval",
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
HackingMethod name = HackingMethod::OutliersRemoval;
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
int num {3};
```

Indicates the number of outliers to be removed in each iteration. 




























### variable n_attempts

```cpp
int n_attempts {1};
```



























Indicates the total number of attempts, i.e., _iterations_, to remove outliers 


### variable min_observations

```cpp
int min_observations {15};
```

Indicates the minimum number of observations allowed during the process. 




























### variable multipliers

```cpp
std::vector< double > multipliers = {3};
```

A list of standard deviation multipliers for identidying outliers. 




























### variable stopping_cond_defs

```cpp
std::vector< std::string > stopping_cond_defs;
```

Stopping condition [PolicyChain]() definitions. 




























### variable defensibility

```cpp
double defensibility {0.5};
```





























### variable prevalence

```cpp
double prevalence {0.7};
```





























### variable stage

```cpp
HackingStage stage {HackingStage::PostProcessing};
```

































-------------------------------

Updated on  7 December 2020 at 13:20:10 CET