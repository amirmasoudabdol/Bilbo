---
title: sam::ResearcherBuilder

---

# sam::ResearcherBuilder

**Module:** **[Abstract Factory Builders](/doxygen/Modules/group___abstract_builders/)**



 [More...](#detailed-description)


`#include <Researcher.h>`

## Public Functions

|                | Name           |
| -------------- | -------------- |
| | **[ResearcherBuilder](/doxygen/Classes/classsam_1_1_researcher_builder/#function-researcherbuilder)**() =default |
| | **[ResearcherBuilder](/doxygen/Classes/classsam_1_1_researcher_builder/#function-researcherbuilder)**(std::string name) |
| [ResearcherBuilder](/doxygen/Classes/classsam_1_1_researcher_builder/) & | **[fromConfigFile](/doxygen/Classes/classsam_1_1_researcher_builder/#function-fromconfigfile)**(json & config)<br>Building the [Researcher](/doxygen/Classes/classsam_1_1_researcher/) using the JSON configuration file.  |
| [ResearcherBuilder](/doxygen/Classes/classsam_1_1_researcher_builder/) & | **[createResearchStrategy](/doxygen/Classes/classsam_1_1_researcher_builder/#function-createresearchstrategy)**(json & ds)<br>CREATING A NEW OBJECT ///.  |
| [Researcher](/doxygen/Classes/classsam_1_1_researcher/) | **[build](/doxygen/Classes/classsam_1_1_researcher_builder/#function-build)**() |

## Detailed Description

```cpp
class sam::ResearcherBuilder;
```


**Note**: At this moment, [ResearcherBuilder](/doxygen/Classes/classsam_1_1_researcher_builder/) is a very limited and can only initialize the [Researcher](/doxygen/Classes/classsam_1_1_researcher/) from a config file. 

[ResearcherBuilder](/doxygen/Classes/classsam_1_1_researcher_builder/) class for [Researcher](/doxygen/Classes/classsam_1_1_researcher/). This takes care of everything and return a fully initialized [Researcher](/doxygen/Classes/classsam_1_1_researcher/) after calling `.[build()](/doxygen/Classes/classsam_1_1_researcher_builder/#function-build)` method.

## Public Functions Documentation

### function ResearcherBuilder

```cpp
ResearcherBuilder() =default
```


### function ResearcherBuilder

```cpp
inline explicit ResearcherBuilder(
    std::string name
)
```


### function fromConfigFile

```cpp
inline ResearcherBuilder & fromConfigFile(
    json & config
)
```

Building the [Researcher](/doxygen/Classes/classsam_1_1_researcher/) using the JSON configuration file. 

**Parameters**: 

  * **config** A JSON object 


**Return**: Return an instance of itself 

This builds a researcher entirely based on the given config file. This is not the best implementation yet but I think it's more readable and reasonable for some use-cases.


### function createResearchStrategy

```cpp
inline ResearcherBuilder & createResearchStrategy(
    json & ds
)
```

CREATING A NEW OBJECT ///. 

Create a new [ResearchStrategy](/doxygen/Classes/classsam_1_1_research_strategy/) for the researcher based on the given configuration. 


### function build

```cpp
inline Researcher build()
```


**Return**: A new [Researcher](/doxygen/Classes/classsam_1_1_researcher/)

**Note**: Be aware that this needs to be called after you set all aspects of the [Researcher](/doxygen/Classes/classsam_1_1_researcher/)

Build and return a new [Researcher](/doxygen/Classes/classsam_1_1_researcher/).


-------------------------------

Updated on 29 June 2021 at 16:13:48 CEST