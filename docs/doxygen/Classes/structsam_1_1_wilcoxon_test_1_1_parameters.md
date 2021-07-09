---
title: sam::WilcoxonTest::Parameters

---

# sam::WilcoxonTest::Parameters



## Public Functions

|                | Name           |
| -------------- | -------------- |
| | **[NLOHMANN_DEFINE_TYPE_INTRUSIVE](/doxygen/Classes/structsam_1_1_wilcoxon_test_1_1_parameters/#function-nlohmann_define_type_intrusive)**([WilcoxonTest::Parameters](/doxygen/Classes/structsam_1_1_wilcoxon_test_1_1_parameters/) , name , alternative , alpha , use_continuity ) |

## Public Attributes

|                | Name           |
| -------------- | -------------- |
| [TestMethod](/doxygen/Classes/classsam_1_1_test_strategy/#enum-testmethod) | **[name](/doxygen/Classes/structsam_1_1_wilcoxon_test_1_1_parameters/#variable-name)**  |
| [TestAlternative](/doxygen/Classes/classsam_1_1_test_strategy/#enum-testalternative) | **[alternative](/doxygen/Classes/structsam_1_1_wilcoxon_test_1_1_parameters/#variable-alternative)**  |
| float | **[alpha](/doxygen/Classes/structsam_1_1_wilcoxon_test_1_1_parameters/#variable-alpha)**  |
| bool | **[use_continuity](/doxygen/Classes/structsam_1_1_wilcoxon_test_1_1_parameters/#variable-use_continuity)**  |

## Public Functions Documentation

### function NLOHMANN_DEFINE_TYPE_INTRUSIVE

```cpp
NLOHMANN_DEFINE_TYPE_INTRUSIVE(
    WilcoxonTest::Parameters ,
    name ,
    alternative ,
    alpha ,
    use_continuity 
)
```


## Public Attributes Documentation

### variable name

```cpp
TestMethod name = [TestMethod::WilcoxonTest](/doxygen/Classes/classsam_1_1_test_strategy/#enumvalue-wilcoxontest);
```


### variable alternative

```cpp
TestAlternative alternative = TestAlternative::TwoSided;
```


### variable alpha

```cpp
float alpha = 0.95;
```


### variable use_continuity

```cpp
bool use_continuity {true};
```


-------------------------------

Updated on 29 June 2021 at 16:13:48 CEST