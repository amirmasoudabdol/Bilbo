---
title: sam::CohensD

---

# sam::CohensD

**Module:** **[Effect Strategies](/doxygen/Modules/group___effect_strategies/)**



Inherits from [sam::EffectStrategy](/doxygen/Classes/classsam_1_1_effect_strategy/)

## Public Functions

|                | Name           |
| -------------- | -------------- |
| | **[CohensD](/doxygen/Classes/classsam_1_1_cohens_d/#function-cohensd)**() =default |
| virtual void | **[computeEffects](/doxygen/Classes/classsam_1_1_cohens_d/#function-computeeffects)**([Experiment](/doxygen/Classes/classsam_1_1_experiment/) * experiment) override |

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

### function CohensD

```cpp
explicit CohensD() =default
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