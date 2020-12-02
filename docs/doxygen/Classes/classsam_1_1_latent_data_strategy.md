---
title: sam::LatentDataStrategy


---

# sam::LatentDataStrategy




 [More...](#detailed-description)


`#include <DataStrategy.h>`


Inherits from [sam::DataStrategy](/doxygen/Classes/classsam_1_1_data_strategy/)











## Public Functions

|                | Name           |
| -------------- | -------------- |
|  | **[LatentDataStrategy](/doxygen/Classes/classsam_1_1_latent_data_strategy/#function-latentdatastrategy)**()  |
| virtual void | **[genData](/doxygen/Classes/classsam_1_1_latent_data_strategy/#function-gendata)**([Experiment](/doxygen/Classes/classsam_1_1_experiment/) * experiment) override  |
| virtual std::vector< arma::Row< double > > | **[genNewObservationsForAllGroups](/doxygen/Classes/classsam_1_1_latent_data_strategy/#function-gennewobservationsforallgroups)**([Experiment](/doxygen/Classes/classsam_1_1_experiment/) * experiment, int n_new_obs) override  |
| virtual arma::Row< double > | **[genNewObservationsFor](/doxygen/Classes/classsam_1_1_latent_data_strategy/#function-gennewobservationsfor)**([Experiment](/doxygen/Classes/classsam_1_1_experiment/) * experiment, int g, int n_new_obs) override <br>Generate `n_new_obs` new observations for `g` group.  |






## Additional inherited members




**Public Types inherited from [sam::DataStrategy](/doxygen/Classes/classsam_1_1_data_strategy/)**

|                | Name           |
| -------------- | -------------- |
| enum | **[DataModel](/doxygen/Classes/classsam_1_1_data_strategy/#enum-datamodel)** { LinearModel, LatentModel, GradedResponseModel } |






**Public Functions inherited from [sam::DataStrategy](/doxygen/Classes/classsam_1_1_data_strategy/)**

|                | Name           |
| -------------- | -------------- |
| std::unique_ptr< [DataStrategy](/doxygen/Classes/classsam_1_1_data_strategy/) > | **[build](/doxygen/Classes/classsam_1_1_data_strategy/#function-build)**(json & data_strategy_config)  |
| virtual  | **[~DataStrategy](/doxygen/Classes/classsam_1_1_data_strategy/#function-~datastrategy)**() =0 <br>Pure deconstructor of the [DataStrategy](/doxygen/Classes/classsam_1_1_data_strategy/) abstract class.  |
| void | **[loadRawData](/doxygen/Classes/classsam_1_1_data_strategy/#function-loadrawdata)**([Experiment](/doxygen/Classes/classsam_1_1_experiment/) * expr, const std::string & filename)  |







## Detailed Description

```cpp
class sam::LatentDataStrategy;
```













**Note**: [LatentDataStrategy](/doxygen/Classes/classsam_1_1_latent_data_strategy/) will generate individual items, therefore it might be slower than other models. 














A Data Strategy for constructing a general [Structural Equaiton Model](https://en.wikipedia.org/wiki/Structural_equation_modeling).









## Public Functions Documentation

### function LatentDataStrategy

```cpp
inline LatentDataStrategy()
```





























### function genData

```cpp
virtual void genData(
    Experiment * experiment
) override
```


























**Reimplements**: [sam::DataStrategy::genData](/doxygen/Classes/classsam_1_1_data_strategy/#function-gendata)


Construct a structural equation model based on the given paramters specified in the ExperimentSteup. Beside `experiment->measurements`, [LatentDataStrategy](/doxygen/Classes/classsam_1_1_latent_data_strategy/) populates the `experiment->items` as well. 

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


**Parameters**: 

  * **experiment** The pointer to the current experiment 
  * **n_new_obs** The number of new observations to be added







**Return**: An array of new observations 





**Note**: This routine uses the secondary random number stream to avoid conflicting with the main random engine.













**Reimplements**: [sam::DataStrategy::genNewObservationsForAllGroups](/doxygen/Classes/classsam_1_1_data_strategy/#function-gennewobservationsforallgroups)


Generates `n_new_obs` new observations to each group.


### function genNewObservationsFor

```cpp
virtual arma::Row< double > genNewObservationsFor(
    Experiment * experiment,
    int g,
    int n_new_obs
) override
```

Generate `n_new_obs` new observations for `g` group. 

**Parameters**: 

  * **experiment** The pointer to the experiment 
  * **g** The target group 
  * **n_new_obs** The number of new observations







**Return**: An array of new observations 


















**Reimplements**: [sam::DataStrategy::genNewObservationsFor](/doxygen/Classes/classsam_1_1_data_strategy/#function-gennewobservationsfor)










-------------------------------

Updated on 23 November 2020 at 14:03:43 CET