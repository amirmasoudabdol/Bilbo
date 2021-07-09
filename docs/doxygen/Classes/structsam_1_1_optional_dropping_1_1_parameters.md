---
title: sam::OptionalDropping::Parameters

---

# sam::OptionalDropping::Parameters

**Module:** **[Parameters of Hacking Strategies](/doxygen/Modules/group___hacking_strategies_parameters/)**



 [More...](#detailed-description)


`#include <HackingStrategy.h>`

## Public Attributes

|                | Name           |
| -------------- | -------------- |
| HackingMethod | **[name](/doxygen/Classes/structsam_1_1_optional_dropping_1_1_parameters/#variable-name)**  |
| HackingTarget | **[target](/doxygen/Classes/structsam_1_1_optional_dropping_1_1_parameters/#variable-target)**  |
| std::vector< std::vector< int > > | **[pooled](/doxygen/Classes/structsam_1_1_optional_dropping_1_1_parameters/#variable-pooled)** <br>List of condition groups to be used for the dropping procedure.  |
| std::vector< std::vector< int > > | **[split_by](/doxygen/Classes/structsam_1_1_optional_dropping_1_1_parameters/#variable-split_by)**  |
| std::vector< std::string > | **[stopping_cond_defs](/doxygen/Classes/structsam_1_1_optional_dropping_1_1_parameters/#variable-stopping_cond_defs)** <br>Stopping condition [PolicyChain]() definitions.  |
| std::optional< float > | **[defensibility](/doxygen/Classes/structsam_1_1_optional_dropping_1_1_parameters/#variable-defensibility)** <br>The defensibility factor of the strategy.  |
| std::optional< float > | **[prevalence](/doxygen/Classes/structsam_1_1_optional_dropping_1_1_parameters/#variable-prevalence)** <br>The prevalence factor of the strategy.  |
| HackingStage | **[stage](/doxygen/Classes/structsam_1_1_optional_dropping_1_1_parameters/#variable-stage)**  |

## Detailed Description

```cpp
struct sam::OptionalDropping::Parameters;
```


Optional Dropping Collection [Parameters](/doxygen/Classes/structsam_1_1_optional_dropping_1_1_parameters/)

Indicates the indicies of groups that you like to be used for splitting in `pooled` variable, e.g. [[1]], the first treatment group; and then use the `split_by` parameters to define the [index, value] of the covariants.

Example usage: 

```cpp
{
  "name": "OptionalDropping",
  "pooled": [[1]],
  "split_by": [[0, 1]],
  "stopping_condition": ["sig"]
}
```

_Filename: .json_

## Public Attributes Documentation

### variable name

```cpp
HackingMethod name = HackingMethod::OptionalDropping;
```


### variable target

```cpp
HackingTarget target {HackingTarget::Both};
```


Indicates which outcome variables are going to be targeted,

* control
* treatment
* both Todoto be implemented 


### variable pooled

```cpp
std::vector< std::vector< int > > pooled;
```

List of condition groups to be used for the dropping procedure. 

### variable split_by

```cpp
std::vector< std::vector< int > > split_by;
```


Lists of covariants index, and their value pairs, e.g., [[0, 0], [0, 1]], that is going to be used by the algorithm to split the dependent variables. In this case, the data will be splitted by the first covariants (level == 0), and then by the second covariants (level == 1). 


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
HackingStage stage {HackingStage::PostProcessing};
```


-------------------------------

Updated on 29 June 2021 at 16:13:47 CEST