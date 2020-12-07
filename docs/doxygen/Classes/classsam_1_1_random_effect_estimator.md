---
title: sam::RandomEffectEstimator
summary: Random Effect Estimator.  

---

# sam::RandomEffectEstimator


**Module:** **[Meta Analysis Methods](/doxygen/Modules/group___meta_analysis/)**

Random Effect Estimator. 

`#include <MetaAnalysis.h>`


Inherits from [sam::MetaAnalysis](/doxygen/Classes/classsam_1_1_meta_analysis/)



## Public Classes

|                | Name           |
| -------------- | -------------- |
| struct | **[Parameters](/doxygen/Classes/structsam_1_1_random_effect_estimator_1_1_parameters/)** <br>[Parameters]() of the [RandomEffectEstimator](/doxygen/Classes/classsam_1_1_random_effect_estimator/).  |
| struct | **[ResultType](/doxygen/Classes/structsam_1_1_random_effect_estimator_1_1_result_type/)**  |








## Public Functions

|                | Name           |
| -------------- | -------------- |
|  | **[RandomEffectEstimator](/doxygen/Classes/classsam_1_1_random_effect_estimator/#function-randomeffectestimator)**() =default  |
|  | **[RandomEffectEstimator](/doxygen/Classes/classsam_1_1_random_effect_estimator/#function-randomeffectestimator)**(const [Parameters](/doxygen/Classes/structsam_1_1_random_effect_estimator_1_1_parameters/) & p)  |
| virtual void | **[estimate](/doxygen/Classes/classsam_1_1_random_effect_estimator/#function-estimate)**([Journal](/doxygen/Classes/classsam_1_1_journal/) * journal)  |
| double | **[DL](/doxygen/Classes/classsam_1_1_random_effect_estimator/#function-dl)**(const arma::Row< double > & yi, const arma::Row< double > & vi, const arma::Row< double > & ai)  |
| double | **[PM](/doxygen/Classes/classsam_1_1_random_effect_estimator/#function-pm)**(const arma::Row< double > & yi, const arma::Row< double > & vi, const double tau2)  |
| [ResultType](/doxygen/Classes/structsam_1_1_random_effect_estimator_1_1_result_type/) | **[RandomEffect](/doxygen/Classes/classsam_1_1_random_effect_estimator/#function-randomeffect)**(const arma::Row< double > & vi, const arma::Row< double > & yi, double tau2)  |


## Public Attributes

|                | Name           |
| -------------- | -------------- |
| [Parameters](/doxygen/Classes/structsam_1_1_random_effect_estimator_1_1_parameters/) | **[params](/doxygen/Classes/classsam_1_1_random_effect_estimator/#variable-params)**  |




## Additional inherited members










**Public Functions inherited from [sam::MetaAnalysis](/doxygen/Classes/classsam_1_1_meta_analysis/)**

|                | Name           |
| -------------- | -------------- |
| virtual  | **[~MetaAnalysis](/doxygen/Classes/classsam_1_1_meta_analysis/#function-~metaanalysis)**() =0  |
| std::unique_ptr< [MetaAnalysis](/doxygen/Classes/classsam_1_1_meta_analysis/) > | **[build](/doxygen/Classes/classsam_1_1_meta_analysis/#function-build)**(std::string name)  |
| std::unique_ptr< [MetaAnalysis](/doxygen/Classes/classsam_1_1_meta_analysis/) > | **[build](/doxygen/Classes/classsam_1_1_meta_analysis/#function-build)**(const json & config)  |
| std::vector< std::string > | **[Columns](/doxygen/Classes/classsam_1_1_meta_analysis/#function-columns)**(std::string name)  |















## Public Functions Documentation

### function `RandomEffectEstimator`

```cpp
RandomEffectEstimator() =default
```





























### function `RandomEffectEstimator`

```cpp
inline RandomEffectEstimator(
    const Parameters & p
)
```





























### function `estimate`

```cpp
virtual void estimate(
    Journal * journal
)
```


























**Reimplements**: [sam::MetaAnalysis::estimate](/doxygen/Classes/classsam_1_1_meta_analysis/#function-estimate)




### function `DL`

```cpp
double DL(
    const arma::Row< double > & yi,
    const arma::Row< double > & vi,
    const arma::Row< double > & ai
)
```





























### function `PM`

```cpp
double PM(
    const arma::Row< double > & yi,
    const arma::Row< double > & vi,
    const double tau2
)
```





























### function `RandomEffect`

```cpp
static ResultType RandomEffect(
    const arma::Row< double > & vi,
    const arma::Row< double > & yi,
    double tau2
)
```































## Public Attributes Documentation

### variable `params`

```cpp
Parameters params;
```

































