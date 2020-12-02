---
title: sam::RankCorrelation


---

# sam::RankCorrelation








Inherits from [sam::MetaAnalysis](/doxygen/Classes/classsam_1_1_meta_analysis/)



## Public Classes

|                | Name           |
| -------------- | -------------- |
| struct | **[Parameters](/doxygen/Classes/structsam_1_1_rank_correlation_1_1_parameters/)**  |
| struct | **[ResultType](/doxygen/Classes/structsam_1_1_rank_correlation_1_1_result_type/)**  |








## Public Functions

|                | Name           |
| -------------- | -------------- |
|  | **[RankCorrelation](/doxygen/Classes/classsam_1_1_rank_correlation/#function-rankcorrelation)**() =default  |
|  | **[RankCorrelation](/doxygen/Classes/classsam_1_1_rank_correlation/#function-rankcorrelation)**(const [Parameters](/doxygen/Classes/structsam_1_1_rank_correlation_1_1_parameters/) & p)  |
| virtual void | **[estimate](/doxygen/Classes/classsam_1_1_rank_correlation/#function-estimate)**([Journal](/doxygen/Classes/classsam_1_1_journal/) * journal)  |
| [ResultType](/doxygen/Classes/structsam_1_1_rank_correlation_1_1_result_type/) | **[RankCor](/doxygen/Classes/classsam_1_1_rank_correlation/#function-rankcor)**(arma::Row< double > yi, arma::Row< double > vi, const [Parameters](/doxygen/Classes/structsam_1_1_rank_correlation_1_1_parameters/) & params)  |
| arma::Row< int > | **[duplicate_count](/doxygen/Classes/classsam_1_1_rank_correlation/#function-duplicate_count)**(arma::rowvec x)  |


## Public Attributes

|                | Name           |
| -------------- | -------------- |
| [Parameters](/doxygen/Classes/structsam_1_1_rank_correlation_1_1_parameters/) | **[params](/doxygen/Classes/classsam_1_1_rank_correlation/#variable-params)**  |




## Additional inherited members










**Public Functions inherited from [sam::MetaAnalysis](/doxygen/Classes/classsam_1_1_meta_analysis/)**

|                | Name           |
| -------------- | -------------- |
| virtual  | **[~MetaAnalysis](/doxygen/Classes/classsam_1_1_meta_analysis/#function-~metaanalysis)**() =0  |
| std::unique_ptr< [MetaAnalysis](/doxygen/Classes/classsam_1_1_meta_analysis/) > | **[build](/doxygen/Classes/classsam_1_1_meta_analysis/#function-build)**(std::string name)  |
| std::unique_ptr< [MetaAnalysis](/doxygen/Classes/classsam_1_1_meta_analysis/) > | **[build](/doxygen/Classes/classsam_1_1_meta_analysis/#function-build)**(const json & config)  |
| std::vector< std::string > | **[Columns](/doxygen/Classes/classsam_1_1_meta_analysis/#function-columns)**(std::string name)  |















## Public Functions Documentation

### function RankCorrelation

```cpp
RankCorrelation() =default
```





























### function RankCorrelation

```cpp
inline RankCorrelation(
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




### function RankCor

```cpp
static ResultType RankCor(
    arma::Row< double > yi,
    arma::Row< double > vi,
    const Parameters & params
)
```





























### function duplicate_count

```cpp
static arma::Row< int > duplicate_count(
    arma::rowvec x
)
```































## Public Attributes Documentation

### variable params

```cpp
Parameters params;
```

































-------------------------------

Updated on 23 November 2020 at 14:03:43 CET