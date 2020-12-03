---
title: sam::TrimAndFill::Parameters


---

# sam::TrimAndFill::Parameters




 [More...](#detailed-description)


`#include <MetaAnalysis.h>`













## Public Functions

|                | Name           |
| -------------- | -------------- |
|  | **[NLOHMANN_DEFINE_TYPE_INTRUSIVE](/doxygen/Classes/structsam_1_1_trim_and_fill_1_1_parameters/#function-nlohmann_define_type_intrusive)**([TrimAndFill::Parameters](/doxygen/Classes/structsam_1_1_trim_and_fill_1_1_parameters/) , name , side , estimator , alpha )  |


## Public Attributes

|                | Name           |
| -------------- | -------------- |
| std::string | **[name](/doxygen/Classes/structsam_1_1_trim_and_fill_1_1_parameters/#variable-name)**  |
| std::string | **[side](/doxygen/Classes/structsam_1_1_trim_and_fill_1_1_parameters/#variable-side)**  |
| std::string | **[estimator](/doxygen/Classes/structsam_1_1_trim_and_fill_1_1_parameters/#variable-estimator)**  |
| double | **[alpha](/doxygen/Classes/structsam_1_1_trim_and_fill_1_1_parameters/#variable-alpha)**  |






## Detailed Description

```cpp
struct sam::TrimAndFill::Parameters;
```
















**Todo**: : to be extended! and be properly implemented 




















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





























### variable estimator

```cpp
std::string estimator {"R0"};
```





























### variable alpha

```cpp
double alpha {0.10};
```

































-------------------------------

Updated on  3 December 2020 at 12:37:29 CET