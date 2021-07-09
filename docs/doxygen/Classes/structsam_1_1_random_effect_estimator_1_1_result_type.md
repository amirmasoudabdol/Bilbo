---
title: sam::RandomEffectEstimator::ResultType

---

# sam::RandomEffectEstimator::ResultType



## Public Functions

|                | Name           |
| -------------- | -------------- |
| | **[ResultType](/doxygen/Classes/structsam_1_1_random_effect_estimator_1_1_result_type/#function-resulttype)**() =default |
| std::vector< std::string > | **[Columns](/doxygen/Classes/structsam_1_1_random_effect_estimator_1_1_result_type/#function-columns)**() |

## Public Attributes

|                | Name           |
| -------------- | -------------- |
| float | **[est](/doxygen/Classes/structsam_1_1_random_effect_estimator_1_1_result_type/#variable-est)**  |
| float | **[se](/doxygen/Classes/structsam_1_1_random_effect_estimator_1_1_result_type/#variable-se)**  |
| float | **[ci_lb](/doxygen/Classes/structsam_1_1_random_effect_estimator_1_1_result_type/#variable-ci_lb)**  |
| float | **[ci_ub](/doxygen/Classes/structsam_1_1_random_effect_estimator_1_1_result_type/#variable-ci_ub)**  |
| float | **[zval](/doxygen/Classes/structsam_1_1_random_effect_estimator_1_1_result_type/#variable-zval)**  |
| float | **[pval](/doxygen/Classes/structsam_1_1_random_effect_estimator_1_1_result_type/#variable-pval)**  |
| float | **[q_stat](/doxygen/Classes/structsam_1_1_random_effect_estimator_1_1_result_type/#variable-q_stat)**  |
| float | **[q_pval](/doxygen/Classes/structsam_1_1_random_effect_estimator_1_1_result_type/#variable-q_pval)**  |
| float | **[tau2](/doxygen/Classes/structsam_1_1_random_effect_estimator_1_1_result_type/#variable-tau2)**  |

## Friends

|                | Name           |
| -------------- | -------------- |
| ostream & | **[operator<<](/doxygen/Classes/structsam_1_1_random_effect_estimator_1_1_result_type/#friend-operator<<)**(ostream & os, const [ResultType](/doxygen/Classes/structsam_1_1_random_effect_estimator_1_1_result_type/) & type)  |

## Public Functions Documentation

### function ResultType

```cpp
ResultType() =default
```


### function Columns

```cpp
static inline std::vector< std::string > Columns()
```


## Public Attributes Documentation

### variable est

```cpp
float est;
```


### variable se

```cpp
float se;
```


### variable ci_lb

```cpp
float ci_lb;
```


### variable ci_ub

```cpp
float ci_ub;
```


### variable zval

```cpp
float zval;
```


### variable pval

```cpp
float pval;
```


### variable q_stat

```cpp
float q_stat;
```


### variable q_pval

```cpp
float q_pval;
```


### variable tau2

```cpp
float tau2;
```


## Friends

### friend operator<<

```cpp
friend ostream & operator<<(
    ostream & os,

    const ResultType & type
);
```


-------------------------------

Updated on 29 June 2021 at 16:13:47 CEST