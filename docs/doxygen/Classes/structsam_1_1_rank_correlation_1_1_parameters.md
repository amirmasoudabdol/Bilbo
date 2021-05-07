---
title: sam::RankCorrelation::Parameters
summary: Parameters of RankCorrelation. 

---

# sam::RankCorrelation::Parameters

**Module:** **[Parameters of Meta Anlaysis Methods](/doxygen/Modules/group___meta_analysis_parameters/)**



[Parameters]() of [RankCorrelation](/doxygen/Classes/classsam_1_1_rank_correlation/). 
`#include <MetaAnalysis.h>`

## Public Functions

|                | Name           |
| -------------- | -------------- |
| | **[NLOHMANN_DEFINE_TYPE_INTRUSIVE](/doxygen/Classes/structsam_1_1_rank_correlation_1_1_parameters/#function-nlohmann_define_type_intrusive)**([RankCorrelation::Parameters](/doxygen/Classes/structsam_1_1_rank_correlation_1_1_parameters/) , name , alternative , [alpha](/doxygen/Classes/structsam_1_1_rank_correlation_1_1_parameters/#variable-alpha) ) |

## Public Attributes

|                | Name           |
| -------------- | -------------- |
| std::string | **[name](/doxygen/Classes/structsam_1_1_rank_correlation_1_1_parameters/#variable-name)**  |
| [TestStrategy::TestAlternative](/doxygen/Classes/classsam_1_1_test_strategy/#enum-testalternative) | **[alternative](/doxygen/Classes/structsam_1_1_rank_correlation_1_1_parameters/#variable-alternative)**  |
| double | **[alpha](/doxygen/Classes/structsam_1_1_rank_correlation_1_1_parameters/#variable-alpha)** <br>The ɑ of the test.  |

## Public Functions Documentation

### function NLOHMANN_DEFINE_TYPE_INTRUSIVE

```cpp
NLOHMANN_DEFINE_TYPE_INTRUSIVE(
    RankCorrelation::Parameters ,
    name ,
    alternative ,
    alpha 
)
```


## Public Attributes Documentation

### variable name

```cpp
std::string name {"RankCorrelation"};
```


### variable alternative

```cpp
TestStrategy::TestAlternative alternative = TestStrategy::TestAlternative::TwoSided;
```


### variable alpha

```cpp
double alpha {0.10};
```

The ɑ of the test. 

-------------------------------

Updated on  7 May 2021 at 14:51:32 CEST