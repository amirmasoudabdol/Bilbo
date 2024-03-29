---
title: sam::TTest::Parameters

---

# sam::TTest::Parameters



## Public Functions

|                | Name           |
| -------------- | -------------- |
| | **[NLOHMANN_DEFINE_TYPE_INTRUSIVE](/doxygen/Classes/structsam_1_1_t_test_1_1_parameters/#function-nlohmann_define_type_intrusive)**([TTest::Parameters](/doxygen/Classes/structsam_1_1_t_test_1_1_parameters/) , name , alternative , alpha , var_equal ) |

## Public Attributes

|                | Name           |
| -------------- | -------------- |
| [TestMethod](/doxygen/Classes/classsam_1_1_test_strategy/#enum-testmethod) | **[name](/doxygen/Classes/structsam_1_1_t_test_1_1_parameters/#variable-name)**  |
| [TestAlternative](/doxygen/Classes/classsam_1_1_test_strategy/#enum-testalternative) | **[alternative](/doxygen/Classes/structsam_1_1_t_test_1_1_parameters/#variable-alternative)**  |
| float | **[alpha](/doxygen/Classes/structsam_1_1_t_test_1_1_parameters/#variable-alpha)**  |
| bool | **[var_equal](/doxygen/Classes/structsam_1_1_t_test_1_1_parameters/#variable-var_equal)**  |

## Public Functions Documentation

### function NLOHMANN_DEFINE_TYPE_INTRUSIVE

```cpp
NLOHMANN_DEFINE_TYPE_INTRUSIVE(
    TTest::Parameters ,
    name ,
    alternative ,
    alpha ,
    var_equal 
)
```


## Public Attributes Documentation

### variable name

```cpp
TestMethod name = [TestMethod::TTest](/doxygen/Classes/classsam_1_1_test_strategy/#enumvalue-ttest);
```


### variable alternative

```cpp
TestAlternative alternative = TestAlternative::TwoSided;
```


### variable alpha

```cpp
float alpha;
```


### variable var_equal

```cpp
bool var_equal {true};
```


-------------------------------

Updated on 29 June 2021 at 16:13:48 CEST