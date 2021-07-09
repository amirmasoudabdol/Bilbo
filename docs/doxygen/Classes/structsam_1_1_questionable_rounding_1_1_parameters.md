---
title: sam::QuestionableRounding::Parameters

---

# sam::QuestionableRounding::Parameters

**Module:** **[Parameters of Hacking Strategies](/doxygen/Modules/group___hacking_strategies_parameters/)**



 [More...](#detailed-description)


`#include <HackingStrategy.h>`

## Public Attributes

|                | Name           |
| -------------- | -------------- |
| HackingMethod | **[name](/doxygen/Classes/structsam_1_1_questionable_rounding_1_1_parameters/#variable-name)**  |
| HackingTarget | **[target](/doxygen/Classes/structsam_1_1_questionable_rounding_1_1_parameters/#variable-target)**  |
| float | **[threshold](/doxygen/Classes/structsam_1_1_questionable_rounding_1_1_parameters/#variable-threshold)**  |
| std::string | **[rounding_method](/doxygen/Classes/structsam_1_1_questionable_rounding_1_1_parameters/#variable-rounding_method)**  |
| std::optional< float > | **[prevalence](/doxygen/Classes/structsam_1_1_questionable_rounding_1_1_parameters/#variable-prevalence)** <br>The prevalence factor of the strategy.  |
| std::optional< float > | **[defensibility](/doxygen/Classes/structsam_1_1_questionable_rounding_1_1_parameters/#variable-defensibility)** <br>The defensibility factor of the strategy.  |
| HackingStage | **[stage](/doxygen/Classes/structsam_1_1_questionable_rounding_1_1_parameters/#variable-stage)**  |

## Detailed Description

```cpp
struct sam::QuestionableRounding::Parameters;
```


Questionable Rounding [Parameters](/doxygen/Classes/structsam_1_1_questionable_rounding_1_1_parameters/)

Example usage: 

```cpp
{
  "name": "QuestionableRounding",
  "rounding_method": "alpha",
  "threshold": 0.01,
  "prevalence": 0.1,
  "defensibility": 0.9,
  "stage": "Reporting"
}
```

_Filename: .json_

## Public Attributes Documentation

### variable name

```cpp
HackingMethod name = HackingMethod::QuestionableRounding;
```


### variable target

```cpp
HackingTarget target {HackingTarget::Treatment};
```


### variable threshold

```cpp
float threshold;
```


Indicates the distance between the pvalue and alpha by which the researcher considers to round the pvalue to significance 


### variable rounding_method

```cpp
std::string rounding_method = "diff";
```


Rounding Method

* diff: Setting the rounded p-value to the difference between pvalue and threshold
* alpha: Setting the rounded p-value to the value of alpha
TodoI cna possibly add more methods here, e.g.,


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
HackingStage stage {HackingStage::Reporting};
```


-------------------------------

Updated on 29 June 2021 at 16:13:47 CEST