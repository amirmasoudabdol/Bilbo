---
title: sam::EffectStrategy
summary: Abstract class for Effect Size Strategy. 

---

# sam::EffectStrategy



Abstract class for Effect Size Strategy. 
`#include <EffectStrategy.h>`

Inherited by [sam::CohensD](/doxygen/Classes/classsam_1_1_cohens_d/), [sam::HedgesG](/doxygen/Classes/classsam_1_1_hedges_g/), [sam::MeanDifference](/doxygen/Classes/classsam_1_1_mean_difference/), [sam::StandardizedMeanDifference](/doxygen/Classes/classsam_1_1_standardized_mean_difference/)

## Public Types

|                | Name           |
| -------------- | -------------- |
| enum| **[EffectEstimator](/doxygen/Classes/classsam_1_1_effect_strategy/#enum-effectestimator)** { CohensD, HedgesG, OddRatio, StandardizedMeanDifference} |

## Public Functions

|                | Name           |
| -------------- | -------------- |
| std::unique_ptr< [EffectStrategy](/doxygen/Classes/classsam_1_1_effect_strategy/) > | **[build](/doxygen/Classes/classsam_1_1_effect_strategy/#function-build)**(json & effect_strategy_config) |
| virtual | **[~EffectStrategy](/doxygen/Classes/classsam_1_1_effect_strategy/#function-~effectstrategy)**() =0 |
| virtual void | **[computeEffects](/doxygen/Classes/classsam_1_1_effect_strategy/#function-computeeffects)**([Experiment](/doxygen/Classes/classsam_1_1_experiment/) * experiment) =0 |

## Public Types Documentation

### enum EffectEstimator

| Enumerator | Value | Description |
| ---------- | ----- | ----------- |
| CohensD | |   |
| HedgesG | |   |
| OddRatio | |   |
| StandardizedMeanDifference | |   |




## Public Functions Documentation

### function build

```cpp
static std::unique_ptr< EffectStrategy > build(
    json & effect_strategy_config
)
```


### function ~EffectStrategy

```cpp
virtual ~EffectStrategy() =0
```


### function computeEffects

```cpp
virtual void computeEffects(
    Experiment * experiment
) =0
```


**Reimplemented by**: [sam::MeanDifference::computeEffects](/doxygen/Classes/classsam_1_1_mean_difference/#function-computeeffects), [sam::StandardizedMeanDifference::computeEffects](/doxygen/Classes/classsam_1_1_standardized_mean_difference/#function-computeeffects), [sam::CohensD::computeEffects](/doxygen/Classes/classsam_1_1_cohens_d/#function-computeeffects), [sam::HedgesG::computeEffects](/doxygen/Classes/classsam_1_1_hedges_g/#function-computeeffects)


-------------------------------

Updated on 29 June 2021 at 16:13:46 CEST