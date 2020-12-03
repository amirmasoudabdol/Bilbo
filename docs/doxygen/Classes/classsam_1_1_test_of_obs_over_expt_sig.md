---
title: sam::TestOfObsOverExptSig


---

# sam::TestOfObsOverExptSig


**Module:** **[Meta Analysis Methods](/doxygen/Modules/group___meta_analysis/)**





Inherits from [sam::MetaAnalysis](/doxygen/Classes/classsam_1_1_meta_analysis/)



## Public Classes

|                | Name           |
| -------------- | -------------- |
| struct | **[Parameters](/doxygen/Classes/structsam_1_1_test_of_obs_over_expt_sig_1_1_parameters/)**  |
| struct | **[ResultType](/doxygen/Classes/structsam_1_1_test_of_obs_over_expt_sig_1_1_result_type/)**  |








## Public Functions

|                | Name           |
| -------------- | -------------- |
|  | **[TestOfObsOverExptSig](/doxygen/Classes/classsam_1_1_test_of_obs_over_expt_sig/#function-testofobsoverexptsig)**() =default  |
|  | **[TestOfObsOverExptSig](/doxygen/Classes/classsam_1_1_test_of_obs_over_expt_sig/#function-testofobsoverexptsig)**(const [Parameters](/doxygen/Classes/structsam_1_1_test_of_obs_over_expt_sig_1_1_parameters/) & p)  |
| virtual void | **[estimate](/doxygen/Classes/classsam_1_1_test_of_obs_over_expt_sig/#function-estimate)**([Journal](/doxygen/Classes/classsam_1_1_journal/) * journal)  |
| [ResultType](/doxygen/Classes/structsam_1_1_test_of_obs_over_expt_sig_1_1_result_type/) | **[TES](/doxygen/Classes/classsam_1_1_test_of_obs_over_expt_sig/#function-tes)**(const arma::Row< double > & sigs, const arma::Row< double > & ni, double beta, double alpha)  |


## Public Attributes

|                | Name           |
| -------------- | -------------- |
| [Parameters](/doxygen/Classes/structsam_1_1_test_of_obs_over_expt_sig_1_1_parameters/) | **[params](/doxygen/Classes/classsam_1_1_test_of_obs_over_expt_sig/#variable-params)**  |




## Additional inherited members










**Public Functions inherited from [sam::MetaAnalysis](/doxygen/Classes/classsam_1_1_meta_analysis/)**

|                | Name           |
| -------------- | -------------- |
| virtual  | **[~MetaAnalysis](/doxygen/Classes/classsam_1_1_meta_analysis/#function-~metaanalysis)**() =0  |
| std::unique_ptr< [MetaAnalysis](/doxygen/Classes/classsam_1_1_meta_analysis/) > | **[build](/doxygen/Classes/classsam_1_1_meta_analysis/#function-build)**(std::string name)  |
| std::unique_ptr< [MetaAnalysis](/doxygen/Classes/classsam_1_1_meta_analysis/) > | **[build](/doxygen/Classes/classsam_1_1_meta_analysis/#function-build)**(const json & config)  |
| std::vector< std::string > | **[Columns](/doxygen/Classes/classsam_1_1_meta_analysis/#function-columns)**(std::string name)  |















## Public Functions Documentation

### function TestOfObsOverExptSig

```cpp
TestOfObsOverExptSig() =default
```





























### function TestOfObsOverExptSig

```cpp
inline TestOfObsOverExptSig(
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




### function TES

```cpp
static ResultType TES(
    const arma::Row< double > & sigs,
    const arma::Row< double > & ni,
    double beta,
    double alpha
)
```




























If E is absolute zero, I'm adding some noise that I don't have to deal with the explosion


A is most likely different from what R spit out, due to brutal rounding that's happening in R.



## Public Attributes Documentation

### variable params

```cpp
Parameters params;
```

































-------------------------------

Updated on  3 December 2020 at 12:37:29 CET