---
title: sam::SignificantSelection
summary: Significant-based Selection Strategy.  

---

# sam::SignificantSelection




Significant-based Selection Strategy.  [More...](#detailed-description)


`#include <SelectionStrategy.h>`


Inherits from SelectionStrategy



## Public Classes

|                | Name           |
| -------------- | -------------- |
| struct | **[Parameters](/doxygen/Classes/structsam_1_1_significant_selection_1_1_parameters/)**  |








## Public Functions

|                | Name           |
| -------------- | -------------- |
|  | **[SignificantSelection](/doxygen/Classes/classsam_1_1_significant_selection/#function-significantselection)**(const [Parameters](/doxygen/Classes/structsam_1_1_significant_selection_1_1_parameters/) & p)  |
| virtual bool | **[review](/doxygen/Classes/classsam_1_1_significant_selection/#function-review)**(const [Submission](/doxygen/Classes/classsam_1_1_submission/) & s) override  |


## Public Attributes

|                | Name           |
| -------------- | -------------- |
| [Parameters](/doxygen/Classes/structsam_1_1_significant_selection_1_1_parameters/) | **[params](/doxygen/Classes/classsam_1_1_significant_selection/#variable-params)**  |






## Detailed Description

```cpp
class sam::SignificantSelection;
```

Significant-based Selection Strategy. 


























Significant-based selection strategy accepts a publication if the given _p_-value is significant. Certain degree of _publication bias_, can be specified. In this case, a [Submission](/doxygen/Classes/classsam_1_1_submission/) has a chance of being published even if the statistics is not significant. Moreover, the [SignificantSelection](/doxygen/Classes/classsam_1_1_significant_selection/) can be tailored toward either positive or negative effect. In this case, the [Journal](/doxygen/Classes/classsam_1_1_journal/) will only accept Submissions with larger or smaller effects. 









## Public Functions Documentation

### function SignificantSelection

```cpp
inline SignificantSelection(
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

  * **s** A reference to the [Submission](/doxygen/Classes/classsam_1_1_submission/)







**Return**: a boolean indicating whether the [Submission](/doxygen/Classes/classsam_1_1_submission/) is accepted. 



















Check if `p-value` of the [Submission](/doxygen/Classes/classsam_1_1_submission/) is less than the specified $\alpha$. If true, it will accept the submission, if not, a random number decide wheather the submission is going to be accepted. The drawn random number, $r$ will be compared to `pub_bias` of the journal.




## Public Attributes Documentation

### variable params

```cpp
Parameters params;
```

































-------------------------------

Updated on 23 November 2020 at 14:03:44 CET