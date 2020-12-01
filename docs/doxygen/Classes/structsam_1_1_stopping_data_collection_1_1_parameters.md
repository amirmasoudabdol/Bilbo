---
title: sam::StoppingDataCollection::Parameters


---

# sam::StoppingDataCollection::Parameters


**Module:** **[Hacking Strategies Parameters](/doxygen/Modules/group___hacking_strategies_parameters/)**

 [More...](#detailed-description)


`#include <HackingStrategy.h>`















## Public Attributes

|                | Name           |
| -------------- | -------------- |
| HackingMethod | **[name](/doxygen/Classes/structsam_1_1_stopping_data_collection_1_1_parameters/#variable-name)**  |
| HackingTarget | **[target](/doxygen/Classes/structsam_1_1_stopping_data_collection_1_1_parameters/#variable-target)**  |
| int | **[batch_size](/doxygen/Classes/structsam_1_1_stopping_data_collection_1_1_parameters/#variable-batch_size)** <br>Number of observations to be purturbed.  |
| std::vector< std::string > | **[stopping_cond_defs](/doxygen/Classes/structsam_1_1_stopping_data_collection_1_1_parameters/#variable-stopping_cond_defs)** <br>Stopping condition [PolicyChain](/doxygen/Classes/structsam_1_1_policy_chain/) definitions.  |
| double | **[defensibility](/doxygen/Classes/structsam_1_1_stopping_data_collection_1_1_parameters/#variable-defensibility)**  |
| double | **[prevalence](/doxygen/Classes/structsam_1_1_stopping_data_collection_1_1_parameters/#variable-prevalence)**  |
| HackingStage | **[stage](/doxygen/Classes/structsam_1_1_stopping_data_collection_1_1_parameters/#variable-stage)**  |






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
* both 


### variable batch_size

```cpp
int batch_size {5};
```

Number of observations to be purturbed. 















**Todo**: To be implemented 











Indicates a set of rule that is going to be used to select the target group 


### variable stopping_cond_defs

```cpp
std::vector< std::string > stopping_cond_defs {"sig"};
```

Stopping condition [PolicyChain](/doxygen/Classes/structsam_1_1_policy_chain/) definitions. 




























### variable defensibility

```cpp
double defensibility {0.05};
```





























### variable prevalence

```cpp
double prevalence {0.1};
```





























### variable stage

```cpp
HackingStage stage {HackingStage::DataCollection};
```

































-------------------------------

Updated on 23 November 2020 at 14:03:44 CET