---
title: sam::Experiment
summary: Experiment class declaration.  

---

# sam::Experiment




[Experiment]() class declaration.  [More...](#detailed-description)


`#include <Experiment.h>`













## Public Functions

|                | Name           |
| -------------- | -------------- |
|  | **[Experiment](/doxygen/Classes/classsam_1_1_experiment/#function-experiment)**() =default  |
|  | **[Experiment](/doxygen/Classes/classsam_1_1_experiment/#function-experiment)**(json & experiment_config)  |
|  | **[Experiment](/doxygen/Classes/classsam_1_1_experiment/#function-experiment)**([ExperimentSetup](/doxygen/Classes/classsam_1_1_experiment_setup/) & e)  |
|  | **[Experiment](/doxygen/Classes/classsam_1_1_experiment/#function-experiment)**([ExperimentSetup](/doxygen/Classes/classsam_1_1_experiment_setup/) & e, std::shared_ptr< [DataStrategy](/doxygen/Classes/classsam_1_1_data_strategy/) > & ds, std::shared_ptr< [TestStrategy](/doxygen/Classes/classsam_1_1_test_strategy/) > & ts, std::shared_ptr< [EffectStrategy](/doxygen/Classes/classsam_1_1_effect_strategy/) > & efs)  |
| [Group](/doxygen/Classes/classsam_1_1_group/) & | **[operator[]](/doxygen/Classes/classsam_1_1_experiment/#function-operator[])**(std::size_t idx)  |
| const [Group](/doxygen/Classes/classsam_1_1_group/) & | **[operator[]](/doxygen/Classes/classsam_1_1_experiment/#function-operator[])**(std::size_t idx) const  |
| [Group](/doxygen/Classes/classsam_1_1_group/) & | **[get_group](/doxygen/Classes/classsam_1_1_experiment/#function-get_group)**(std::size_t idx)  |
| const [Group](/doxygen/Classes/classsam_1_1_group/) & | **[get_group](/doxygen/Classes/classsam_1_1_experiment/#function-get_group)**(std::size_t idx) const  |
| auto | **[begin](/doxygen/Classes/classsam_1_1_experiment/#function-begin)**()  |
| auto | **[end](/doxygen/Classes/classsam_1_1_experiment/#function-end)**()  |
| auto | **[begin](/doxygen/Classes/classsam_1_1_experiment/#function-begin)**() const  |
| auto | **[end](/doxygen/Classes/classsam_1_1_experiment/#function-end)**() const  |
| void | **[runTest](/doxygen/Classes/classsam_1_1_experiment/#function-runtest)**() <br>Runs the Test Strategy.  |
| void | **[setTestStrategy](/doxygen/Classes/classsam_1_1_experiment/#function-setteststrategy)**(std::shared_ptr< [TestStrategy](/doxygen/Classes/classsam_1_1_test_strategy/) > & ts)  |
| void | **[setDataStrategy](/doxygen/Classes/classsam_1_1_experiment/#function-setdatastrategy)**(std::shared_ptr< [DataStrategy](/doxygen/Classes/classsam_1_1_data_strategy/) > & ds)  |
| void | **[setEffectSizeEstimator](/doxygen/Classes/classsam_1_1_experiment/#function-seteffectsizeestimator)**(std::shared_ptr< [EffectStrategy](/doxygen/Classes/classsam_1_1_effect_strategy/) > & es)  |
| void | **[initExperiment](/doxygen/Classes/classsam_1_1_experiment/#function-initexperiment)**()  |
| void | **[generateData](/doxygen/Classes/classsam_1_1_experiment/#function-generatedata)**() <br>Use the `data_strategy` to generate the data.  |
| void | **[preProcessData](/doxygen/Classes/classsam_1_1_experiment/#function-preprocessdata)**()  |
| void | **[calculateStatistics](/doxygen/Classes/classsam_1_1_experiment/#function-calculatestatistics)**()  |
| void | **[calculateEffects](/doxygen/Classes/classsam_1_1_experiment/#function-calculateeffects)**()  |
| void | **[recalculateEverything](/doxygen/Classes/classsam_1_1_experiment/#function-recalculateeverything)**()  |
| void | **[recalculateEverythingForGroup](/doxygen/Classes/classsam_1_1_experiment/#function-recalculateeverythingforgroup)**(size_t inx)  |
| void | **[clear](/doxygen/Classes/classsam_1_1_experiment/#function-clear)**() <br>Clear contents of the experiment.  |


## Public Attributes

|                | Name           |
| -------------- | -------------- |
| int | **[exprid](/doxygen/Classes/classsam_1_1_experiment/#variable-exprid)**  |
| int | **[repid](/doxygen/Classes/classsam_1_1_experiment/#variable-repid)**  |
| bool | **[is_hacked](/doxygen/Classes/classsam_1_1_experiment/#variable-is_hacked)** <br>Indicates if any hacking routine has been applied on the experiment.  |
| std::vector< int > | **[hacks_history](/doxygen/Classes/classsam_1_1_experiment/#variable-hacks_history)**  |
| bool | **[is_published](/doxygen/Classes/classsam_1_1_experiment/#variable-is_published)**  |
| [ExperimentSetup](/doxygen/Classes/classsam_1_1_experiment_setup/) | **[setup](/doxygen/Classes/classsam_1_1_experiment/#variable-setup)**  |
| std::shared_ptr< [DataStrategy](/doxygen/Classes/classsam_1_1_data_strategy/) > | **[data_strategy](/doxygen/Classes/classsam_1_1_experiment/#variable-data_strategy)**  |
| std::shared_ptr< [TestStrategy](/doxygen/Classes/classsam_1_1_test_strategy/) > | **[test_strategy](/doxygen/Classes/classsam_1_1_experiment/#variable-test_strategy)**  |
| std::shared_ptr< [EffectStrategy](/doxygen/Classes/classsam_1_1_effect_strategy/) > | **[effect_strategy](/doxygen/Classes/classsam_1_1_experiment/#variable-effect_strategy)**  |
| std::vector< [Group](/doxygen/Classes/classsam_1_1_group/) > | **[groups_](/doxygen/Classes/classsam_1_1_experiment/#variable-groups_)**  |






## Detailed Description

```cpp
class sam::Experiment;
```

[Experiment]() class declaration. 












**Note**: This could be an abstract class. The abstract will define the body an experiment while subclasses customize it for different type of experiments. This can be used to save space because I can only define relevant variables for each type of experiment 























## Public Functions Documentation

### function Experiment

```cpp
Experiment() =default
```





























### function Experiment

```cpp
Experiment(
    json & experiment_config
)
```





























### function Experiment

```cpp
Experiment(
    ExperimentSetup & e
)
```





























### function Experiment

```cpp
Experiment(
    ExperimentSetup & e,
    std::shared_ptr< DataStrategy > & ds,
    std::shared_ptr< TestStrategy > & ts,
    std::shared_ptr< EffectStrategy > & efs
)
```





























### function operator[]

```cpp
inline Group & operator[](
    std::size_t idx
)
```













**Note**: 

  * I think these are bad ideas, I think they should just return the index that are being asked to, and then some other method, actually returns the group like `get_group`, and `set_group` or even a `[Group](/doxygen/Classes/classsam_1_1_group/) operator()` why not. 
  * This means I need to change the [DataStrategy](/doxygen/Classes/classsam_1_1_data_strategy/) too, and make sure that in each iteration, I start with a fresh [Experiment](/doxygen/Classes/classsam_1_1_experiment/) rather than a half cleanup one. 




**Todo**: : I think these guys are a bit strange, they work and I'm not sure why I have them like this but I think I can do better, for now I put some guard 











These operators are returning the correct group, even if the group list is not sorted


### function operator[]

```cpp
inline const Group & operator[](
    std::size_t idx
) const
```





























### function get_group

```cpp
inline Group & get_group(
    std::size_t idx
)
```





























### function get_group

```cpp
inline const Group & get_group(
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





























### function runTest

```cpp
void runTest()
```

Runs the Test Strategy. 




























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


### function initExperiment

```cpp
void initExperiment()
```



























Helper function for the [Researcher](/doxygen/Classes/classsam_1_1_researcher/) to fully initilize the experiment by generating the data, calculating the statistics and effects, as well as running the test. 


### function generateData

```cpp
void generateData()
```

Use the `data_strategy` to generate the data. 












**Note**: The `data_strategy` takes over the entire experiment and populate the `measurements` based on `setup`'s parameters. 
















### function preProcessData

```cpp
void preProcessData()
```













**Note**: `pre_processing_steps` lists the available steps and their order. 














Run different pre-processing steps before passing the data to the [Researcher](/doxygen/Classes/classsam_1_1_researcher/).


### function calculateStatistics

```cpp
void calculateStatistics()
```



























Calculate the statistics by sending the `experiment` to the `test_strategy`. 


### function calculateEffects

```cpp
void calculateEffects()
```



























Iterates over the list of EffectSizeEstimators, and calculate different different estimates accordingly. 


### function recalculateEverything

```cpp
void recalculateEverything()
```





























### function recalculateEverythingForGroup

```cpp
void recalculateEverythingForGroup(
    size_t inx
)
```





























### function clear

```cpp
void clear()
```

Clear contents of the experiment. 






























## Public Attributes Documentation

### variable exprid

```cpp
int exprid {0};
```





























### variable repid

```cpp
int repid {0};
```





























### variable is_hacked

```cpp
bool is_hacked = false;
```

Indicates if any hacking routine has been applied on the experiment. 




























### variable hacks_history

```cpp
std::vector< int > hacks_history;
```





























### variable is_published

```cpp
bool is_published = false;
```





























### variable setup

```cpp
ExperimentSetup setup;
```





























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





























### variable groups_

```cpp
std::vector< Group > groups_;
```

































-------------------------------

Updated on  2 December 2020 at 14:48:53 CET