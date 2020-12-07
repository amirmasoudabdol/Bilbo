---
title: sam::ExperimentSetup
summary: Define a class for ExperimentSetup.  

---

# sam::ExperimentSetup


**Module:** **[Experiment Modules](/doxygen/Modules/group___experiment/)**

Define a class for [ExperimentSetup]().  [More...](#detailed-description)


`#include <ExperimentSetup.h>`













## Public Functions

|                | Name           |
| -------------- | -------------- |
| [ExperimentSetupBuilder](/doxygen/Classes/classsam_1_1_experiment_setup_builder/) | **[create](/doxygen/Classes/classsam_1_1_experiment_setup/#function-create)**()  |
|  | **[ExperimentSetup](/doxygen/Classes/classsam_1_1_experiment_setup/#function-experimentsetup)**() =default  |
|  | **[ExperimentSetup](/doxygen/Classes/classsam_1_1_experiment_setup/#function-experimentsetup)**(json & config)  |
| const int | **[nc](/doxygen/Classes/classsam_1_1_experiment_setup/#function-nc)**() const  |
| const int | **[nd](/doxygen/Classes/classsam_1_1_experiment_setup/#function-nd)**() const  |
| const int | **[ng](/doxygen/Classes/classsam_1_1_experiment_setup/#function-ng)**() const  |
| const int | **[nreps](/doxygen/Classes/classsam_1_1_experiment_setup/#function-nreps)**() const  |
| const arma::Row< int > & | **[nobs](/doxygen/Classes/classsam_1_1_experiment_setup/#function-nobs)**() const  |
| void | **[randomizeTheParameters](/doxygen/Classes/classsam_1_1_experiment_setup/#function-randomizetheparameters)**()  |


## Public Attributes

|                | Name           |
| -------------- | -------------- |
| json | **[tsp_conf](/doxygen/Classes/classsam_1_1_experiment_setup/#variable-tsp_conf)** <br>Test Strategy Parameters.  |
| json | **[dsp_conf](/doxygen/Classes/classsam_1_1_experiment_setup/#variable-dsp_conf)** <br>Data Strategy Parameters.  |
| json | **[esp_conf](/doxygen/Classes/classsam_1_1_experiment_setup/#variable-esp_conf)** <br>Effect Estimator Parameters.  |


## Friends

|                | Name           |
| -------------- | -------------- |
| class | **[ExperimentSetupBuilder](/doxygen/Classes/classsam_1_1_experiment_setup/#friend-experimentsetupbuilder)**  |




## Detailed Description

```cpp
class sam::ExperimentSetup;
```

Define a class for [ExperimentSetup](). 


























[ExperimentSetup](/doxygen/Classes/classsam_1_1_experiment_setup/) contains the necessary parameters for initiating and generating the data needed for the [Experiment](/doxygen/Classes/classsam_1_1_experiment/). 









## Public Functions Documentation

### function create

```cpp
static ExperimentSetupBuilder create()
```








**Return**: An instance of the builder. 



















Create a new [ExperimentSetup](/doxygen/Classes/classsam_1_1_experiment_setup/) by invoking a [ExperimentSetupBuilder](/doxygen/Classes/classsam_1_1_experiment_setup_builder/).


### function ExperimentSetup

```cpp
ExperimentSetup() =default
```



























Default constructor of the [ExperimentSetup](/doxygen/Classes/classsam_1_1_experiment_setup/). This is necessary because of the [ExperimentSetupBuilder](/doxygen/Classes/classsam_1_1_experiment_setup_builder/)


### function ExperimentSetup

```cpp
explicit ExperimentSetup(
    json & config
)
```





























### function nc

```cpp
inline const int nc() const
```





























### function nd

```cpp
inline const int nd() const
```





























### function ng

```cpp
inline const int ng() const
```





























### function nreps

```cpp
inline const int nreps() const
```





























### function nobs

```cpp
inline const arma::Row< int > & nobs() const
```





























### function randomizeTheParameters

```cpp
void randomizeTheParameters()
```































## Public Attributes Documentation

### variable tsp_conf

```cpp
json tsp_conf;
```

Test Strategy Parameters. 




























### variable dsp_conf

```cpp
json dsp_conf;
```

Data Strategy Parameters. 




























### variable esp_conf

```cpp
json esp_conf;
```

Effect Estimator Parameters. 






























## Friends

### friend ExperimentSetupBuilder

```cpp
friend class ExperimentSetupBuilder;
```































-------------------------------

Updated on  7 December 2020 at 13:20:09 CET