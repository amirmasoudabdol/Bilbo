---
title: sam::DataStrategy
summary: Abstract class for Data Strategies.  

---

# sam::DataStrategy


**Module:** **[Data Strategies](/doxygen/Modules/group___data_strategies/)**

Abstract class for Data Strategies.  [More...](#detailed-description)


`#include <DataStrategy.h>`



Inherited by [sam::GRMDataStrategy](/doxygen/Classes/classsam_1_1_g_r_m_data_strategy/), [sam::LatentDataStrategy](/doxygen/Classes/classsam_1_1_latent_data_strategy/), [sam::LinearModelStrategy](/doxygen/Classes/classsam_1_1_linear_model_strategy/)




## Public Types

|                | Name           |
| -------------- | -------------- |
| enum | **[DataModel](/doxygen/Classes/classsam_1_1_data_strategy/#enum-datamodel)** { LinearModel, LatentModel, GradedResponseModel } |






## Public Functions

|                | Name           |
| -------------- | -------------- |
| std::unique_ptr< [DataStrategy](/doxygen/Classes/classsam_1_1_data_strategy/) > | **[build](/doxygen/Classes/classsam_1_1_data_strategy/#function-build)**(json & data_strategy_config) <br>[DataStrategy](/doxygen/Classes/classsam_1_1_data_strategy/) Factory Method.  |
| virtual  | **[~DataStrategy](/doxygen/Classes/classsam_1_1_data_strategy/#function-~datastrategy)**() =0 <br>Pure deconstructor of the [DataStrategy](/doxygen/Classes/classsam_1_1_data_strategy/) abstract class.  |
| virtual void | **[genData](/doxygen/Classes/classsam_1_1_data_strategy/#function-gendata)**([Experiment](/doxygen/Classes/classsam_1_1_experiment/) * experiment) =0 <br>Generates data based on the selected DataModel.  |
| virtual std::vector< arma::Row< double > > | **[genNewObservationsForAllGroups](/doxygen/Classes/classsam_1_1_data_strategy/#function-gennewobservationsforallgroups)**([Experiment](/doxygen/Classes/classsam_1_1_experiment/) * experiment, int n_new_obs) =0 <br>Generates `n_new_obs` new observations for each group.  |
| virtual arma::Row< double > | **[genNewObservationsFor](/doxygen/Classes/classsam_1_1_data_strategy/#function-gennewobservationsfor)**([Experiment](/doxygen/Classes/classsam_1_1_experiment/) * experiment, int g, int n_new_obs) =0 <br>Generate `n_new_obs` new observations for `g` group.  |








## Detailed Description

```cpp
class sam::DataStrategy;
```

Abstract class for Data Strategies. 


























A DataGenStrategy should at least two methods, `genData` and `genNewObservationForAllGroups`. The former is mainly used to populate a new [Experiment](/doxygen/Classes/classsam_1_1_experiment/) while the latter is being used by some hacking strategies, e.g. [OptionalStopping](/doxygen/Classes/classsam_1_1_optional_stopping/), where new data — from the same population — is needed. 



## Public Types Documentation

### enum `DataModel`


| Enumerator | Value | Description |
| ---------- | ----- | ----------- |
| LinearModel |  |   |
| LatentModel |  |   |
| GradedResponseModel |  |   |





































## Public Functions Documentation

### function `build`

```cpp
static std::unique_ptr< DataStrategy > build(
    json & data_strategy_config
)
```

[DataStrategy](/doxygen/Classes/classsam_1_1_data_strategy/) Factory Method. 

**Parameters**: 

  * **`data_strategy_config`** The data strategy configuration







**Return**: A unique_ptr to a new [DataStrategy](/doxygen/Classes/classsam_1_1_data_strategy/)





















### function `~DataStrategy`

```cpp
virtual ~DataStrategy() =0
```

Pure deconstructor of the [DataStrategy](/doxygen/Classes/classsam_1_1_data_strategy/) abstract class. 




























### function `genData`

```cpp
virtual void genData(
    Experiment * experiment
) =0
```

Generates data based on the selected DataModel. 

**Parameters**: 

  * **`experiment`** A pointer to an [Experiment](/doxygen/Classes/classsam_1_1_experiment/) object 

























**Reimplemented by**: [sam::LinearModelStrategy::genData](/doxygen/Classes/classsam_1_1_linear_model_strategy/#function-gendata), [sam::LatentDataStrategy::genData](/doxygen/Classes/classsam_1_1_latent_data_strategy/#function-gendata), [sam::GRMDataStrategy::genData](/doxygen/Classes/classsam_1_1_g_r_m_data_strategy/#function-gendata)


Populates the `experiment->groups_->measurements` with data based on the parameters specified in `setup`.


### function `genNewObservationsForAllGroups`

```cpp
virtual std::vector< arma::Row< double > > genNewObservationsForAllGroups(
    Experiment * experiment,
    int n_new_obs
) =0
```

Generates `n_new_obs` new observations for each group. 

**Parameters**: 

  * **`experiment`** The pointer to the current experiment 
  * **`n_new_obs`** The number of new observations to be generated







**Return**: An array of new observations 


















**Reimplemented by**: [sam::LinearModelStrategy::genNewObservationsForAllGroups](/doxygen/Classes/classsam_1_1_linear_model_strategy/#function-gennewobservationsforallgroups), [sam::LatentDataStrategy::genNewObservationsForAllGroups](/doxygen/Classes/classsam_1_1_latent_data_strategy/#function-gennewobservationsforallgroups), [sam::GRMDataStrategy::genNewObservationsForAllGroups](/doxygen/Classes/classsam_1_1_g_r_m_data_strategy/#function-gennewobservationsforallgroups)




### function `genNewObservationsFor`

```cpp
virtual arma::Row< double > genNewObservationsFor(
    Experiment * experiment,
    int g,
    int n_new_obs
) =0
```

Generate `n_new_obs` new observations for `g` group. 

**Parameters**: 

  * **`experiment`** The pointer to the experiment 
  * **`g`** The target group 
  * **`n_new_obs`** The number of new observations







**Return**: An array of new observations 


















**Reimplemented by**: [sam::LinearModelStrategy::genNewObservationsFor](/doxygen/Classes/classsam_1_1_linear_model_strategy/#function-gennewobservationsfor), [sam::LatentDataStrategy::genNewObservationsFor](/doxygen/Classes/classsam_1_1_latent_data_strategy/#function-gennewobservationsfor), [sam::GRMDataStrategy::genNewObservationsFor](/doxygen/Classes/classsam_1_1_g_r_m_data_strategy/#function-gennewobservationsfor)










