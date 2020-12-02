---
title: sam::MeanDifference


---

# sam::MeanDifference








Inherits from [sam::EffectStrategy](/doxygen/Classes/classsam_1_1_effect_strategy/)











## Public Functions

|                | Name           |
| -------------- | -------------- |
|  | **[MeanDifference](/doxygen/Classes/classsam_1_1_mean_difference/#function-meandifference)**()  |
|  | **[MeanDifference](/doxygen/Classes/classsam_1_1_mean_difference/#function-meandifference)**([EffectStrategyParameters](/doxygen/Classes/structsam_1_1_effect_strategy_1_1_effect_strategy_parameters/) esp)  |
| virtual void | **[computeEffects](/doxygen/Classes/classsam_1_1_mean_difference/#function-computeeffects)**([Experiment](/doxygen/Classes/classsam_1_1_experiment/) * experiment)  |






## Additional inherited members


**Public Classes inherited from [sam::EffectStrategy](/doxygen/Classes/classsam_1_1_effect_strategy/)**

|                | Name           |
| -------------- | -------------- |
| struct | **[EffectStrategyParameters](/doxygen/Classes/structsam_1_1_effect_strategy_1_1_effect_strategy_parameters/)**  |


**Public Types inherited from [sam::EffectStrategy](/doxygen/Classes/classsam_1_1_effect_strategy/)**

|                | Name           |
| -------------- | -------------- |
| enum | **[EffectEstimator](/doxygen/Classes/classsam_1_1_effect_strategy/#enum-effectestimator)** { CohensD, HedgesG, OddRatio, StandardizedMeanDifference } |






**Public Functions inherited from [sam::EffectStrategy](/doxygen/Classes/classsam_1_1_effect_strategy/)**

|                | Name           |
| -------------- | -------------- |
| std::unique_ptr< [EffectStrategy](/doxygen/Classes/classsam_1_1_effect_strategy/) > | **[build](/doxygen/Classes/classsam_1_1_effect_strategy/#function-build)**(json & effect_strategy_config)  |
| virtual  | **[~EffectStrategy](/doxygen/Classes/classsam_1_1_effect_strategy/#function-~effectstrategy)**() =0  |


**Public Attributes inherited from [sam::EffectStrategy](/doxygen/Classes/classsam_1_1_effect_strategy/)**

|                | Name           |
| -------------- | -------------- |
| [EffectStrategyParameters](/doxygen/Classes/structsam_1_1_effect_strategy_1_1_effect_strategy_parameters/) | **[params](/doxygen/Classes/classsam_1_1_effect_strategy/#variable-params)**  |













## Public Functions Documentation

### function MeanDifference

```cpp
inline explicit MeanDifference()
```





























### function MeanDifference

```cpp
inline explicit MeanDifference(
    EffectStrategyParameters esp
)
```





























### function computeEffects

```cpp
virtual void computeEffects(
    Experiment * experiment
)
```


























**Reimplements**: [sam::EffectStrategy::computeEffects](/doxygen/Classes/classsam_1_1_effect_strategy/#function-computeeffects)










-------------------------------

Updated on 23 November 2020 at 14:03:43 CET