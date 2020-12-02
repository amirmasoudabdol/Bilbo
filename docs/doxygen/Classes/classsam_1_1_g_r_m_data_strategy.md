---
title: sam::GRMDataStrategy
summary: Simulate data from Graded Response Model.  

---

# sam::GRMDataStrategy




Simulate data from Graded Response Model.  [More...](#detailed-description)


`#include <DataStrategy.h>`


Inherits from [sam::DataStrategy](/doxygen/Classes/classsam_1_1_data_strategy/)



## Public Classes

|                | Name           |
| -------------- | -------------- |
| struct | **[Parameters](/doxygen/Classes/structsam_1_1_g_r_m_data_strategy_1_1_parameters/)**  |








## Public Functions

|                | Name           |
| -------------- | -------------- |
|  | **[GRMDataStrategy](/doxygen/Classes/classsam_1_1_g_r_m_data_strategy/#function-grmdatastrategy)**()  |
|  | **[GRMDataStrategy](/doxygen/Classes/classsam_1_1_g_r_m_data_strategy/#function-grmdatastrategy)**(const [Parameters](/doxygen/Classes/structsam_1_1_g_r_m_data_strategy_1_1_parameters/) & p)  |
| virtual void | **[genData](/doxygen/Classes/classsam_1_1_g_r_m_data_strategy/#function-gendata)**([Experiment](/doxygen/Classes/classsam_1_1_experiment/) * experiment) override  |
| virtual std::vector< arma::Row< double > > | **[genNewObservationsForAllGroups](/doxygen/Classes/classsam_1_1_g_r_m_data_strategy/#function-gennewobservationsforallgroups)**([Experiment](/doxygen/Classes/classsam_1_1_experiment/) * experiment, int n_new_obs) override  |
| virtual arma::Row< double > | **[genNewObservationsFor](/doxygen/Classes/classsam_1_1_g_r_m_data_strategy/#function-gennewobservationsfor)**([Experiment](/doxygen/Classes/classsam_1_1_experiment/) * experiment, int g, int n_new_obs) override <br>Generate `n_new_obs` new observations for `g` group.  |






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
class sam::GRMDataStrategy;
```

Simulate data from Graded Response Model. 












**Note**: :

* DVs in GRM are distinguished by their participant abilities to answer tests. Therefore, we'll have `ng_` number of `abilities`. This value is being used to, in each group, to initialize a normal distribution of `\theta ~ N(abilitis[i], 1)`.
* $ \beta $























## Public Functions Documentation

### function GRMDataStrategy

```cpp
inline GRMDataStrategy()
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


**Parameters**: 

  * **experiment** A pointer to an [Experiment](/doxygen/Classes/classsam_1_1_experiment/) object 

























**Reimplements**: [sam::DataStrategy::genData](/doxygen/Classes/classsam_1_1_data_strategy/#function-gendata)


Populates the `experiment->measurements` with data based on the parameters specified in `setup`.


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

Updated on  2 December 2020 at 14:48:54 CET