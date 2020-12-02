---
title: sam::EggersTestEstimator


---

# sam::EggersTestEstimator


**Module:** **[Meta Analysis Methods](/doxygen/Modules/group___meta_analysis/)**





Inherits from [sam::MetaAnalysis](/doxygen/Classes/classsam_1_1_meta_analysis/)



## Public Classes

|                | Name           |
| -------------- | -------------- |
| struct | **[Parameters](/doxygen/Classes/structsam_1_1_eggers_test_estimator_1_1_parameters/)**  |
| struct | **[ResultType](/doxygen/Classes/structsam_1_1_eggers_test_estimator_1_1_result_type/)**  |








## Public Functions

|                | Name           |
| -------------- | -------------- |
|  | **[EggersTestEstimator](/doxygen/Classes/classsam_1_1_eggers_test_estimator/#function-eggerstestestimator)**() =default  |
|  | **[EggersTestEstimator](/doxygen/Classes/classsam_1_1_eggers_test_estimator/#function-eggerstestestimator)**(const [Parameters](/doxygen/Classes/structsam_1_1_eggers_test_estimator_1_1_parameters/) & p)  |
| virtual void | **[estimate](/doxygen/Classes/classsam_1_1_eggers_test_estimator/#function-estimate)**([Journal](/doxygen/Classes/classsam_1_1_journal/) * journal)  |
| [ResultType](/doxygen/Classes/structsam_1_1_eggers_test_estimator_1_1_result_type/) | **[EggersTest](/doxygen/Classes/classsam_1_1_eggers_test_estimator/#function-eggerstest)**(const arma::Row< double > & yi, const arma::Row< double > & vi, double alpha)  |


## Public Attributes

|                | Name           |
| -------------- | -------------- |
| [Parameters](/doxygen/Classes/structsam_1_1_eggers_test_estimator_1_1_parameters/) | **[params](/doxygen/Classes/classsam_1_1_eggers_test_estimator/#variable-params)**  |




## Additional inherited members










**Public Functions inherited from [sam::MetaAnalysis](/doxygen/Classes/classsam_1_1_meta_analysis/)**

|                | Name           |
| -------------- | -------------- |
| virtual  | **[~MetaAnalysis](/doxygen/Classes/classsam_1_1_meta_analysis/#function-~metaanalysis)**() =0  |
| std::unique_ptr< [MetaAnalysis](/doxygen/Classes/classsam_1_1_meta_analysis/) > | **[build](/doxygen/Classes/classsam_1_1_meta_analysis/#function-build)**(std::string name)  |
| std::unique_ptr< [MetaAnalysis](/doxygen/Classes/classsam_1_1_meta_analysis/) > | **[build](/doxygen/Classes/classsam_1_1_meta_analysis/#function-build)**(const json & config)  |
| std::vector< std::string > | **[Columns](/doxygen/Classes/classsam_1_1_meta_analysis/#function-columns)**(std::string name)  |















## Public Functions Documentation

### function EggersTestEstimator

```cpp
EggersTestEstimator() =default
```





























### function EggersTestEstimator

```cpp
inline EggersTestEstimator(
    const Parameters & p
)
```





























### function estimate

```cpp
virtual void estimate(
    Journal * journal
)
```


























**Reimplements**: [sam::MetaAnalysis::estimate](/doxygen/Classes/classsam_1_1_meta_analysis/#function-estimate)




### function EggersTest

```cpp
static ResultType EggersTest(
    const arma::Row< double > & yi,
    const arma::Row< double > & vi,
    double alpha
)
```































## Public Attributes Documentation

### variable params

```cpp
Parameters params;
```

































-------------------------------

Updated on  2 December 2020 at 14:48:55 CET