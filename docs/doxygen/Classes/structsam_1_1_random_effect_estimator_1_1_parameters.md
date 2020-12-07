---
title: sam::RandomEffectEstimator::Parameters
summary: Parameters of the RandomEffectEstimator.  

---

# sam::RandomEffectEstimator::Parameters


**Module:** **[Parameters of Meta Anlaysis Methods](/doxygen/Modules/group___meta_analysis_parameters/)**

[Parameters]() of the [RandomEffectEstimator](/doxygen/Classes/classsam_1_1_random_effect_estimator/). 

`#include <MetaAnalysis.h>`













## Public Functions

|                | Name           |
| -------------- | -------------- |
|  | **[NLOHMANN_DEFINE_TYPE_INTRUSIVE](/doxygen/Classes/structsam_1_1_random_effect_estimator_1_1_parameters/#function-nlohmann_define_type_intrusive)**([RandomEffectEstimator::Parameters](/doxygen/Classes/structsam_1_1_random_effect_estimator_1_1_parameters/) , name , [estimator](/doxygen/Classes/structsam_1_1_random_effect_estimator_1_1_parameters/#variable-estimator) )  |


## Public Attributes

|                | Name           |
| -------------- | -------------- |
| std::string | **[name](/doxygen/Classes/structsam_1_1_random_effect_estimator_1_1_parameters/#variable-name)**  |
| std::string | **[estimator](/doxygen/Classes/structsam_1_1_random_effect_estimator_1_1_parameters/#variable-estimator)** <br>The random effect estimator.  |














## Public Functions Documentation

### function NLOHMANN_DEFINE_TYPE_INTRUSIVE

```cpp
NLOHMANN_DEFINE_TYPE_INTRUSIVE(
    RandomEffectEstimator::Parameters ,
    name ,
    estimator 
)
```































## Public Attributes Documentation

### variable name

```cpp
std::string name {"RandomEffectEstimator"};
```





























### variable estimator

```cpp
std::string estimator {"DL"};
```

The random effect estimator. 
































-------------------------------

Updated on  7 December 2020 at 13:20:10 CET