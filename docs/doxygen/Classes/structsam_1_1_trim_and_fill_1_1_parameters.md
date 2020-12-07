---
title: sam::TrimAndFill::Parameters
summary: Parameters of the TrimAndFill.  

---

# sam::TrimAndFill::Parameters




[Parameters]() of the [TrimAndFill](/doxygen/Classes/classsam_1_1_trim_and_fill/). 

`#include <MetaAnalysis.h>`













## Public Functions

|                | Name           |
| -------------- | -------------- |
|  | **[NLOHMANN_DEFINE_TYPE_INTRUSIVE](/doxygen/Classes/structsam_1_1_trim_and_fill_1_1_parameters/#function-nlohmann_define_type_intrusive)**([TrimAndFill::Parameters](/doxygen/Classes/structsam_1_1_trim_and_fill_1_1_parameters/) , name , [side](/doxygen/Classes/structsam_1_1_trim_and_fill_1_1_parameters/#variable-side) , [estimator](/doxygen/Classes/structsam_1_1_trim_and_fill_1_1_parameters/#variable-estimator) , [alpha](/doxygen/Classes/structsam_1_1_trim_and_fill_1_1_parameters/#variable-alpha) )  |


## Public Attributes

|                | Name           |
| -------------- | -------------- |
| std::string | **[name](/doxygen/Classes/structsam_1_1_trim_and_fill_1_1_parameters/#variable-name)**  |
| std::string | **[side](/doxygen/Classes/structsam_1_1_trim_and_fill_1_1_parameters/#variable-side)** <br>Indicates the side of the funnel plot where missing values should be imputed.  |
| std::string | **[estimator](/doxygen/Classes/structsam_1_1_trim_and_fill_1_1_parameters/#variable-estimator)** <br>The symmetry estimator.  |
| double | **[alpha](/doxygen/Classes/structsam_1_1_trim_and_fill_1_1_parameters/#variable-alpha)** <br>The ɑ of the test.  |














## Public Functions Documentation

### function NLOHMANN_DEFINE_TYPE_INTRUSIVE

```cpp
NLOHMANN_DEFINE_TYPE_INTRUSIVE(
    TrimAndFill::Parameters ,
    name ,
    side ,
    estimator ,
    alpha 
)
```































## Public Attributes Documentation

### variable name

```cpp
std::string name {"TrimAndFill"};
```





























### variable side

```cpp
std::string side {"auto"};
```

Indicates the side of the funnel plot where missing values should be imputed. 




























### variable estimator

```cpp
std::string estimator {"R0"};
```

The symmetry estimator. 




























### variable alpha

```cpp
double alpha {0.10};
```

The ɑ of the test. 
































-------------------------------

Updated on  7 December 2020 at 13:20:10 CET