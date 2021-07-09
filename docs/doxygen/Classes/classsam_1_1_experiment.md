---
title: sam::Experiment
summary: Experiment encapsulates data and methods needed by the Researcher to conduct its research. 

---

# sam::Experiment

**Module:** **[Experiment Modules](/doxygen/Modules/group___experiment/)**



[Experiment]() encapsulates data and methods needed by the [Researcher]() to conduct its research.  [More...](#detailed-description)


`#include <Experiment.h>`

## Public Functions

|                | Name           |
| -------------- | -------------- |
| [DependentVariable](/doxygen/Classes/classsam_1_1_dependent_variable/) & | **[operator[]](/doxygen/Classes/classsam_1_1_experiment/#function-operator[])**(std::size_t idx) |
| const [DependentVariable](/doxygen/Classes/classsam_1_1_dependent_variable/) & | **[operator[]](/doxygen/Classes/classsam_1_1_experiment/#function-operator[])**(std::size_t idx) const |
| auto | **[begin](/doxygen/Classes/classsam_1_1_experiment/#function-begin)**() |
| auto | **[end](/doxygen/Classes/classsam_1_1_experiment/#function-end)**() |
| auto | **[begin](/doxygen/Classes/classsam_1_1_experiment/#function-begin)**() const |
| auto | **[end](/doxygen/Classes/classsam_1_1_experiment/#function-end)**() const |
| | **[Experiment](/doxygen/Classes/classsam_1_1_experiment/#function-experiment)**() =default<br>Default constructor.  |
| | **[Experiment](/doxygen/Classes/classsam_1_1_experiment/#function-experiment)**(json & experiment_config)<br>Constructs an [Experiment](/doxygen/Classes/classsam_1_1_experiment/) object using the given JSON configuration.  |
| | **[Experiment](/doxygen/Classes/classsam_1_1_experiment/#function-experiment)**([ExperimentSetup](/doxygen/Classes/classsam_1_1_experiment_setup/) & e)<br>Constructs an [Experiment](/doxygen/Classes/classsam_1_1_experiment/) using an already initialized [ExperimentSetup]().  |
| | **[Experiment](/doxygen/Classes/classsam_1_1_experiment/#function-experiment)**([ExperimentSetup](/doxygen/Classes/classsam_1_1_experiment_setup/) & e, std::shared_ptr< [DataStrategy](/doxygen/Classes/classsam_1_1_data_strategy/) > & ds, std::shared_ptr< [TestStrategy](/doxygen/Classes/classsam_1_1_test_strategy/) > & ts, std::shared_ptr< [EffectStrategy](/doxygen/Classes/classsam_1_1_effect_strategy/) > & es)<br>Directly constructs an [Experiment](/doxygen/Classes/classsam_1_1_experiment/) from its components.  |
| void | **[addNewCondition](/doxygen/Classes/classsam_1_1_experiment/#function-addnewcondition)**() |
| void | **[addNewCondition](/doxygen/Classes/classsam_1_1_experiment/#function-addnewcondition)**(const std::vector< [DependentVariable](/doxygen/Classes/classsam_1_1_dependent_variable/) > & dvs) |
| void | **[addNewDependentVariable](/doxygen/Classes/classsam_1_1_experiment/#function-addnewdependentvariable)**(const [DependentVariable](/doxygen/Classes/classsam_1_1_dependent_variable/) & dv)<br>Adds a new dependent variable to the list.  |
| void | **[addNewCandidates](/doxygen/Classes/classsam_1_1_experiment/#function-addnewcandidates)**(const std::vector< [Submission](/doxygen/Classes/classsam_1_1_submission/) > & subs)<br>Adds new submissions to the list of submissions.  |
| void | **[setHackedStatus](/doxygen/Classes/classsam_1_1_experiment/#function-sethackedstatus)**(const bool status)<br>Sets the hacked status of the experiment.  |
| void | **[setPublishedStatus](/doxygen/Classes/classsam_1_1_experiment/#function-setpublishedstatus)**(const bool status)<br>Sets the published status of the experiment.  |
| void | **[setHackedStatusOf](/doxygen/Classes/classsam_1_1_experiment/#function-sethackedstatusof)**(const std::vector< size_t > & idxs, const bool status)<br>Sets the hacked status of a group of dvs.  |
| void | **[setCandidateStatusOf](/doxygen/Classes/classsam_1_1_experiment/#function-setcandidatestatusof)**(const std::vector< size_t > & idxs, const bool status)<br>Sets the candidate status of a group of dvs.  |
| bool | **[isHacked](/doxygen/Classes/classsam_1_1_experiment/#function-ishacked)**() const<br>Returns true if the experiment is hacked.  |
| bool | **[isModified](/doxygen/Classes/classsam_1_1_experiment/#function-ismodified)**() const<br>Returns true if the experiment has been modified in anyway.  |
| bool | **[hasCandidates](/doxygen/Classes/classsam_1_1_experiment/#function-hascandidates)**() const<br>Returns true if there is an candidate in the experiment.  |
| bool | **[hasCovariants](/doxygen/Classes/classsam_1_1_experiment/#function-hascovariants)**() const<br>Returns true if there is an candidate in the experiment.  |
| bool | **[isPublished](/doxygen/Classes/classsam_1_1_experiment/#function-ispublished)**() const<br>Returns true if the experiment has been published by the [Journal]().  |
| size_t | **[nCandidates](/doxygen/Classes/classsam_1_1_experiment/#function-ncandidates)**() const<br>Returns the number of candidate DVs.  |
| int | **[nCovariants](/doxygen/Classes/classsam_1_1_experiment/#function-ncovariants)**() const |
| void | **[reset](/doxygen/Classes/classsam_1_1_experiment/#function-reset)**()<br>Clears and re-initializes the dependent variables.  |
| void | **[generateData](/doxygen/Classes/classsam_1_1_experiment/#function-generatedata)**()<br>Uses the [DataStrategy](/doxygen/Classes/classsam_1_1_data_strategy/) to populate every DVs with raw the data.  |
| void | **[generateCovariants](/doxygen/Classes/classsam_1_1_experiment/#function-generatecovariants)**()<br>Generates covariants data.  |
| void | **[calculateStatistics](/doxygen/Classes/classsam_1_1_experiment/#function-calculatestatistics)**()<br>Asks each [DependentVariable](/doxygen/Classes/classsam_1_1_dependent_variable/) to update its general statistics, e.g., mean, var.  |
| void | **[calculateTests](/doxygen/Classes/classsam_1_1_experiment/#function-calculatetests)**()<br>Uses the [TestStrategy]() to run the statistical test.  |
| void | **[calculateEffects](/doxygen/Classes/classsam_1_1_experiment/#function-calculateeffects)**()<br>Uses the [EffectStrategy](/doxygen/Classes/classsam_1_1_effect_strategy/) to calculates the effect sizes.  |
| void | **[recalculateEverything](/doxygen/Classes/classsam_1_1_experiment/#function-recalculateeverything)**()<br>Runs [calculateStatistics()](/doxygen/Classes/classsam_1_1_experiment/#function-calculatestatistics), [calculateTests()](/doxygen/Classes/classsam_1_1_experiment/#function-calculatetests), and [calculateEffects()](/doxygen/Classes/classsam_1_1_experiment/#function-calculateeffects) in order.  |
| void | **[clear](/doxygen/Classes/classsam_1_1_experiment/#function-clear)**()<br>Clears the content of the experiment.  |
| void | **[setTestStrategy](/doxygen/Classes/classsam_1_1_experiment/#function-setteststrategy)**(std::shared_ptr< [TestStrategy](/doxygen/Classes/classsam_1_1_test_strategy/) > & ts) |
| void | **[setDataStrategy](/doxygen/Classes/classsam_1_1_experiment/#function-setdatastrategy)**(std::shared_ptr< [DataStrategy](/doxygen/Classes/classsam_1_1_data_strategy/) > & ds) |
| void | **[setEffectSizeEstimator](/doxygen/Classes/classsam_1_1_experiment/#function-seteffectsizeestimator)**(std::shared_ptr< [EffectStrategy](/doxygen/Classes/classsam_1_1_effect_strategy/) > & es) |

## Public Attributes

|                | Name           |
| -------------- | -------------- |
| int | **[simid](/doxygen/Classes/classsam_1_1_experiment/#variable-simid)**  |
| int | **[exprid](/doxygen/Classes/classsam_1_1_experiment/#variable-exprid)**  |
| int | **[repid](/doxygen/Classes/classsam_1_1_experiment/#variable-repid)**  |
| int | **[n_covariants](/doxygen/Classes/classsam_1_1_experiment/#variable-n_covariants)** <br>Indicates the number of covariants.  |
| arma::Mat< int > | **[covariants](/doxygen/Classes/classsam_1_1_experiment/#variable-covariants)**  |
| [ExperimentSetup](/doxygen/Classes/classsam_1_1_experiment_setup/) | **[setup](/doxygen/Classes/classsam_1_1_experiment/#variable-setup)**  |
| std::shared_ptr< [DataStrategy](/doxygen/Classes/classsam_1_1_data_strategy/) > | **[data_strategy](/doxygen/Classes/classsam_1_1_experiment/#variable-data_strategy)**  |
| std::shared_ptr< [TestStrategy](/doxygen/Classes/classsam_1_1_test_strategy/) > | **[test_strategy](/doxygen/Classes/classsam_1_1_experiment/#variable-test_strategy)**  |
| std::shared_ptr< [EffectStrategy](/doxygen/Classes/classsam_1_1_effect_strategy/) > | **[effect_strategy](/doxygen/Classes/classsam_1_1_experiment/#variable-effect_strategy)**  |
| std::vector< [DependentVariable](/doxygen/Classes/classsam_1_1_dependent_variable/) > | **[dvs_](/doxygen/Classes/classsam_1_1_experiment/#variable-dvs_)**  |
| std::optional< std::vector< [Submission](/doxygen/Classes/classsam_1_1_submission/) > > | **[candidates](/doxygen/Classes/classsam_1_1_experiment/#variable-candidates)** <br>List of all possible candidates from this experiment so far!  |

## Detailed Description

```cpp
class sam::Experiment;
```

[Experiment]() encapsulates data and methods needed by the [Researcher]() to conduct its research. 

[Experiment](/doxygen/Classes/classsam_1_1_experiment/) has a full access to all data-related strategies, e.g., [DataStrategy](/doxygen/Classes/classsam_1_1_data_strategy/), [TestStrategy](/doxygen/Classes/classsam_1_1_test_strategy/), and [EffectStrategy](/doxygen/Classes/classsam_1_1_effect_strategy/). It also contains the raw research data in the form of list of DependentVariable(s). Moreover, the [Experiment](/doxygen/Classes/classsam_1_1_experiment/) stores a copy of the [ExperimentSetup](/doxygen/Classes/classsam_1_1_experiment_setup/) where most study parameters are stored in. 

## Public Functions Documentation

### function operator[]

```cpp
DependentVariable & operator[](
    std::size_t idx
)
```


**Todo**: I'm not the fan of this `find_if` here, and I think I can do better. 

I think I can avoid this search if I use std::reference_wrapper 

These operators are returning the correct group, even if the group list is not sorted.


### function operator[]

```cpp
const DependentVariable & operator[](
    std::size_t idx
) const
```


### function begin

```cpp
inline auto begin()
```


### function end

```cpp
inline auto end()
```


### function begin

```cpp
inline auto begin() const
```


### function end

```cpp
inline auto end() const
```


### function Experiment

```cpp
Experiment() =default
```

Default constructor. 

### function Experiment

```cpp
Experiment(
    json & experiment_config
)
```

Constructs an [Experiment](/doxygen/Classes/classsam_1_1_experiment/) object using the given JSON configuration. 

This constructs an [Experiment](/doxygen/Classes/classsam_1_1_experiment/), and allocates the resources necessary for the experiment to setup its dependent variables, etc. Using the config parameters of the Data, Test, and Effect strategies, it also initializes those to be used by the [Researcher](/doxygen/Classes/classsam_1_1_researcher/) or the [Experiment](/doxygen/Classes/classsam_1_1_experiment/) itself 


### function Experiment

```cpp
Experiment(
    ExperimentSetup & e
)
```

Constructs an [Experiment](/doxygen/Classes/classsam_1_1_experiment/) using an already initialized [ExperimentSetup](). 

**Note**: This can be used in cases where the underlying strategies should be preserved while some experiment parameters needs to be modified. 

Since [ExperimentSetup](/doxygen/Classes/classsam_1_1_experiment_setup/) already contains the definition of Data, Test, and Effect strategies, this method accepts the [ExperimentSetup](/doxygen/Classes/classsam_1_1_experiment_setup/) as it is, and only initialize those strategies.


### function Experiment

```cpp
Experiment(
    ExperimentSetup & e,
    std::shared_ptr< DataStrategy > & ds,
    std::shared_ptr< TestStrategy > & ts,
    std::shared_ptr< EffectStrategy > & es
)
```

Directly constructs an [Experiment](/doxygen/Classes/classsam_1_1_experiment/) from its components. 

**Note**: This is mainly used by the ExperimentBuilder 

This directly constructs the experiment by directly constructing its internal based on the set of given parameters.


### function addNewCondition

```cpp
void addNewCondition()
```


Adds a new condition @TODO TO BE IMPLEMENTED! 


### function addNewCondition

```cpp
void addNewCondition(
    const std::vector< DependentVariable > & dvs
)
```


Adds a new condition @TODO TO BE IMPLEMENTED! 


### function addNewDependentVariable

```cpp
void addNewDependentVariable(
    const DependentVariable & dv
)
```

Adds a new dependent variable to the list. 

### function addNewCandidates

```cpp
void addNewCandidates(
    const std::vector< Submission > & subs
)
```

Adds new submissions to the list of submissions. 

Adds new candidates to the list of selected candidates 


### function setHackedStatus

```cpp
void setHackedStatus(
    const bool status
)
```

Sets the hacked status of the experiment. 

**Attention**: Setting this to `true` will make the `[isHacked()](/doxygen/Classes/classsam_1_1_experiment/#function-ishacked)` to return `true`. Basically, this overrules the status of the dependent variables, but it doesn't overwrite them! 

It sets the overall hacked status of the experiment to status.


### function setPublishedStatus

```cpp
void setPublishedStatus(
    const bool status
)
```

Sets the published status of the experiment. 

### function setHackedStatusOf

```cpp
void setHackedStatusOf(
    const std::vector< size_t > & idxs,
    const bool status
)
```

Sets the hacked status of a group of dvs. 

### function setCandidateStatusOf

```cpp
void setCandidateStatusOf(
    const std::vector< size_t > & idxs,
    const bool status
)
```

Sets the candidate status of a group of dvs. 

### function isHacked

```cpp
bool isHacked() const
```

Returns true if the experiment is hacked. 

An experiment is hacked if its hacked status has been set to `true`, or one of its dependent variables has been flagged as hacked 


### function isModified

```cpp
bool isModified() const
```

Returns true if the experiment has been modified in anyway. 

### function hasCandidates

```cpp
bool hasCandidates() const
```

Returns true if there is an candidate in the experiment. 

### function hasCovariants

```cpp
bool hasCovariants() const
```

Returns true if there is an candidate in the experiment. 

### function isPublished

```cpp
bool isPublished() const
```

Returns true if the experiment has been published by the [Journal](). 

### function nCandidates

```cpp
size_t nCandidates() const
```

Returns the number of candidate DVs. 

### function nCovariants

```cpp
int nCovariants() const
```


### function reset

```cpp
void reset()
```

Clears and re-initializes the dependent variables. 

This cleanup the [Experiment](/doxygen/Classes/classsam_1_1_experiment/), and reallocate its memory again. Technically, preparing the experiment for a new run. 


### function generateData

```cpp
void generateData()
```

Uses the [DataStrategy](/doxygen/Classes/classsam_1_1_data_strategy/) to populate every DVs with raw the data. 

### function generateCovariants

```cpp
void generateCovariants()
```

Generates covariants data. 

@Todo Check if all groups are the same size


### function calculateStatistics

```cpp
void calculateStatistics()
```

Asks each [DependentVariable](/doxygen/Classes/classsam_1_1_dependent_variable/) to update its general statistics, e.g., mean, var. 

### function calculateTests

```cpp
void calculateTests()
```

Uses the [TestStrategy]() to run the statistical test. 

### function calculateEffects

```cpp
void calculateEffects()
```

Uses the [EffectStrategy](/doxygen/Classes/classsam_1_1_effect_strategy/) to calculates the effect sizes. 

### function recalculateEverything

```cpp
void recalculateEverything()
```

Runs [calculateStatistics()](/doxygen/Classes/classsam_1_1_experiment/#function-calculatestatistics), [calculateTests()](/doxygen/Classes/classsam_1_1_experiment/#function-calculatetests), and [calculateEffects()](/doxygen/Classes/classsam_1_1_experiment/#function-calculateeffects) in order. 

### function clear

```cpp
void clear()
```

Clears the content of the experiment. 

**Todo**: I think this is a bad implementation, and I should probably just discard the list of DVs and recreate them for the new [Experiment](/doxygen/Classes/classsam_1_1_experiment/), which is probably safer! Something like `dvs_.clear()`

It clears every DVs individually, and also sort them back into the correct order.


### function setTestStrategy

```cpp
inline void setTestStrategy(
    std::shared_ptr< TestStrategy > & ts
)
```


**Parameters**: 

  * **t** A reference to a Test Strategy instance 


Set or re-set the Test Strategy


### function setDataStrategy

```cpp
inline void setDataStrategy(
    std::shared_ptr< DataStrategy > & ds
)
```


**Parameters**: 

  * **d** A reference to a Data Strategy instance 


Set or re-set the Data Strategy


### function setEffectSizeEstimator

```cpp
inline void setEffectSizeEstimator(
    std::shared_ptr< EffectStrategy > & es
)
```


**Parameters**: 

  * **es** A reference to an Effect Strategy instance. 


Set or re-set the Effect Strategy


## Public Attributes Documentation

### variable simid

```cpp
int simid {0};
```


### variable exprid

```cpp
int exprid {0};
```


### variable repid

```cpp
int repid {0};
```


### variable n_covariants

```cpp
int n_covariants {0};
```

Indicates the number of covariants. 

### variable covariants

```cpp
arma::Mat< int > covariants;
```


### variable setup

```cpp
ExperimentSetup setup;
```


An instance of the [ExperimentSetup](/doxygen/Classes/classsam_1_1_experiment_setup/). All other strategies can access and query it for meta information about the [Experiment](/doxygen/Classes/classsam_1_1_experiment/)


### variable data_strategy

```cpp
std::shared_ptr< DataStrategy > data_strategy;
```


### variable test_strategy

```cpp
std::shared_ptr< TestStrategy > test_strategy;
```


### variable effect_strategy

```cpp
std::shared_ptr< EffectStrategy > effect_strategy;
```


### variable dvs_

```cpp
std::vector< DependentVariable > dvs_;
```


### variable candidates

```cpp
std::optional< std::vector< Submission > > candidates;
```

List of all possible candidates from this experiment so far! 

**Note**: This is not yet in use! 

This is a list of any dvs that has been flagged as submissions during the lifespan of this experiment


-------------------------------

Updated on 29 June 2021 at 16:13:47 CEST