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
| [Parameter](/doxygen/Classes/classsam_1_1_parameter/)< float > | **[ratio](/doxygen/Classes/structsam_1_1_optional_stopping_1_1_parameters/#variable-ratio)** <br>If not 0., `ratio` * n_obs will be added to the experiment.  |
| [Parameter](/doxygen/Classes/classsam_1_1_parameter/)< int > | **[n_attempts](/doxygen/Classes/structsam_1_1_optional_stopping_1_1_parameters/#variable-n_attempts)** <br>Number of times that [Researcher]() add `num` observations to each group.  |
| std::vector< std::string > | **[stopping_cond_defs](/doxygen/Classes/structsam_1_1_optional_stopping_1_1_parameters/#variable-stopping_cond_defs)** <br>Stopping condition [PolicyChain]() definitions.  |
| std::optional< float > | **[defensibility](/doxygen/Classes/structsam_1_1_optional_stopping_1_1_parameters/#variable-defensibility)** <br>The defensibility factor of the strategy.  |
| std::optional< float > | **[prevalence](/doxygen/Classes/structsam_1_1_optional_stopping_1_1_parameters/#variable-prevalence)** <br>The prevalence factor of the strategy.  |
| HackingStage | **[stage](/doxygen/Classes/structsam_1_1_optional_stopping_1_1_parameters/#variable-stage)** <br>The default execution stage of the strategy.  |

## Detailed Description

```cpp
struct sam::OptionalStopping::Parameters;
```


[Parameter](/doxygen/Classes/classsam_1_1_parameter/) of optional stopping strategy 

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

**See**: [sam::Parameter](/doxygen/Classes/classsam_1_1_parameter/)

### variable target

```cpp
HackingTarget target {HackingTarget::Both};
```

Indicates which groups are going to be targets. 

### variable ratio

```cpp
Parameter< float > ratio;
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

The default execution stage of the strategy. 

-------------------------------

Updated on 29 June 2021 at 16:13:47 CEST