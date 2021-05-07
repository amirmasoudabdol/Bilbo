---
title: sam::LinearModelStrategy
summary: Linear Model Data Strategy. 

---

# sam::LinearModelStrategy

**Module:** **[Data Strategies](/doxygen/Modules/group___data_strategies/)**



Linear Model Data Strategy. 
`#include <DataStrategy.h>`

Inherits from [sam::DataStrategy](/doxygen/Classes/classsam_1_1_data_strategy/)

## Public Classes

|                | Name           |
| -------------- | -------------- |
| struct | **[Parameters](/doxygen/Classes/structsam_1_1_linear_model_strategy_1_1_parameters/)** <br>[Parameters]() of [LinearModelStrategy](/doxygen/Classes/classsam_1_1_linear_model_strategy/).  |

## Public Functions

|                | Name           |
| -------------- | -------------- |
| | **[LinearModelStrategy](/doxygen/Classes/classsam_1_1_linear_model_strategy/#function-linearmodelstrategy)**() =default |
| | **[LinearModelStrategy](/doxygen/Classes/classsam_1_1_linear_model_strategy/#function-linearmodelstrategy)**(const [Parameters](/doxygen/Classes/structsam_1_1_linear_model_strategy_1_1_parameters/) p) |
| virtual void | **[genData](/doxygen/Classes/classsam_1_1_linear_model_strategy/#function-gendata)**([Experiment](/doxygen/Classes/classsam_1_1_experiment/) * experiment) override<br>Generates data based on the selected DataModel.  |
| virtual std::vector< arma::Row< double > > | **[genNewObservationsForAllGroups](/doxygen/Classes/classsam_1_1_linear_model_strategy/#function-gennewobservationsforallgroups)**([Experiment](/doxygen/Classes/classsam_1_1_experiment/) * experiment, int n_new_obs) override<br>Generates `n_new_obs` new observations for each group.  |

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


## Public Functions Documentation

### function LinearModelStrategy

```cpp
LinearModelStrategy() =default
```


### function LinearModelStrategy

```cpp
inline explicit LinearModelStrategy(
    const Parameters p
)
```


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


Generates the samples

Generate the error terms if specified

This is ugly but it should work


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