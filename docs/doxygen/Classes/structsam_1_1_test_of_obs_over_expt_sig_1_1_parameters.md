---
title: sam::TestOfObsOverExptSig::Parameters

---

# sam::TestOfObsOverExptSig::Parameters

**Module:** **[Parameters of Meta Anlaysis Methods](/doxygen/Modules/group___meta_analysis_parameters/)**



 [More...](#detailed-description)


`#include <MetaAnalysis.h>`

## Public Functions

|                | Name           |
| -------------- | -------------- |
| | **[NLOHMANN_DEFINE_TYPE_INTRUSIVE](/doxygen/Classes/structsam_1_1_test_of_obs_over_expt_sig_1_1_parameters/#function-nlohmann_define_type_intrusive)**([TestOfObsOverExptSig::Parameters](/doxygen/Classes/structsam_1_1_test_of_obs_over_expt_sig_1_1_parameters/) , name , alpha ) |

## Public Attributes

|                | Name           |
| -------------- | -------------- |
| std::string | **[name](/doxygen/Classes/structsam_1_1_test_of_obs_over_expt_sig_1_1_parameters/#variable-name)**  |
| float | **[alpha](/doxygen/Classes/structsam_1_1_test_of_obs_over_expt_sig_1_1_parameters/#variable-alpha)**  |

## Detailed Description

```cpp
struct sam::TestOfObsOverExptSig::Parameters;
```


[Parameters](/doxygen/Classes/structsam_1_1_test_of_obs_over_expt_sig_1_1_parameters/) of [TestOfObsOverExptSig](/doxygen/Classes/classsam_1_1_test_of_obs_over_expt_sig/)

## Public Functions Documentation

### function NLOHMANN_DEFINE_TYPE_INTRUSIVE

```cpp
NLOHMANN_DEFINE_TYPE_INTRUSIVE(
    TestOfObsOverExptSig::Parameters ,
    name ,
    alpha 
)
```


## Public Attributes Documentation

### variable name

```cpp
std::string name {"TestOfObsOverExptSig"};
```


### variable alpha

```cpp
float alpha {0.10};
```


-------------------------------

Updated on 29 June 2021 at 16:13:48 CEST