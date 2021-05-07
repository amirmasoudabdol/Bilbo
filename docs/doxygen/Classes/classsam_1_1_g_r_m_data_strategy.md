---
title: sam::GRMDataStrategy
summary: Simulate data based on General Graded Response Model. 

---

# sam::GRMDataStrategy

**Module:** **[Data Strategies](/doxygen/Modules/group___data_strategies/)**



Simulate data based on General Graded Response Model.  [More...](#detailed-description)


`#include <DataStrategy.h>`

Inherits from [sam::DataStrategy](/doxygen/Classes/classsam_1_1_data_strategy/)

## Public Classes

|                | Name           |
| -------------- | -------------- |
| struct | **[Parameters](/doxygen/Classes/structsam_1_1_g_r_m_data_strategy_1_1_parameters/)**  |

## Public Functions

|                | Name           |
| -------------- | -------------- |
| | **[GRMDataStrategy](/doxygen/Classes/classsam_1_1_g_r_m_data_strategy/#function-grmdatastrategy)**() =default |
| | **[GRMDataStrategy](/doxygen/Classes/classsam_1_1_g_r_m_data_strategy/#function-grmdatastrategy)**(const [Parameters](/doxygen/Classes/structsam_1_1_g_r_m_data_strategy_1_1_parameters/) & p) |
| virtual void | **[genData](/doxygen/Classes/classsam_1_1_g_r_m_data_strategy/#function-gendata)**([Experiment](/doxygen/Classes/classsam_1_1_experiment/) * experiment) override<br>Generates data based on the selected DataModel.  |
| virtual std::vector< arma::Row< double > > | **[genNewObservationsForAllGroups](/doxygen/Classes/classsam_1_1_g_r_m_data_strategy/#function-gennewobservationsforallgroups)**([Experiment](/doxygen/Classes/classsam_1_1_experiment/) * experiment, int n_new_obs) override<br>Generates `n_new_obs` new observations for each group.  |

## Additional inherited members

**Public Types inherited from [sam::DataStrategy](/doxygen/Classes/classsam_1_1_data_strategy/)**

|                | Name           |
| -------------- | -------------- |
| enum| **[DataModel](/doxygen/Classes/classsam_1_1_data_strategy/#enum-datamodel)** { LinearModel, LatentModel, GradedResponseModel} |

**Public Functions inherited from [sam::DataStrategy](/doxygen/Classes/classsam_1_1_data_strategy/)**

|                | Name           |
| -------------- | -------------- |
| std::unique_ptr< [DataStrategy](/doxygen/Classes/classsam_1_1_data_strategy/) > | **[build](/doxygen/Classes/classsam_1_1_data_strategy/#function-build)**(json & data_strategy_config)<br>[DataStrategy](/doxygen/Classes/classsam_1_1_data_strategy/) Factory Method.  |
| virtual | **[~DataStrategy](/doxygen/Classes/classsam_1_1_data_strategy/#function-~datastrategy)**() =0<br>Pure destructors of the [DataStrategy](/doxygen/Classes/classsam_1_1_data_strategy/) abstract class.  |


## Detailed Description

```cpp
class sam::GRMDataStrategy;
```

Simulate data based on General Graded Response Model. 

**Note**: :

* DVs in GRM are distinguished by their participant abilities to answer tests. Therefore, we'll have `ng_` number of `abilities`. This value is being used to, in each group, to initialize a normal distribution of `\theta ~ N(abilities[i], 1)`.
* β 
## Public Functions Documentation

### function GRMDataStrategy

```cpp
GRMDataStrategy() =default
```


### function GRMDataStrategy

```cpp
GRMDataStrategy(
    const Parameters & p
)
```


Some initialization


### function genData

```cpp
virtual void genData(
    Experiment * experiment
) override
```

Generates data based on the selected DataModel. 

**Parameters**: 

  * **experiment** A pointer to an [Experiment](/doxygen/Classes/classsam_1_1_experiment/) object 


**Reimplements**: [sam::DataStrategy::genData](/doxygen/Classes/classsam_1_1_data_strategy/#function-gendata)


Populates the `experiment->groups_->measurements` with data based on the parameters specified in `setup`.


### function genNewObservationsForAllGroups

```cpp
virtual std::vector< arma::Row< double > > genNewObservationsForAllGroups(
    Experiment * experiment,
    int n_new_obs
) override
```

Generates `n_new_obs` new observations for each group. 

**Parameters**: 

  * **experiment** The pointer to the current experiment 
  * **n_new_obs** The number of new observations to be generated


**Return**: An array of new observations 

**Reimplements**: [sam::DataStrategy::genNewObservationsForAllGroups](/doxygen/Classes/classsam_1_1_data_strategy/#function-gennewobservationsforallgroups)


-------------------------------

Updated on  7 May 2021 at 14:51:31 CEST