---
title: sam::TrimAndFill
summary: Trim and Fill Publication Bias Test. 

---

# sam::TrimAndFill

**Module:** **[Meta Analysis Methods](/doxygen/Modules/group___meta_analysis/)**



Trim and Fill Publication Bias Test. 
`#include <MetaAnalysis.h>`

Inherits from [sam::MetaAnalysis](/doxygen/Classes/classsam_1_1_meta_analysis/)

## Public Classes

|                | Name           |
| -------------- | -------------- |
| struct | **[Parameters](/doxygen/Classes/structsam_1_1_trim_and_fill_1_1_parameters/)** <br>[Parameters]() of the [TrimAndFill](/doxygen/Classes/classsam_1_1_trim_and_fill/).  |
| struct | **[ResultType](/doxygen/Classes/structsam_1_1_trim_and_fill_1_1_result_type/)**  |

## Public Functions

|                | Name           |
| -------------- | -------------- |
| | **[TrimAndFill](/doxygen/Classes/classsam_1_1_trim_and_fill/#function-trimandfill)**() =default |
| | **[TrimAndFill](/doxygen/Classes/classsam_1_1_trim_and_fill/#function-trimandfill)**(const [Parameters](/doxygen/Classes/structsam_1_1_trim_and_fill_1_1_parameters/) & p) |
| virtual void | **[estimate](/doxygen/Classes/classsam_1_1_trim_and_fill/#function-estimate)**([Journal](/doxygen/Classes/classsam_1_1_journal/) * journal) |
| [ResultType](/doxygen/Classes/structsam_1_1_trim_and_fill_1_1_result_type/) | **[TF](/doxygen/Classes/classsam_1_1_trim_and_fill/#function-tf)**(arma::Row< double > yi, arma::Row< double > vi, arma::Row< double > ni, const [Parameters](/doxygen/Classes/structsam_1_1_trim_and_fill_1_1_parameters/) & params) |

## Public Attributes

|                | Name           |
| -------------- | -------------- |
| [Parameters](/doxygen/Classes/structsam_1_1_trim_and_fill_1_1_parameters/) | **[params](/doxygen/Classes/classsam_1_1_trim_and_fill/#variable-params)**  |

## Additional inherited members

**Public Functions inherited from [sam::MetaAnalysis](/doxygen/Classes/classsam_1_1_meta_analysis/)**

|                | Name           |
| -------------- | -------------- |
| virtual | **[~MetaAnalysis](/doxygen/Classes/classsam_1_1_meta_analysis/#function-~metaanalysis)**() =0 |
| std::unique_ptr< [MetaAnalysis](/doxygen/Classes/classsam_1_1_meta_analysis/) > | **[build](/doxygen/Classes/classsam_1_1_meta_analysis/#function-build)**(std::string name) |
| std::unique_ptr< [MetaAnalysis](/doxygen/Classes/classsam_1_1_meta_analysis/) > | **[build](/doxygen/Classes/classsam_1_1_meta_analysis/#function-build)**(const json & config) |
| std::vector< std::string > | **[Columns](/doxygen/Classes/classsam_1_1_meta_analysis/#function-columns)**(std::string name) |


## Public Functions Documentation

### function TrimAndFill

```cpp
TrimAndFill() =default
```


### function TrimAndFill

```cpp
inline TrimAndFill(
    const Parameters & p
)
```


### function estimate

```cpp
virtual void estimate(
    Journal * journal
)
```


**Reimplements**: [sam::MetaAnalysis::estimate](/doxygen/Classes/classsam_1_1_meta_analysis/#function-estimate)


### function TF

```cpp
static ResultType TF(
    arma::Row< double > yi,
    arma::Row< double > vi,
    arma::Row< double > ni,
    const Parameters & params
)
```


Determining the side

flip data if examining right side

sort data by increasing yi

centered values;

Todoties_method="first"); // ranked absolute centered values; 

signed ranked centered values;

estimate the number of missing studies with the L0 estimator

estimate the number of missing studies with the Q0 estimator

round k0 and make sure that k0 is non-negative

---------------&mdash; Filling and estimating -------------&mdash;

if estimated number of missing studies is > 0

flip data back if side is right

create filled-in data set

apply limits if specified Todo: to be implemented 

fit model with imputed data

Todoneed to be integrated! 

Adjustment for p_k0

TodoThis imbue can be improved 

TodoStill need to report the p_k0 


## Public Attributes Documentation

### variable params

```cpp
Parameters params;
```


-------------------------------

Updated on  7 June 2021 at 12:00:21 CEST