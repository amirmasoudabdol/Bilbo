---
title: sam::LatentDataStrategy
summary: ⚠️ TO BE IMPLEMENTED! 

---

# sam::LatentDataStrategy

**Module:** **[Data Strategies](/doxygen/Modules/group___data_strategies/)**



⚠️ TO BE IMPLEMENTED!  [More...](#detailed-description)


`#include <DataStrategy.h>`

Inherits from [sam::DataStrategy](/doxygen/Classes/classsam_1_1_data_strategy/)

## Public Functions

|                | Name           |
| -------------- | -------------- |
| | **[LatentDataStrategy](/doxygen/Classes/classsam_1_1_latent_data_strategy/#function-latentdatastrategy)**() =default |
| virtual void | **[genData](/doxygen/Classes/classsam_1_1_latent_data_strategy/#function-gendata)**([Experiment](/doxygen/Classes/classsam_1_1_experiment/) * experiment) override |
| virtual std::vector< arma::Row< double > > | **[genNewObservationsForAllGroups](/doxygen/Classes/classsam_1_1_latent_data_strategy/#function-gennewobservationsforallgroups)**([Experiment](/doxygen/Classes/classsam_1_1_experiment/) * experiment, int n_new_obs) override<br>Generates `n_new_obs` new observations for each group.  |

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
class sam::LatentDataStrategy;
```

⚠️ TO BE IMPLEMENTED! 

**Note**: [LatentDataStrategy](/doxygen/Classes/classsam_1_1_latent_data_strategy/) will generate individual items, therefore it might be slower than other models. 

**Warning**: To be implemented!

A Data Strategy for constructing a general [Structural Equation Model](https://en.wikipedia.org/wiki/Structural_equation_modeling).

## Public Functions Documentation

### function LatentDataStrategy

```cpp
LatentDataStrategy() =default
```


### function genData

```cpp
virtual void genData(
    Experiment * experiment
) override
```


**Reimplements**: [sam::DataStrategy::genData](/doxygen/Classes/classsam_1_1_data_strategy/#function-gendata)


Construct a structural equation model based on the given parameters specified in the [ExperimentSetup](/doxygen/Classes/classsam_1_1_experiment_setup/). Beside `experiment->measurements`, [LatentDataStrategy](/doxygen/Classes/classsam_1_1_latent_data_strategy/) populates the `experiment->items` as well. 


dvSigma->data = flatten(experiment->setup.getTrueValueOf("sigm")).data();

this->mainRngStream->mvnorm_n(allErrorMeans, allErrorsSigma, allErrors);

gsl_vector_set(itemMeans, r, gsl_stats_mean(tmpRow->data, 1, nobs));


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