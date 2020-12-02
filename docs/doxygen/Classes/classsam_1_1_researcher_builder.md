---
title: sam::ResearcherBuilder


---

# sam::ResearcherBuilder




 [More...](#detailed-description)


`#include <Researcher.h>`













## Public Functions

|                | Name           |
| -------------- | -------------- |
|  | **[ResearcherBuilder](/doxygen/Classes/classsam_1_1_researcher_builder/#function-researcherbuilder)**()  |
|  | **[ResearcherBuilder](/doxygen/Classes/classsam_1_1_researcher_builder/#function-researcherbuilder)**(std::string name)  |
| [ResearcherBuilder](/doxygen/Classes/classsam_1_1_researcher_builder/) & | **[fromConfigFile](/doxygen/Classes/classsam_1_1_researcher_builder/#function-fromconfigfile)**(json & config)  |
| [ResearcherBuilder](/doxygen/Classes/classsam_1_1_researcher_builder/) & | **[createDecisionStrategy](/doxygen/Classes/classsam_1_1_researcher_builder/#function-createdecisionstrategy)**(json & ds) <br>CREATEING NEW OBJECT ///.  |
| [ResearcherBuilder](/doxygen/Classes/classsam_1_1_researcher_builder/) & | **[createNewHackingStrategyGroup](/doxygen/Classes/classsam_1_1_researcher_builder/#function-createnewhackingstrategygroup)**(json & hacking_strategy_group_config) <br>Create a new [Journal](/doxygen/Classes/classsam_1_1_journal/) for the researcher based on the given configuration.  |
| [ResearcherBuilder](/doxygen/Classes/classsam_1_1_researcher_builder/) & | **[createNewHackingStrategy](/doxygen/Classes/classsam_1_1_researcher_builder/#function-createnewhackingstrategy)**(json & hacking_strategy_config)  |
| [ResearcherBuilder](/doxygen/Classes/classsam_1_1_researcher_builder/) & | **[setDataStrategy](/doxygen/Classes/classsam_1_1_researcher_builder/#function-setdatastrategy)**(std::shared_ptr< [DataStrategy](/doxygen/Classes/classsam_1_1_data_strategy/) > ds) <br>SETTING NEW OBJECT ///.  |
| [ResearcherBuilder](/doxygen/Classes/classsam_1_1_researcher_builder/) & | **[setTestStrategy](/doxygen/Classes/classsam_1_1_researcher_builder/#function-setteststrategy)**(std::shared_ptr< [TestStrategy](/doxygen/Classes/classsam_1_1_test_strategy/) > & ts)  |
| [ResearcherBuilder](/doxygen/Classes/classsam_1_1_researcher_builder/) & | **[setJournalSelectionStrategy](/doxygen/Classes/classsam_1_1_researcher_builder/#function-setjournalselectionstrategy)**(std::unique_ptr< SelectionStrategy > ss)  |
| [ResearcherBuilder](/doxygen/Classes/classsam_1_1_researcher_builder/) & | **[setDecisionStrategy](/doxygen/Classes/classsam_1_1_researcher_builder/#function-setdecisionstrategy)**(std::unique_ptr< [DecisionStrategy](/doxygen/Classes/classsam_1_1_decision_strategy/) > ds)  |
| [ResearcherBuilder](/doxygen/Classes/classsam_1_1_researcher_builder/) & | **[setHackingStrategy](/doxygen/Classes/classsam_1_1_researcher_builder/#function-sethackingstrategy)**([HackingStrategy](/doxygen/Classes/classsam_1_1_hacking_strategy/) * hs)  |
| [ResearcherBuilder](/doxygen/Classes/classsam_1_1_researcher_builder/) & | **[setHackingStrategy](/doxygen/Classes/classsam_1_1_researcher_builder/#function-sethackingstrategy)**(std::vector< std::vector< [HackingStrategy](/doxygen/Classes/classsam_1_1_hacking_strategy/) * >> )  |
| [ResearcherBuilder](/doxygen/Classes/classsam_1_1_researcher_builder/) & | **[addHackingStrategyGroup](/doxygen/Classes/classsam_1_1_researcher_builder/#function-addhackingstrategygroup)**(std::vector< [HackingStrategy](/doxygen/Classes/classsam_1_1_hacking_strategy/) * > hsg)  |
| [ResearcherBuilder](/doxygen/Classes/classsam_1_1_researcher_builder/) & | **[addNewHackingStrategy](/doxygen/Classes/classsam_1_1_researcher_builder/#function-addnewhackingstrategy)**([HackingStrategy](/doxygen/Classes/classsam_1_1_hacking_strategy/) * new_hs)  |
| [ResearcherBuilder](/doxygen/Classes/classsam_1_1_researcher_builder/) & | **[chooseHackingStrategies](/doxygen/Classes/classsam_1_1_researcher_builder/#function-choosehackingstrategies)**(std::vector< HackingMethod > hacking_strategies_pool, int n_group, int m_strategies)  |
| [ResearcherBuilder](/doxygen/Classes/classsam_1_1_researcher_builder/) & | **[pickRandomHackingStrategies](/doxygen/Classes/classsam_1_1_researcher_builder/#function-pickrandomhackingstrategies)**(int n_group, int m_method)  |
| [Researcher](/doxygen/Classes/classsam_1_1_researcher/) | **[build](/doxygen/Classes/classsam_1_1_researcher_builder/#function-build)**()  |








## Detailed Description

```cpp
class sam::ResearcherBuilder;
```



























[ResearcherBuilder](/doxygen/Classes/classsam_1_1_researcher_builder/) class for [Researcher](/doxygen/Classes/classsam_1_1_researcher/). This takes care of eveyrthing and return a fully initialized [Researcher](/doxygen/Classes/classsam_1_1_researcher/) after calling `.[build()](/doxygen/Classes/classsam_1_1_researcher_builder/#function-build)` method. 









## Public Functions Documentation

### function ResearcherBuilder

```cpp
inline ResearcherBuilder()
```





























### function ResearcherBuilder

```cpp
inline ResearcherBuilder(
    std::string name
)
```





























### function fromConfigFile

```cpp
inline ResearcherBuilder & fromConfigFile(
    json & config
)
```


**Parameters**: 

  * **config** A JSON object 







**Return**: Return an instance of itself








**Todo**: This needs to be splitted into different pieces 











Build a researcher entirely based on the given config file. This is not the best implementation still but I think it's more readable and reasonable for some usecases.

TodoI can technically replace all these direct calls with calls to their counterpart in the Builder! 

Copying the original list for later shuffling!

Selecting between hacking

Reordering hacking strategies based on selection priority

Bug! This will explode because it has to deconstruct the `lua` instance and that's not really possible since it is a public member of the abstract class, meaning that other hacking strategies that are already in the list wants to use it! 

The actual reason is related to the stopping_condition. For instance, if a hacking strategy hasn't initialized its stopping_condition, then SAM doesn't know how to deconstruct it 

I think I can move the stopping_condition to the abstract class, or just make sure that all classes at least have some empty [PolicyChain](/doxygen/Classes/structsam_1_1_policy_chain/). I think the latter is easier as I can just construct an empty one! 

even if I leave [OutliersRemoval](/doxygen/Classes/classsam_1_1_outliers_removal/) stopping_condition empty, things will be fine! What's special about [FabricatingData](/doxygen/Classes/classsam_1_1_fabricating_data/) method 

Even if I don't initiate [OutliersRemoval](/doxygen/Classes/classsam_1_1_outliers_removal/) stopping condition this will be fine! 

Not really sure how this resolved itself, but I think Xcode was struggling with the memory! At some point, it crashed, and my problem was solved!


Selecting only n_hacks of those

Setting the execution order

Reorder hacking strategies based on the prefered execution order

Sorting the selected hacking strategies based on their stage The stable_sort has been used because I'd like to keep the given order in previous stages

Indicate what percentage of [Researcher](/doxygen/Classes/classsam_1_1_researcher/)'s work is going to be submitted

### function createDecisionStrategy

```cpp
inline ResearcherBuilder & createDecisionStrategy(
    json & ds
)
```

CREATEING NEW OBJECT ///. 


























Create a new [DecisionStrategy](/doxygen/Classes/classsam_1_1_decision_strategy/) for the researcher based on the given configuration. 


### function createNewHackingStrategyGroup

```cpp
inline ResearcherBuilder & createNewHackingStrategyGroup(
    json & hacking_strategy_group_config
)
```

Create a new [Journal](/doxygen/Classes/classsam_1_1_journal/) for the researcher based on the given configuration. 












**Note**: 

  * The configuration needs to include information about the SelectionStrategy as well.
  * : This assumes that the experiment setup is correctly initiated. 
















Create a new [Experiment](/doxygen/Classes/classsam_1_1_experiment/) based on the given [ExperimentSetup](/doxygen/Classes/classsam_1_1_experiment_setup/).


### function createNewHackingStrategy

```cpp
inline ResearcherBuilder & createNewHackingStrategy(
    json & hacking_strategy_config
)
```





























### function setDataStrategy

```cpp
inline ResearcherBuilder & setDataStrategy(
    std::shared_ptr< DataStrategy > ds
)
```

SETTING NEW OBJECT ///. 




























### function setTestStrategy

```cpp
inline ResearcherBuilder & setTestStrategy(
    std::shared_ptr< TestStrategy > & ts
)
```





























### function setJournalSelectionStrategy

```cpp
inline ResearcherBuilder & setJournalSelectionStrategy(
    std::unique_ptr< SelectionStrategy > ss
)
```





























### function setDecisionStrategy

```cpp
inline ResearcherBuilder & setDecisionStrategy(
    std::unique_ptr< DecisionStrategy > ds
)
```





























### function setHackingStrategy

```cpp
ResearcherBuilder & setHackingStrategy(
    HackingStrategy * hs
)
```





























### function setHackingStrategy

```cpp
ResearcherBuilder & setHackingStrategy(
    std::vector< std::vector< HackingStrategy * >> 
)
```





























### function addHackingStrategyGroup

```cpp
inline ResearcherBuilder & addHackingStrategyGroup(
    std::vector< HackingStrategy * > hsg
)
```





























### function addNewHackingStrategy

```cpp
inline ResearcherBuilder & addNewHackingStrategy(
    HackingStrategy * new_hs
)
```





























### function chooseHackingStrategies

```cpp
inline ResearcherBuilder & chooseHackingStrategies(
    std::vector< HackingMethod > hacking_strategies_pool,
    int n_group,
    int m_strategies
)
```


**Parameters**: 

  * **hacking_strategies_pool** A set of hacking strategy methods use to prepare researcher's hacking startegies 
  * **n_group** The number of hacking strategies groups 
  * **m_strategies** The number of hacking startegies in each group 







**Return**: Return an instance of itself where hacking_strategies has been initialized accordingly. 



















Prepare a set of hacking strategies groups by populating each group from the given `hacking_strategies_pool`

auto h_method = enum_cast<HackingMethod>(Random::get<int>(0, hacking_strategies_pool.size() - 1));

### function pickRandomHackingStrategies

```cpp
inline ResearcherBuilder & pickRandomHackingStrategies(
    int n_group,
    int m_method
)
```


**Parameters**: 

  * **n_group** Number of groups of hacking strategies 
  * **m_strategies** Number of hacking strategies in each group 







**Return**: Return an instance of itself where hacking_strategies has been initialized accordingly. 



















Constructs `n_group`'s of hacking strategies, each consisting of maximum `m_strategies`'s or steps. Each startegy is being selected randomly between all available strategies.


### function build

```cpp
inline Researcher build()
```








**Return**: A new [Researcher](/doxygen/Classes/classsam_1_1_researcher/)





**Note**: Be aware that this needs to be called after you set all aspects of the [Researcher](/doxygen/Classes/classsam_1_1_researcher/)














Build and return a new [Researcher](/doxygen/Classes/classsam_1_1_researcher/).








-------------------------------

Updated on  2 December 2020 at 14:48:54 CET