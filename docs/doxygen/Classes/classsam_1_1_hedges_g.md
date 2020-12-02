---
title: sam::HedgesG


---

# sam::HedgesG


**Module:** **[Effect Strategies](/doxygen/Modules/group___effect_strategies/)**





Inherits from [sam::EffectStrategy](/doxygen/Classes/classsam_1_1_effect_strategy/)











## Public Functions

|                | Name           |
| -------------- | -------------- |
|  | **[HedgesG](/doxygen/Classes/classsam_1_1_hedges_g/#function-hedgesg)**()  |
|  | **[HedgesG](/doxygen/Classes/classsam_1_1_hedges_g/#function-hedgesg)**([EffectStrategyParameters](/doxygen/Classes/structsam_1_1_effect_strategy_1_1_effect_strategy_parameters/) esp)  |
| virtual void | **[computeEffects](/doxygen/Classes/classsam_1_1_hedges_g/#function-computeeffects)**([Experiment](/doxygen/Classes/classsam_1_1_experiment/) * experiment)  |






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

### function HedgesG

```cpp
inline explicit HedgesG()
```





























### function HedgesG

```cpp
inline explicit HedgesG(
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



Skipping Treatment groups







-------------------------------

Updated on  2 December 2020 at 14:48:54 CET