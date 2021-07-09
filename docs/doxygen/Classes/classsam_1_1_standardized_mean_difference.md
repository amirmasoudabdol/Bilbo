---
title: sam::StandardizedMeanDifference

---

# sam::StandardizedMeanDifference

**Module:** **[Effect Strategies](/doxygen/Modules/group___effect_strategies/)**



Inherits from [sam::EffectStrategy](/doxygen/Classes/classsam_1_1_effect_strategy/)

## Public Functions

|                | Name           |
| -------------- | -------------- |
| | **[StandardizedMeanDifference](/doxygen/Classes/classsam_1_1_standardized_mean_difference/#function-standardizedmeandifference)**() =default |
| virtual void | **[computeEffects](/doxygen/Classes/classsam_1_1_standardized_mean_difference/#function-computeeffects)**([Experiment](/doxygen/Classes/classsam_1_1_experiment/) * experiment) override |

## Additional inherited members

**Public Types inherited from [sam::EffectStrategy](/doxygen/Classes/classsam_1_1_effect_strategy/)**

|                | Name           |
| -------------- | -------------- |
| enum| **[EffectEstimator](/doxygen/Classes/classsam_1_1_effect_strategy/#enum-effectestimator)** { CohensD, HedgesG, OddRatio, StandardizedMeanDifference} |

**Public Functions inherited from [sam::EffectStrategy](/doxygen/Classes/classsam_1_1_effect_strategy/)**

|                | Name           |
| -------------- | -------------- |
| std::unique_ptr< [EffectStrategy](/doxygen/Classes/classsam_1_1_effect_strategy/) > | **[build](/doxygen/Classes/classsam_1_1_effect_strategy/#function-build)**(json & effect_strategy_config) |
| virtual | **[~EffectStrategy](/doxygen/Classes/classsam_1_1_effect_strategy/#function-~effectstrategy)**() =0 |


## Public Functions Documentation

### function StandardizedMeanDifference

```cpp
explicit StandardizedMeanDifference() =default
```


### function computeEffects

```cpp
virtual void computeEffects(
    Experiment * experiment
) override
```


**Reimplements**: [sam::EffectStrategy::computeEffects](/doxygen/Classes/classsam_1_1_effect_strategy/#function-computeeffects)


-------------------------------

Updated on 29 June 2021 at 16:13:47 CEST