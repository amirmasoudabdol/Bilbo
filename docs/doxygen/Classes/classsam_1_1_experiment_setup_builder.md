---
title: sam::ExperimentSetupBuilder


---

# sam::ExperimentSetupBuilder


**Module:** **[Abstract Factory Builders](/doxygen/Modules/group___abstract_builders/)**
















## Public Functions

|                | Name           |
| -------------- | -------------- |
|  | **[ExperimentSetupBuilder](/doxygen/Classes/classsam_1_1_experiment_setup_builder/#function-experimentsetupbuilder)**() =default  |
| [ExperimentSetupBuilder](/doxygen/Classes/classsam_1_1_experiment_setup_builder/) & | **[fromConfigFile](/doxygen/Classes/classsam_1_1_experiment_setup_builder/#function-fromconfigfile)**(json & config) <br>Create and configure a new experiment setup based on the given configuration.  |
| [ExperimentSetupBuilder](/doxygen/Classes/classsam_1_1_experiment_setup_builder/) & | **[setSeed](/doxygen/Classes/classsam_1_1_experiment_setup_builder/#function-setseed)**(const int s) <br>Sets the seed for randomizing setup parameters.  |
| [ExperimentSetupBuilder](/doxygen/Classes/classsam_1_1_experiment_setup_builder/) & | **[setNumConditions](/doxygen/Classes/classsam_1_1_experiment_setup_builder/#function-setnumconditions)**(const int nc)  |
| [ExperimentSetupBuilder](/doxygen/Classes/classsam_1_1_experiment_setup_builder/) & | **[setNumDependentVariables](/doxygen/Classes/classsam_1_1_experiment_setup_builder/#function-setnumdependentvariables)**(const int nd)  |
| [ExperimentSetupBuilder](/doxygen/Classes/classsam_1_1_experiment_setup_builder/) & | **[setNumItems](/doxygen/Classes/classsam_1_1_experiment_setup_builder/#function-setnumitems)**(const int ni)  |
| [ExperimentSetupBuilder](/doxygen/Classes/classsam_1_1_experiment_setup_builder/) & | **[setNumObservations](/doxygen/Classes/classsam_1_1_experiment_setup_builder/#function-setnumobservations)**(const int nobs)  |
| [ExperimentSetupBuilder](/doxygen/Classes/classsam_1_1_experiment_setup_builder/) & | **[setNumObservations](/doxygen/Classes/classsam_1_1_experiment_setup_builder/#function-setnumobservations)**(const arma::Row< int > & nobs)  |
| [ExperimentSetupBuilder](/doxygen/Classes/classsam_1_1_experiment_setup_builder/) & | **[setTestStrategyParameters](/doxygen/Classes/classsam_1_1_experiment_setup_builder/#function-setteststrategyparameters)**(json & test_strategy_config)  |
| [ExperimentSetupBuilder](/doxygen/Classes/classsam_1_1_experiment_setup_builder/) & | **[setDataStrategyParameters](/doxygen/Classes/classsam_1_1_experiment_setup_builder/#function-setdatastrategyparameters)**(json & data_strategy_config)  |
| [ExperimentSetupBuilder](/doxygen/Classes/classsam_1_1_experiment_setup_builder/) & | **[setEffectStrategyParameters](/doxygen/Classes/classsam_1_1_experiment_setup_builder/#function-seteffectstrategyparameters)**(json & effect_strategy_config)  |
| [ExperimentSetup](/doxygen/Classes/classsam_1_1_experiment_setup/) | **[build](/doxygen/Classes/classsam_1_1_experiment_setup_builder/#function-build)**()  |
















## Public Functions Documentation

### function `ExperimentSetupBuilder`

```cpp
ExperimentSetupBuilder() =default
```





























### function `fromConfigFile`

```cpp
ExperimentSetupBuilder & fromConfigFile(
    json & config
)
```

Create and configure a new experiment setup based on the given configuration. 




























### function `setSeed`

```cpp
inline ExperimentSetupBuilder & setSeed(
    const int s
)
```

Sets the seed for randomizing setup parameters. 

**Parameters**: 

  * **`s`** seed







**Return**: A reference to the builder 





















### function `setNumConditions`

```cpp
inline ExperimentSetupBuilder & setNumConditions(
    const int nc
)
```





























### function `setNumDependentVariables`

```cpp
inline ExperimentSetupBuilder & setNumDependentVariables(
    const int nd
)
```





























### function `setNumItems`

```cpp
inline ExperimentSetupBuilder & setNumItems(
    const int ni
)
```





























### function `setNumObservations`

```cpp
inline ExperimentSetupBuilder & setNumObservations(
    const int nobs
)
```





























### function `setNumObservations`

```cpp
inline ExperimentSetupBuilder & setNumObservations(
    const arma::Row< int > & nobs
)
```




























Todo: Recover this, it's been removed during the [Parameter](/doxygen/Classes/classsam_1_1_parameter/) transition 

### function `setTestStrategyParameters`

```cpp
inline ExperimentSetupBuilder & setTestStrategyParameters(
    json & test_strategy_config
)
```





























### function `setDataStrategyParameters`

```cpp
inline ExperimentSetupBuilder & setDataStrategyParameters(
    json & data_strategy_config
)
```





























### function `setEffectStrategyParameters`

```cpp
inline ExperimentSetupBuilder & setEffectStrategyParameters(
    json & effect_strategy_config
)
```





























### function `build`

```cpp
inline ExperimentSetup build()
```



































