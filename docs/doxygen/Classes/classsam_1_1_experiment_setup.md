---
title: sam::ExperimentSetup
summary: Declaration of ExperimentSetup class. 

---

# sam::ExperimentSetup

**Module:** **[Experiment Modules](/doxygen/Modules/group___experiment/)**



Declaration of [ExperimentSetup]() class.  [More...](#detailed-description)


`#include <ExperimentSetup.h>`

## Public Functions

|                | Name           |
| -------------- | -------------- |
| void | **[setObs](/doxygen/Classes/classsam_1_1_experiment_setup/#function-setobs)**(const json & config, size_t n_c, size_t n_d) |
| void | **[setObs](/doxygen/Classes/classsam_1_1_experiment_setup/#function-setobs)**([Parameter](/doxygen/Classes/classsam_1_1_parameter/)< int > nobs, size_t n_c, size_t n_d) |
| void | **[setObs](/doxygen/Classes/classsam_1_1_experiment_setup/#function-setobs)**(const arma::Row< int > & nobs, size_t n_c, size_t n_d) |
| [ExperimentSetupBuilder](/doxygen/Classes/classsam_1_1_experiment_setup_builder/) | **[create](/doxygen/Classes/classsam_1_1_experiment_setup/#function-create)**() |
| | **[ExperimentSetup](/doxygen/Classes/classsam_1_1_experiment_setup/#function-experimentsetup)**() =default |
| | **[ExperimentSetup](/doxygen/Classes/classsam_1_1_experiment_setup/#function-experimentsetup)**(json & config)<br>Constructs and initializes the [ExperimentSetup](/doxygen/Classes/classsam_1_1_experiment_setup/).  |
| int | **[nc](/doxygen/Classes/classsam_1_1_experiment_setup/#function-nc)**() const<br>Returns the number of conditions.  |
| void | **[setNC](/doxygen/Classes/classsam_1_1_experiment_setup/#function-setnc)**(int n_c)<br>Sets the number of conditions.  |
| int | **[nd](/doxygen/Classes/classsam_1_1_experiment_setup/#function-nd)**() const<br>Returns the number of dependent variables in each conditions.  |
| void | **[setND](/doxygen/Classes/classsam_1_1_experiment_setup/#function-setnd)**(int n_d)<br>Sets the number of dependent variables in each group.  |
| int | **[ng](/doxygen/Classes/classsam_1_1_experiment_setup/#function-ng)**() const<br>Returns the total number of groups.  |
| int | **[nreps](/doxygen/Classes/classsam_1_1_experiment_setup/#function-nreps)**() const<br>Returns the total number of _planned_ replications.  |
| void | **[setNR](/doxygen/Classes/classsam_1_1_experiment_setup/#function-setnr)**(int n_reps)<br>Sets the number of replications.  |
| const arma::Row< int > & | **[nobs](/doxygen/Classes/classsam_1_1_experiment_setup/#function-nobs)**() const<br>Returns the _original_ number of observations per group.  |
| void | **[randomize](/doxygen/Classes/classsam_1_1_experiment_setup/#function-randomize)**()<br>Randomizes the internal parameters of the [Experiment](/doxygen/Classes/classsam_1_1_experiment/), if necessary.  |

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

Declaration of [ExperimentSetup]() class. 

[ExperimentSetup](/doxygen/Classes/classsam_1_1_experiment_setup/) stores all the necessary parameters concerning the experiment design, e.g., number of conditions, number of dependent variables, etc. It also stores a copy of the data, test, and effect strategies' configurations. 

## Public Functions Documentation

### function setObs

```cpp
inline void setObs(
    const json & config,
    size_t n_c,
    size_t n_d
)
```


### function setObs

```cpp
inline void setObs(
    Parameter< int > nobs,
    size_t n_c,
    size_t n_d
)
```


### function setObs

```cpp
inline void setObs(
    const arma::Row< int > & nobs,
    size_t n_c,
    size_t n_d
)
```


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


### function ExperimentSetup

```cpp
explicit ExperimentSetup(
    json & config
)
```

Constructs and initializes the [ExperimentSetup](/doxygen/Classes/classsam_1_1_experiment_setup/). 

**Parameters**: 

  * **config** A JSON configuration object 


This set and calculates design parameters of the experiment. It also archives the definition of data, test, and effect strategies. These archives may later be retrieved by the [Journal](/doxygen/Classes/classsam_1_1_journal/) during the review process.


### function nc

```cpp
inline int nc() const
```

Returns the number of conditions. 

### function setNC

```cpp
inline void setNC(
    int n_c
)
```

Sets the number of conditions. 

### function nd

```cpp
inline int nd() const
```

Returns the number of dependent variables in each conditions. 

### function setND

```cpp
inline void setND(
    int n_d
)
```

Sets the number of dependent variables in each group. 

### function ng

```cpp
inline int ng() const
```

Returns the total number of groups. 

This is an internal parameters and it's mainly used to iterate over conditions and dependent variables. It's calculated as \(n_g = n_c \times n_d\)


### function nreps

```cpp
inline int nreps() const
```

Returns the total number of _planned_ replications. 

### function setNR

```cpp
inline void setNR(
    int n_reps
)
```

Sets the number of replications. 

### function nobs

```cpp
inline const arma::Row< int > & nobs() const
```

Returns the _original_ number of observations per group. 

### function randomize

```cpp
void randomize()
```

Randomizes the internal parameters of the [Experiment](/doxygen/Classes/classsam_1_1_experiment/), if necessary. 

This randomizes all those parameters of the [ExperimentSetup](/doxygen/Classes/classsam_1_1_experiment_setup/) that are defined by a distribution 


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
friend class ExperimentSetupBuilder(
    ExperimentSetupBuilder 
);
```


-------------------------------

Updated on  7 June 2021 at 12:00:21 CEST