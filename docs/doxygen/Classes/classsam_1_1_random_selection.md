---
title: sam::RandomSelection
summary: Random Selection Strategy.  

---

# sam::RandomSelection




Random Selection Strategy.  [More...](#detailed-description)


`#include <SelectionStrategy.h>`


Inherits from SelectionStrategy



## Public Classes

|                | Name           |
| -------------- | -------------- |
| struct | **[Parameters](/doxygen/Classes/structsam_1_1_random_selection_1_1_parameters/)**  |








## Public Functions

|                | Name           |
| -------------- | -------------- |
|  | **[RandomSelection](/doxygen/Classes/classsam_1_1_random_selection/#function-randomselection)**(const [Parameters](/doxygen/Classes/structsam_1_1_random_selection_1_1_parameters/) & p)  |
| virtual bool | **[review](/doxygen/Classes/classsam_1_1_random_selection/#function-review)**(const [Submission](/doxygen/Classes/classsam_1_1_submission/) & s) override  |


## Public Attributes

|                | Name           |
| -------------- | -------------- |
| [Parameters](/doxygen/Classes/structsam_1_1_random_selection_1_1_parameters/) | **[params](/doxygen/Classes/classsam_1_1_random_selection/#variable-params)**  |






## Detailed Description

```cpp
class sam::RandomSelection;
```

Random Selection Strategy. 












**Note**: This is technically the [SignificantSelection](/doxygen/Classes/classsam_1_1_significant_selection/) with pub_bias set to 0. 














In this method, [Journal](/doxygen/Classes/classsam_1_1_journal/) does not check any criteria for accepting or rejecting a submission. Each submission has 50% chance of being accepted.









## Public Functions Documentation

### function RandomSelection

```cpp
inline RandomSelection(
    const Parameters & p
)
```





























### function review

```cpp
virtual bool review(
    const Submission & s
) override
```


**Parameters**: 

  * **s** corresponding submission 







**Return**: a boolean indicating whether the [Submission](/doxygen/Classes/classsam_1_1_submission/) is accpeted. 



















Draw a random number between $ r \in [0, 1] $, reject the submission if $ r < 0.5 $.




## Public Attributes Documentation

### variable params

```cpp
Parameters params;
```

































-------------------------------

Updated on 23 November 2020 at 14:03:43 CET