---
title: sam::FixedEffectEstimator


---

# sam::FixedEffectEstimator








Inherits from [sam::MetaAnalysis](/doxygen/Classes/classsam_1_1_meta_analysis/)



## Public Classes

|                | Name           |
| -------------- | -------------- |
| struct | **[ResultType](/doxygen/Classes/structsam_1_1_fixed_effect_estimator_1_1_result_type/)**  |








## Public Functions

|                | Name           |
| -------------- | -------------- |
|  | **[FixedEffectEstimator](/doxygen/Classes/classsam_1_1_fixed_effect_estimator/#function-fixedeffectestimator)**() =default  |
| virtual void | **[estimate](/doxygen/Classes/classsam_1_1_fixed_effect_estimator/#function-estimate)**([Journal](/doxygen/Classes/classsam_1_1_journal/) * journal)  |
| [ResultType](/doxygen/Classes/structsam_1_1_fixed_effect_estimator_1_1_result_type/) | **[FixedEffect](/doxygen/Classes/classsam_1_1_fixed_effect_estimator/#function-fixedeffect)**(const arma::Row< double > & yi, const arma::Row< double > & vi)  |






## Additional inherited members










**Public Functions inherited from [sam::MetaAnalysis](/doxygen/Classes/classsam_1_1_meta_analysis/)**

|                | Name           |
| -------------- | -------------- |
| virtual  | **[~MetaAnalysis](/doxygen/Classes/classsam_1_1_meta_analysis/#function-~metaanalysis)**() =0  |
| std::unique_ptr< [MetaAnalysis](/doxygen/Classes/classsam_1_1_meta_analysis/) > | **[build](/doxygen/Classes/classsam_1_1_meta_analysis/#function-build)**(std::string name)  |
| std::unique_ptr< [MetaAnalysis](/doxygen/Classes/classsam_1_1_meta_analysis/) > | **[build](/doxygen/Classes/classsam_1_1_meta_analysis/#function-build)**(const json & config)  |
| std::vector< std::string > | **[Columns](/doxygen/Classes/classsam_1_1_meta_analysis/#function-columns)**(std::string name)  |















## Public Functions Documentation

### function FixedEffectEstimator

```cpp
FixedEffectEstimator() =default
```





























### function estimate

```cpp
virtual void estimate(
    Journal * journal
)
```


























**Reimplements**: [sam::MetaAnalysis::estimate](/doxygen/Classes/classsam_1_1_meta_analysis/#function-estimate)




### function FixedEffect

```cpp
static inline ResultType FixedEffect(
    const arma::Row< double > & yi,
    const arma::Row< double > & vi
)
```



































-------------------------------

Updated on 23 November 2020 at 14:03:43 CET