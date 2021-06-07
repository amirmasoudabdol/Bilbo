---
title: sam::OptionalStopping::Parameters

---

# sam::OptionalStopping::Parameters

**Module:** **[Parameters of Hacking Strategies](/doxygen/Modules/group___hacking_strategies_parameters/)**



 [More...](#detailed-description)


`#include <HackingStrategy.h>`

## Public Attributes

|                | Name           |
| -------------- | -------------- |
| HackingMethod | **[name](/doxygen/Classes/structsam_1_1_optional_stopping_1_1_parameters/#variable-name)** <br>Placeholder for hacking strategy name.  |
| [Parameter](/doxygen/Classes/classsam_1_1_parameter/)< int > | **[num](/doxygen/Classes/structsam_1_1_optional_stopping_1_1_parameters/#variable-num)** <br>Number of new observations to be added to each group.  |
| HackingTarget | **[target](/doxygen/Classes/structsam_1_1_optional_stopping_1_1_parameters/#variable-target)** <br>Indicates which groups are going to be targets.  |
| [Parameter](/doxygen/Classes/classsam_1_1_parameter/)< double > | **[ratio](/doxygen/Classes/structsam_1_1_optional_stopping_1_1_parameters/#variable-ratio)** <br>If not 0., `ratio` * n_obs will be added to the experiment.  |
| [Parameter](/doxygen/Classes/classsam_1_1_parameter/)< int > | **[n_attempts](/doxygen/Classes/structsam_1_1_optional_stopping_1_1_parameters/#variable-n_attempts)** <br>Number of times that [Researcher]() add `num` observations to each group.  |
| std::vector< std::string > | **[stopping_cond_defs](/doxygen/Classes/structsam_1_1_optional_stopping_1_1_parameters/#variable-stopping_cond_defs)** <br>Stopping condition [PolicyChain]() definitions.  |
| double | **[defensibility](/doxygen/Classes/structsam_1_1_optional_stopping_1_1_parameters/#variable-defensibility)**  |
| double | **[prevalence](/doxygen/Classes/structsam_1_1_optional_stopping_1_1_parameters/#variable-prevalence)**  |
| HackingStage | **[stage](/doxygen/Classes/structsam_1_1_optional_stopping_1_1_parameters/#variable-stage)**  |

## Detailed Description

```cpp
struct sam::OptionalStopping::Parameters;
```


[Parameter](/doxygen/Classes/classsam_1_1_parameter/) of optional stopping method. 

## Public Attributes Documentation

### variable name

```cpp
HackingMethod name = HackingMethod::OptionalStopping;
```

Placeholder for hacking strategy name. 

### variable num

```cpp
Parameter< int > num;
```

Number of new observations to be added to each group. 

### variable target

```cpp
HackingTarget target {HackingTarget::Both};
```

Indicates which groups are going to be targets. 

### variable ratio

```cpp
Parameter< double > ratio;
```

If not 0., `ratio` * n_obs will be added to the experiment. 

### variable n_attempts

```cpp
Parameter< int > n_attempts {1};
```

Number of times that [Researcher]() add `num` observations to each group. 

### variable stopping_cond_defs

```cpp
std::vector< std::string > stopping_cond_defs;
```

Stopping condition [PolicyChain]() definitions. 

### variable defensibility

```cpp
double defensibility {0.1};
```


### variable prevalence

```cpp
double prevalence {0.7};
```


### variable stage

```cpp
HackingStage stage {HackingStage::PostProcessing};
```


-------------------------------

Updated on  7 June 2021 at 12:00:21 CEST