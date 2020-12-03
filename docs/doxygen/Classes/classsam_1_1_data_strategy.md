---
title: sam::DataStrategy
summary: Abstract class for Data Strategies.  

---

# sam::DataStrategy




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
| std::unique_ptr< [DataStrategy](/doxygen/Classes/classsam_1_1_data_strategy/) > | **[build](/doxygen/Classes/classsam_1_1_data_strategy/#function-build)**(json & data_strategy_config)  |
| virtual  | **[~DataStrategy](/doxygen/Classes/classsam_1_1_data_strategy/#function-~datastrategy)**() =0 <br>Pure deconstructor of the [DataStrategy](/doxygen/Classes/classsam_1_1_data_strategy/) abstract class.  |
| void | **[loadRawData](/doxygen/Classes/classsam_1_1_data_strategy/#function-loadrawdata)**([Experiment](/doxygen/Classes/classsam_1_1_experiment/) * expr, const std::string & filename)  |
| virtual void | **[genData](/doxygen/Classes/classsam_1_1_data_strategy/#function-gendata)**([Experiment](/doxygen/Classes/classsam_1_1_experiment/) * experiment) =0  |
| virtual std::vector< arma::Row< double > > | **[genNewObservationsForAllGroups](/doxygen/Classes/classsam_1_1_data_strategy/#function-gennewobservationsforallgroups)**([Experiment](/doxygen/Classes/classsam_1_1_experiment/) * experiment, int n_new_obs) =0  |
| virtual arma::Row< double > | **[genNewObservationsFor](/doxygen/Classes/classsam_1_1_data_strategy/#function-gennewobservationsfor)**([Experiment](/doxygen/Classes/classsam_1_1_experiment/) * experiment, int g, int n_new_obs) =0 <br>Generate `n_new_obs` new observations for `g` group.  |








## Detailed Description

```cpp
class sam::DataStrategy;
```

Abstract class for Data Strategies. 












!!! note "Note"
    Each Data Strategy should have access to an instance of RandomNumberGenerator. This is usually done by creating a desired _random engine_ and passing the pointer to the DataGenStrategy. 














A DataGenStrategy should at least two methods, `genData` and `genNewObservationForAllGroups`. The former is mainly used to populate a new [Experiment](/doxygen/Classes/classsam_1_1_experiment/) while the latter is being used by some hacking strategies, e.g. [OptionalStopping](/doxygen/Classes/classsam_1_1_optional_stopping/), where new data — from the same population — is needed.



## Public Types Documentation

### enum DataModel


| Enumerator | Value | Description |
| ---------- | ----- | ----------- |
| LinearModel |  |   |
| LatentModel |  |   |
| GradedResponseModel |  |   |





































## Public Functions Documentation

### function build

```cpp
static std::unique_ptr< DataStrategy > build(
    json & data_strategy_config
)
```


**Parameters**: 

  * **setup** An instance of [ExperimentSetup](/doxygen/Classes/classsam_1_1_experiment_setup/)







**Return**: a new [DataStrategy](/doxygen/Classes/classsam_1_1_data_strategy/)



















Factory method for [DataStrategy](/doxygen/Classes/classsam_1_1_data_strategy/).


### function ~DataStrategy

```cpp
virtual ~DataStrategy() =0
```

Pure deconstructor of the [DataStrategy](/doxygen/Classes/classsam_1_1_data_strategy/) abstract class. 




























### function loadRawData

```cpp
void loadRawData(
    Experiment * expr,
    const std::string & filename
)
```


**Parameters**: 

  * **expr** A pointer to the experiment 
  * **filename** The CSV filename 


























Read a CSV file and load the data into the measurement. Each column is considered to be one group, based on the information already provided in the `experiment.setup`.


### function genData

```cpp
virtual void genData(
    Experiment * experiment
) =0
```


**Parameters**: 

  * **experiment** A pointer to an [Experiment](/doxygen/Classes/classsam_1_1_experiment/) object 

























**Reimplemented by**: [sam::LinearModelStrategy::genData](/doxygen/Classes/classsam_1_1_linear_model_strategy/#function-gendata), [sam::LatentDataStrategy::genData](/doxygen/Classes/classsam_1_1_latent_data_strategy/#function-gendata), [sam::GRMDataStrategy::genData](/doxygen/Classes/classsam_1_1_g_r_m_data_strategy/#function-gendata)


Populates the `experiment->measurements` with data based on the parameters specified in `setup`.


### function genNewObservationsForAllGroups

```cpp
virtual std::vector< arma::Row< double > > genNewObservationsForAllGroups(
    Experiment * experiment,
    int n_new_obs
) =0
```


**Parameters**: 

  * **experiment** The pointer to the current experiment 
  * **n_new_obs** The number of new observations to be added







**Return**: An array of new observations 





!!! note "Note"
    This routine uses the secondary random number stream to avoid conflicting with the main random engine.













**Reimplemented by**: [sam::LinearModelStrategy::genNewObservationsForAllGroups](/doxygen/Classes/classsam_1_1_linear_model_strategy/#function-gennewobservationsforallgroups), [sam::LatentDataStrategy::genNewObservationsForAllGroups](/doxygen/Classes/classsam_1_1_latent_data_strategy/#function-gennewobservationsforallgroups), [sam::GRMDataStrategy::genNewObservationsForAllGroups](/doxygen/Classes/classsam_1_1_g_r_m_data_strategy/#function-gennewobservationsforallgroups)


Generates `n_new_obs` new observations to each group.


### function genNewObservationsFor

```cpp
virtual arma::Row< double > genNewObservationsFor(
    Experiment * experiment,
    int g,
    int n_new_obs
) =0
```

Generate `n_new_obs` new observations for `g` group. 

**Parameters**: 

  * **experiment** The pointer to the experiment 
  * **g** The target group 
  * **n_new_obs** The number of new observations







**Return**: An array of new observations 


















**Reimplemented by**: [sam::LinearModelStrategy::genNewObservationsFor](/doxygen/Classes/classsam_1_1_linear_model_strategy/#function-gennewobservationsfor), [sam::LatentDataStrategy::genNewObservationsFor](/doxygen/Classes/classsam_1_1_latent_data_strategy/#function-gennewobservationsfor), [sam::GRMDataStrategy::genNewObservationsFor](/doxygen/Classes/classsam_1_1_g_r_m_data_strategy/#function-gennewobservationsfor)










-------------------------------

Updated on  3 December 2020 at 12:37:28 CET