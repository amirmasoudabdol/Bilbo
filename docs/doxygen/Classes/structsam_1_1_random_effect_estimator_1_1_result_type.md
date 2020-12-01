---
title: sam::RandomEffectEstimator::ResultType


---

# sam::RandomEffectEstimator::ResultType



















## Public Functions

|                | Name           |
| -------------- | -------------- |
|  | **[ResultType](/doxygen/Classes/structsam_1_1_random_effect_estimator_1_1_result_type/#function-resulttype)**() =default  |
|  | **[operator arma::Row< double >](/doxygen/Classes/structsam_1_1_random_effect_estimator_1_1_result_type/#function-operator-armarow<-double->)**()  |
| std::vector< std::string > | **[Columns](/doxygen/Classes/structsam_1_1_random_effect_estimator_1_1_result_type/#function-columns)**()  |


## Public Attributes

|                | Name           |
| -------------- | -------------- |
| double | **[est](/doxygen/Classes/structsam_1_1_random_effect_estimator_1_1_result_type/#variable-est)**  |
| double | **[se](/doxygen/Classes/structsam_1_1_random_effect_estimator_1_1_result_type/#variable-se)**  |
| double | **[ci_lb](/doxygen/Classes/structsam_1_1_random_effect_estimator_1_1_result_type/#variable-ci_lb)**  |
| double | **[ci_ub](/doxygen/Classes/structsam_1_1_random_effect_estimator_1_1_result_type/#variable-ci_ub)**  |
| double | **[zval](/doxygen/Classes/structsam_1_1_random_effect_estimator_1_1_result_type/#variable-zval)**  |
| double | **[pval](/doxygen/Classes/structsam_1_1_random_effect_estimator_1_1_result_type/#variable-pval)**  |
| double | **[q_stat](/doxygen/Classes/structsam_1_1_random_effect_estimator_1_1_result_type/#variable-q_stat)**  |
| double | **[q_pval](/doxygen/Classes/structsam_1_1_random_effect_estimator_1_1_result_type/#variable-q_pval)**  |
| double | **[tau2](/doxygen/Classes/structsam_1_1_random_effect_estimator_1_1_result_type/#variable-tau2)**  |


## Friends

|                | Name           |
| -------------- | -------------- |
| ostream & | **[operator<<](/doxygen/Classes/structsam_1_1_random_effect_estimator_1_1_result_type/#friend-operator<<)**(ostream & os, const [ResultType](/doxygen/Classes/structsam_1_1_random_effect_estimator_1_1_result_type/) & type)  |












## Public Functions Documentation

### function ResultType

```cpp
ResultType() =default
```





























### function operator arma::Row< double >

```cpp
inline operator arma::Row< double >()
```





























### function Columns

```cpp
static inline std::vector< std::string > Columns()
```































## Public Attributes Documentation

### variable est

```cpp
double est;
```





























### variable se

```cpp
double se;
```





























### variable ci_lb

```cpp
double ci_lb;
```





























### variable ci_ub

```cpp
double ci_ub;
```





























### variable zval

```cpp
double zval;
```





























### variable pval

```cpp
double pval;
```





























### variable q_stat

```cpp
double q_stat;
```





























### variable q_pval

```cpp
double q_pval;
```





























### variable tau2

```cpp
double tau2;
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

Updated on 23 November 2020 at 14:03:43 CET