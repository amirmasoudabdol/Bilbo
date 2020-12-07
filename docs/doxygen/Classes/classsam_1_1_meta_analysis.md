---
title: sam::MetaAnalysis


---

# sam::MetaAnalysis









Inherited by [sam::EggersTestEstimator](/doxygen/Classes/classsam_1_1_eggers_test_estimator/), [sam::FixedEffectEstimator](/doxygen/Classes/classsam_1_1_fixed_effect_estimator/), [sam::RandomEffectEstimator](/doxygen/Classes/classsam_1_1_random_effect_estimator/), [sam::RankCorrelation](/doxygen/Classes/classsam_1_1_rank_correlation/), [sam::TestOfObsOverExptSig](/doxygen/Classes/classsam_1_1_test_of_obs_over_expt_sig/), [sam::TrimAndFill](/doxygen/Classes/classsam_1_1_trim_and_fill/)










## Public Functions

|                | Name           |
| -------------- | -------------- |
| virtual  | **[~MetaAnalysis](/doxygen/Classes/classsam_1_1_meta_analysis/#function-~metaanalysis)**() =0  |
| virtual void | **[estimate](/doxygen/Classes/classsam_1_1_meta_analysis/#function-estimate)**([Journal](/doxygen/Classes/classsam_1_1_journal/) * journal) =0  |
| std::unique_ptr< [MetaAnalysis](/doxygen/Classes/classsam_1_1_meta_analysis/) > | **[build](/doxygen/Classes/classsam_1_1_meta_analysis/#function-build)**(std::string name)  |
| std::unique_ptr< [MetaAnalysis](/doxygen/Classes/classsam_1_1_meta_analysis/) > | **[build](/doxygen/Classes/classsam_1_1_meta_analysis/#function-build)**(const json & config)  |
| std::vector< std::string > | **[Columns](/doxygen/Classes/classsam_1_1_meta_analysis/#function-columns)**(std::string name)  |
















## Public Functions Documentation

### function `~MetaAnalysis`

```cpp
virtual ~MetaAnalysis() =0
```





























### function `estimate`

```cpp
virtual void estimate(
    Journal * journal
) =0
```


























**Reimplemented by**: [sam::RandomEffectEstimator::estimate](/doxygen/Classes/classsam_1_1_random_effect_estimator/#function-estimate), [sam::FixedEffectEstimator::estimate](/doxygen/Classes/classsam_1_1_fixed_effect_estimator/#function-estimate), [sam::EggersTestEstimator::estimate](/doxygen/Classes/classsam_1_1_eggers_test_estimator/#function-estimate), [sam::TestOfObsOverExptSig::estimate](/doxygen/Classes/classsam_1_1_test_of_obs_over_expt_sig/#function-estimate), [sam::TrimAndFill::estimate](/doxygen/Classes/classsam_1_1_trim_and_fill/#function-estimate), [sam::RankCorrelation::estimate](/doxygen/Classes/classsam_1_1_rank_correlation/#function-estimate)




### function `build`

```cpp
static std::unique_ptr< MetaAnalysis > build(
    std::string name
)
```





























### function `build`

```cpp
static std::unique_ptr< MetaAnalysis > build(
    const json & config
)
```





























### function `Columns`

```cpp
static std::vector< std::string > Columns(
    std::string name
)
```



































