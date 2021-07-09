---
title: sam::YuenTest::Parameters

---

# sam::YuenTest::Parameters



## Public Functions

|                | Name           |
| -------------- | -------------- |
| | **[NLOHMANN_DEFINE_TYPE_INTRUSIVE](/doxygen/Classes/structsam_1_1_yuen_test_1_1_parameters/#function-nlohmann_define_type_intrusive)**([YuenTest::Parameters](/doxygen/Classes/structsam_1_1_yuen_test_1_1_parameters/) , name , alternative , alpha , trim , paired ) |

## Public Attributes

|                | Name           |
| -------------- | -------------- |
| [TestMethod](/doxygen/Classes/classsam_1_1_test_strategy/#enum-testmethod) | **[name](/doxygen/Classes/structsam_1_1_yuen_test_1_1_parameters/#variable-name)**  |
| [TestAlternative](/doxygen/Classes/classsam_1_1_test_strategy/#enum-testalternative) | **[alternative](/doxygen/Classes/structsam_1_1_yuen_test_1_1_parameters/#variable-alternative)**  |
| float | **[alpha](/doxygen/Classes/structsam_1_1_yuen_test_1_1_parameters/#variable-alpha)**  |
| float | **[trim](/doxygen/Classes/structsam_1_1_yuen_test_1_1_parameters/#variable-trim)**  |
| bool | **[paired](/doxygen/Classes/structsam_1_1_yuen_test_1_1_parameters/#variable-paired)**  |

## Public Functions Documentation

### function NLOHMANN_DEFINE_TYPE_INTRUSIVE

```cpp
NLOHMANN_DEFINE_TYPE_INTRUSIVE(
    YuenTest::Parameters ,
    name ,
    alternative ,
    alpha ,
    trim ,
    paired 
)
```


## Public Attributes Documentation

### variable name

```cpp
TestMethod name = [TestMethod::YuenTest](/doxygen/Classes/classsam_1_1_test_strategy/#enumvalue-yuentest);
```


### variable alternative

```cpp
TestAlternative alternative = TestAlternative::TwoSided;
```


### variable alpha

```cpp
float alpha {0.05};
```


### variable trim

```cpp
float trim {0.20};
```


### variable paired

```cpp
bool paired {false};
```


-------------------------------

Updated on 29 June 2021 at 16:13:48 CEST