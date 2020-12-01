---
title: sam::FreeSelection
summary: FreeSelection doesn't pose any restriction on the submission and all submissions will be accepted.  

---

# sam::FreeSelection




[FreeSelection]() doesn't pose any restriction on the submission and all submissions will be accepted. 

`#include <SelectionStrategy.h>`


Inherits from SelectionStrategy



## Public Classes

|                | Name           |
| -------------- | -------------- |
| struct | **[Parameters](/doxygen/Classes/structsam_1_1_free_selection_1_1_parameters/)**  |








## Public Functions

|                | Name           |
| -------------- | -------------- |
|  | **[FreeSelection](/doxygen/Classes/classsam_1_1_free_selection/#function-freeselection)**()  |
| virtual bool | **[review](/doxygen/Classes/classsam_1_1_free_selection/#function-review)**(const [Submission](/doxygen/Classes/classsam_1_1_submission/) & s) override <br>Accepting anything!  |


## Public Attributes

|                | Name           |
| -------------- | -------------- |
| [Parameters](/doxygen/Classes/structsam_1_1_free_selection_1_1_parameters/) | **[params](/doxygen/Classes/classsam_1_1_free_selection/#variable-params)**  |














## Public Functions Documentation

### function FreeSelection

```cpp
inline FreeSelection()
```





























### function review

```cpp
inline virtual bool review(
    const Submission & s
) override
```

Accepting anything! 






























## Public Attributes Documentation

### variable params

```cpp
Parameters params;
```

































-------------------------------

Updated on 23 November 2020 at 14:03:43 CET