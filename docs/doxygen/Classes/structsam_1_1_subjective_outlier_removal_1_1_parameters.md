---
title: sam::SubjectiveOutlierRemoval::Parameters
summary: SubjectiveOutlierRemoval's parameters.  

---

# sam::SubjectiveOutlierRemoval::Parameters


**Module:** **[Parameters of Hacking Strategies](/doxygen/Modules/group___hacking_strategies_parameters/)**

[SubjectiveOutlierRemoval](/doxygen/Classes/classsam_1_1_subjective_outlier_removal/)'s parameters.  [More...](#detailed-description)


`#include <HackingStrategy.h>`















## Public Attributes

|                | Name           |
| -------------- | -------------- |
| HackingMethod | **[name](/doxygen/Classes/structsam_1_1_subjective_outlier_removal_1_1_parameters/#variable-name)** <br>A placeholder for the name.  |
| HackingTarget | **[target](/doxygen/Classes/structsam_1_1_subjective_outlier_removal_1_1_parameters/#variable-target)** <br>TO BE IMPLEMENTED.  |
| std::vector< int > | **[range](/doxygen/Classes/structsam_1_1_subjective_outlier_removal_1_1_parameters/#variable-range)** <br>A vector of `{min, max}`, defining the range of `K`.  |
| double | **[step_size](/doxygen/Classes/structsam_1_1_subjective_outlier_removal_1_1_parameters/#variable-step_size)** <br>Indicates the step size of walking through K's.  |
| int | **[min_observations](/doxygen/Classes/structsam_1_1_subjective_outlier_removal_1_1_parameters/#variable-min_observations)** <br>Indicates minimum number of observatons.  |
| std::vector< std::string > | **[stopping_cond_defs](/doxygen/Classes/structsam_1_1_subjective_outlier_removal_1_1_parameters/#variable-stopping_cond_defs)** <br>Stopping condition [PolicyChain](/doxygen/Classes/structsam_1_1_policy_chain/) definitions.  |
| double | **[prevalence](/doxygen/Classes/structsam_1_1_subjective_outlier_removal_1_1_parameters/#variable-prevalence)**  |
| double | **[defensibility](/doxygen/Classes/structsam_1_1_subjective_outlier_removal_1_1_parameters/#variable-defensibility)**  |
| HackingStage | **[stage](/doxygen/Classes/structsam_1_1_subjective_outlier_removal_1_1_parameters/#variable-stage)**  |






## Detailed Description

```cpp
struct sam::SubjectiveOutlierRemoval::Parameters;
```

[SubjectiveOutlierRemoval](/doxygen/Classes/classsam_1_1_subjective_outlier_removal/)'s parameters. 


























These are parameters specific to this hacking strategy. You can set them either progmatically when you are constructing a new [SubjectiveOutlierRemoval](/doxygen/Classes/classsam_1_1_subjective_outlier_removal/), e.g., `[SubjectiveOutlierRemoval](/doxygen/Classes/classsam_1_1_subjective_outlier_removal/) sor{<name>, {min, max}, ssize};`.

Or, when you are using `SAMrun` to run your simulation. In this case, your JSON variable must comply with the name and type of paramters here. For example, the following JSON defines the default subjective outliers removal.



```cpp
{
   "name": "SubjectiveOutlierRemoval",
   "range": [2, 4],
   "step_size": 0.1,
   "min_observations": 5
}
```

_Filename: .json_











## Public Attributes Documentation

### variable name

```cpp
HackingMethod name = HackingMethod::SubjectiveOutlierRemoval;
```

A placeholder for the name. 




























### variable target

```cpp
HackingTarget target {HackingTarget::Both};
```

TO BE IMPLEMENTED. 




























### variable range

```cpp
std::vector< int > range {2, 4};
```

A vector of `{min, max}`, defining the range of `K`. 




























### variable step_size

```cpp
double step_size {0.1};
```

Indicates the step size of walking through K's. 




























### variable min_observations

```cpp
int min_observations {5};
```

Indicates minimum number of observatons. 




























### variable stopping_cond_defs

```cpp
std::vector< std::string > stopping_cond_defs {{"sig"}};
```

Stopping condition [PolicyChain](/doxygen/Classes/structsam_1_1_policy_chain/) definitions. 




























### variable prevalence

```cpp
double prevalence {0.1};
```





























### variable defensibility

```cpp
double defensibility {0.1};
```





























### variable stage

```cpp
HackingStage stage {HackingStage::PostProcessing};
```

































-------------------------------

Updated on  7 December 2020 at 13:20:10 CET