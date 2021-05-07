---
title: sam::EggersTestEstimator::Parameters
summary: Parameters of the EggersTestEstimator. 

---

# sam::EggersTestEstimator::Parameters

**Module:** **[Parameters of Meta Anlaysis Methods](/doxygen/Modules/group___meta_analysis_parameters/)**



[Parameters]() of the [EggersTestEstimator](/doxygen/Classes/classsam_1_1_eggers_test_estimator/).  [More...](#detailed-description)


`#include <MetaAnalysis.h>`

## Public Functions

|                | Name           |
| -------------- | -------------- |
| | **[NLOHMANN_DEFINE_TYPE_INTRUSIVE](/doxygen/Classes/structsam_1_1_eggers_test_estimator_1_1_parameters/#function-nlohmann_define_type_intrusive)**([EggersTestEstimator::Parameters](/doxygen/Classes/structsam_1_1_eggers_test_estimator_1_1_parameters/) , name , [alpha](/doxygen/Classes/structsam_1_1_eggers_test_estimator_1_1_parameters/#variable-alpha) ) |

## Public Attributes

|                | Name           |
| -------------- | -------------- |
| std::string | **[name](/doxygen/Classes/structsam_1_1_eggers_test_estimator_1_1_parameters/#variable-name)**  |
| double | **[alpha](/doxygen/Classes/structsam_1_1_eggers_test_estimator_1_1_parameters/#variable-alpha)** <br>The ɑ of the test.  |

## Detailed Description

```cpp
struct sam::EggersTestEstimator::Parameters;
```

[Parameters]() of the [EggersTestEstimator](/doxygen/Classes/classsam_1_1_eggers_test_estimator/). 

While Egger's test is often performed with ɑ = 0.1, it's possible to change the ɑ using the [alpha](/doxygen/Classes/structsam_1_1_eggers_test_estimator_1_1_parameters/#variable-alpha) parameter. 

## Public Functions Documentation

### function NLOHMANN_DEFINE_TYPE_INTRUSIVE

```cpp
NLOHMANN_DEFINE_TYPE_INTRUSIVE(
    EggersTestEstimator::Parameters ,
    name ,
    alpha 
)
```


## Public Attributes Documentation

### variable name

```cpp
std::string name {"EggersTestEstimator"};
```


### variable alpha

```cpp
double alpha {0.10};
```

The ɑ of the test. 

-------------------------------

Updated on  7 May 2021 at 14:51:32 CEST