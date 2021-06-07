---
title: sam::QuestionableRounding::Parameters

---

# sam::QuestionableRounding::Parameters

**Module:** **[Parameters of Hacking Strategies](/doxygen/Modules/group___hacking_strategies_parameters/)**



 [More...](#detailed-description)


`#include <HackingStrategy.h>`

## Public Functions

|                | Name           |
| -------------- | -------------- |
| | **[NLOHMANN_DEFINE_TYPE_INTRUSIVE](/doxygen/Classes/structsam_1_1_questionable_rounding_1_1_parameters/#function-nlohmann_define_type_intrusive)**([QuestionableRounding::Parameters](/doxygen/Classes/structsam_1_1_questionable_rounding_1_1_parameters/) , name , [threshold](/doxygen/Classes/structsam_1_1_questionable_rounding_1_1_parameters/#variable-threshold) , [rounding_method](/doxygen/Classes/structsam_1_1_questionable_rounding_1_1_parameters/#variable-rounding_method) , prevalence , defensibility , stage ) |

## Public Attributes

|                | Name           |
| -------------- | -------------- |
| HackingMethod | **[name](/doxygen/Classes/structsam_1_1_questionable_rounding_1_1_parameters/#variable-name)**  |
| double | **[threshold](/doxygen/Classes/structsam_1_1_questionable_rounding_1_1_parameters/#variable-threshold)**  |
| std::string | **[rounding_method](/doxygen/Classes/structsam_1_1_questionable_rounding_1_1_parameters/#variable-rounding_method)**  |
| double | **[prevalence](/doxygen/Classes/structsam_1_1_questionable_rounding_1_1_parameters/#variable-prevalence)**  |
| double | **[defensibility](/doxygen/Classes/structsam_1_1_questionable_rounding_1_1_parameters/#variable-defensibility)**  |
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

## Public Functions Documentation

### function NLOHMANN_DEFINE_TYPE_INTRUSIVE

```cpp
NLOHMANN_DEFINE_TYPE_INTRUSIVE(
    QuestionableRounding::Parameters ,
    name ,
    threshold ,
    rounding_method ,
    prevalence ,
    defensibility ,
    stage 
)
```


**Note**: While this mostly works fine, there is one drawback that it cannot handle missing argument. The change is in nlohmann list and when released, I can use optional and this macro will handle everything just fine 

This is a helper macro that generates from/to_json methods for this struct. 


## Public Attributes Documentation

### variable name

```cpp
HackingMethod name = HackingMethod::QuestionableRounding;
```


### variable threshold

```cpp
double threshold {0.005};
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
double prevalence {0.9};
```


### variable defensibility

```cpp
double defensibility {0.7};
```


### variable stage

```cpp
HackingStage stage {HackingStage::Reporting};
```


-------------------------------

Updated on  7 June 2021 at 12:00:21 CEST