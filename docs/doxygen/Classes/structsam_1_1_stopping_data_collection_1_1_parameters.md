---
title: sam::StoppingDataCollection::Parameters

---

# sam::StoppingDataCollection::Parameters

**Module:** **[Parameters of Hacking Strategies](/doxygen/Modules/group___hacking_strategies_parameters/)**



 [More...](#detailed-description)


`#include <HackingStrategy.h>`

## Public Attributes

|                | Name           |
| -------------- | -------------- |
| HackingMethod | **[name](/doxygen/Classes/structsam_1_1_stopping_data_collection_1_1_parameters/#variable-name)**  |
| HackingTarget | **[target](/doxygen/Classes/structsam_1_1_stopping_data_collection_1_1_parameters/#variable-target)**  |
| int | **[batch_size](/doxygen/Classes/structsam_1_1_stopping_data_collection_1_1_parameters/#variable-batch_size)** <br>Number of observations to be perturbed.  |
| std::vector< std::string > | **[stopping_cond_defs](/doxygen/Classes/structsam_1_1_stopping_data_collection_1_1_parameters/#variable-stopping_cond_defs)** <br>Stopping condition [PolicyChain]() definitions.  |
| std::optional< float > | **[defensibility](/doxygen/Classes/structsam_1_1_stopping_data_collection_1_1_parameters/#variable-defensibility)** <br>The defensibility factor of the strategy.  |
| std::optional< float > | **[prevalence](/doxygen/Classes/structsam_1_1_stopping_data_collection_1_1_parameters/#variable-prevalence)** <br>The prevalence factor of the strategy.  |
| HackingStage | **[stage](/doxygen/Classes/structsam_1_1_stopping_data_collection_1_1_parameters/#variable-stage)** <br>The default execution stage of the strategy.  |

## Detailed Description

```cpp
struct sam::StoppingDataCollection::Parameters;
```


Stopping Data Collection [Parameters](/doxygen/Classes/structsam_1_1_stopping_data_collection_1_1_parameters/)

Example usage: 

```cpp
{
  "name": "StoppingDataCollection",
  "batch_size": 5,
  "stopping_condition": ["sig"]
}
```

_Filename: .json_

## Public Attributes Documentation

### variable name

```cpp
HackingMethod name = HackingMethod::StoppingDataCollection;
```


### variable target

```cpp
HackingTarget target {HackingTarget::Both};
```


Indicates which outcome variables are going to be targeted,

* control
* treatment
* both Todoto be implemented 


### variable batch_size

```cpp
int batch_size;
```

Number of observations to be perturbed. 

**Todo**: To be implemented 

Indicates a set of rule that is going to be used to select the target group 


### variable stopping_cond_defs

```cpp
std::vector< std::string > stopping_cond_defs {"sig"};
```

Stopping condition [PolicyChain]() definitions. 

### variable defensibility

```cpp
std::optional< float > defensibility;
```

The defensibility factor of the strategy. 

### variable prevalence

```cpp
std::optional< float > prevalence;
```

The prevalence factor of the strategy. 

### variable stage

```cpp
HackingStage stage {HackingStage::DataCollection};
```

The default execution stage of the strategy. 

-------------------------------

Updated on 29 June 2021 at 16:13:47 CEST