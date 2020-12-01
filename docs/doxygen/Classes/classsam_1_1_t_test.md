---
title: sam::TTest
summary: Declration of t-test.  

---

# sam::TTest




Declration of t-test.  [More...](#detailed-description)


`#include <TestStrategy.h>`


Inherits from [sam::TestStrategy](/doxygen/Classes/classsam_1_1_test_strategy/)



## Public Classes

|                | Name           |
| -------------- | -------------- |
| struct | **[Parameters](/doxygen/Classes/structsam_1_1_t_test_1_1_parameters/)**  |
| struct | **[ResultType](/doxygen/Classes/structsam_1_1_t_test_1_1_result_type/)**  |








## Public Functions

|                | Name           |
| -------------- | -------------- |
|  | **[TTest](/doxygen/Classes/classsam_1_1_t_test/#function-ttest)**(const [Parameters](/doxygen/Classes/structsam_1_1_t_test_1_1_parameters/) & p)  |
| virtual void | **[run](/doxygen/Classes/classsam_1_1_t_test/#function-run)**([Experiment](/doxygen/Classes/classsam_1_1_experiment/) * experiment) override  |
| virtual void | **[run](/doxygen/Classes/classsam_1_1_t_test/#function-run)**([Group](/doxygen/Classes/classsam_1_1_group/) & group_1, [Group](/doxygen/Classes/classsam_1_1_group/) & group_2) override  |
| [ResultType](/doxygen/Classes/structsam_1_1_t_test_1_1_result_type/) | **[t_test](/doxygen/Classes/classsam_1_1_t_test/#function-t_test)**(const arma::Row< double > & d1, const arma::Row< double > & d2, double alpha, [TestStrategy::TestAlternative](/doxygen/Classes/classsam_1_1_test_strategy/#enum-testalternative) alternative)  |
| [ResultType](/doxygen/Classes/structsam_1_1_t_test_1_1_result_type/) | **[t_test](/doxygen/Classes/classsam_1_1_t_test/#function-t_test)**(double Sm1, double Sd1, double Sn1, double Sm2, double Sd2, double Sn2, double alpha, [TestStrategy::TestAlternative](/doxygen/Classes/classsam_1_1_test_strategy/#enum-testalternative) alternative, bool equal_var)  |
| std::pair< double, bool > | **[compute_pvalue](/doxygen/Classes/classsam_1_1_t_test/#function-compute_pvalue)**(double tstat, double df, double alpha, [TestStrategy::TestAlternative](/doxygen/Classes/classsam_1_1_test_strategy/#enum-testalternative) alternative)  |
| [ResultType](/doxygen/Classes/structsam_1_1_t_test_1_1_result_type/) | **[single_sample_t_test](/doxygen/Classes/classsam_1_1_t_test/#function-single_sample_t_test)**(double M, double Sm, double Sd, unsigned Sn, double alpha, [TestStrategy::TestAlternative](/doxygen/Classes/classsam_1_1_test_strategy/#enum-testalternative) alternative)  |
| [ResultType](/doxygen/Classes/structsam_1_1_t_test_1_1_result_type/) | **[two_samples_t_test_equal_sd](/doxygen/Classes/classsam_1_1_t_test/#function-two_samples_t_test_equal_sd)**(double Sm1, double Sd1, unsigned Sn1, double Sm2, double Sd2, unsigned Sn2, double alpha, [TestStrategy::TestAlternative](/doxygen/Classes/classsam_1_1_test_strategy/#enum-testalternative) alternative)  |
| [ResultType](/doxygen/Classes/structsam_1_1_t_test_1_1_result_type/) | **[two_samples_t_test_unequal_sd](/doxygen/Classes/classsam_1_1_t_test/#function-two_samples_t_test_unequal_sd)**(double Sm1, double Sd1, unsigned Sn1, double Sm2, double Sd2, unsigned Sn2, double alpha, [TestStrategy::TestAlternative](/doxygen/Classes/classsam_1_1_test_strategy/#enum-testalternative) alternative)  |


## Public Attributes

|                | Name           |
| -------------- | -------------- |
| [Parameters](/doxygen/Classes/structsam_1_1_t_test_1_1_parameters/) | **[params](/doxygen/Classes/classsam_1_1_t_test/#variable-params)**  |




## Additional inherited members




**Public Types inherited from [sam::TestStrategy](/doxygen/Classes/classsam_1_1_test_strategy/)**

|                | Name           |
| -------------- | -------------- |
| enum | **[TestMethod](/doxygen/Classes/classsam_1_1_test_strategy/#enum-testmethod)** { TTest, FTest, YuenTest, WilcoxonTest } |
| enum | **[TestAlternative](/doxygen/Classes/classsam_1_1_test_strategy/#enum-testalternative)** { Less, Greater, TwoSided } |






**Public Functions inherited from [sam::TestStrategy](/doxygen/Classes/classsam_1_1_test_strategy/)**

|                | Name           |
| -------------- | -------------- |
| virtual  | **[~TestStrategy](/doxygen/Classes/classsam_1_1_test_strategy/#function-~teststrategy)**() =0  |
| virtual double | **[alpha](/doxygen/Classes/classsam_1_1_test_strategy/#function-alpha)**()  |
| std::unique_ptr< [TestStrategy](/doxygen/Classes/classsam_1_1_test_strategy/) > | **[build](/doxygen/Classes/classsam_1_1_test_strategy/#function-build)**(json & test_strategy_config)  |


**Public Attributes inherited from [sam::TestStrategy](/doxygen/Classes/classsam_1_1_test_strategy/)**

|                | Name           |
| -------------- | -------------- |
| double | **[alpha_](/doxygen/Classes/classsam_1_1_test_strategy/#variable-alpha_)**  |





## Detailed Description

```cpp
class sam::TTest;
```

Declration of t-test. 


























The `[run()](/doxygen/Classes/classsam_1_1_t_test/#function-run)` method will check the significance of the difference between two groups. In the current setup, every `experiment->means` is considered an effect size between a treatment group and a control group with the mean of zero. Therefore, computing the t-statistics and computing the p-value would be sufficient. This is technically an implementation of [one sample t-test](https://en.wikipedia.org/wiki/Student%27s_t-test#One-sample_t-test). 









## Public Functions Documentation

### function TTest

```cpp
inline TTest(
    const Parameters & p
)
```





























### function run

```cpp
virtual void run(
    Experiment * experiment
) override
```


























**Reimplements**: [sam::TestStrategy::run](/doxygen/Classes/classsam_1_1_test_strategy/#function-run)



TodoThis could be declared static 

### function run

```cpp
inline virtual void run(
    Group & group_1,
    Group & group_2
) override
```


























**Reimplements**: [sam::TestStrategy::run](/doxygen/Classes/classsam_1_1_test_strategy/#function-run)




### function t_test

```cpp
static ResultType t_test(
    const arma::Row< double > & d1,
    const arma::Row< double > & d2,
    double alpha,
    TestStrategy::TestAlternative alternative
)
```





























### function t_test

```cpp
static ResultType t_test(
    double Sm1,
    double Sd1,
    double Sn1,
    double Sm2,
    double Sd2,
    double Sn2,
    double alpha,
    TestStrategy::TestAlternative alternative,
    bool equal_var
)
```





























### function compute_pvalue

```cpp
static std::pair< double, bool > compute_pvalue(
    double tstat,
    double df,
    double alpha,
    TestStrategy::TestAlternative alternative
)
```





























### function single_sample_t_test

```cpp
static ResultType single_sample_t_test(
    double M,
    double Sm,
    double Sd,
    unsigned Sn,
    double alpha,
    TestStrategy::TestAlternative alternative
)
```


**Parameters**: 

  * **M** True Mean. 
  * **Sm** Sample Mean. 
  * **Sd** Sample Standard Deviation. 
  * **Sn** Sample Size. 
  * **alpha** Significance Level. 







**Return**: [TTest::ResultType](/doxygen/Classes/structsam_1_1_t_test_1_1_result_type/)





**Note**: Obtained from [Boost Library Example](https://www.boost.org/doc/libs/1_69_0/libs/math/doc/html/math_toolkit/stat_tut/weg/st_eg/paired_st.html).














A Students t test applied to a single set of data. We are testing the null hypothesis that the true mean of the sample is M, and that any variation is down to chance. We can also test the alternative hypothesis that any difference is not down to chance


### function two_samples_t_test_equal_sd

```cpp
static ResultType two_samples_t_test_equal_sd(
    double Sm1,
    double Sd1,
    unsigned Sn1,
    double Sm2,
    double Sd2,
    unsigned Sn2,
    double alpha,
    TestStrategy::TestAlternative alternative
)
```


**Parameters**: 

  * **Sm1** Sample Mean 1. 
  * **Sd1** Sample Standard Deviation 1. 
  * **Sn1** Sample Size 1. 
  * **Sm2** Sample Mean 2. 
  * **Sd2** Sample Standard Deviation 2. 
  * **Sn2** Sample Size 2. 
  * **alpha** Significance Level. 







**Return**: [TTest::ResultType](/doxygen/Classes/structsam_1_1_t_test_1_1_result_type/)





**Note**: Obtained from [Boost Library Example](https://www.boost.org/doc/libs/1_69_0/libs/math/doc/html/math_toolkit/stat_tut/weg/st_eg/paired_st.html).














A Students t test applied to two sets of data. We are testing the null hypothesis that the two samples have the same mean and that any difference if due to chance.


### function two_samples_t_test_unequal_sd

```cpp
static ResultType two_samples_t_test_unequal_sd(
    double Sm1,
    double Sd1,
    unsigned Sn1,
    double Sm2,
    double Sd2,
    unsigned Sn2,
    double alpha,
    TestStrategy::TestAlternative alternative
)
```


**Parameters**: 

  * **Sm1** Sample Mean 1. 
  * **Sd1** Sample Standard Deviation 1. 
  * **Sn1** Sample Size 1. 
  * **Sm2** Sample Mean 2. 
  * **Sd2** Sample Standard Deviation 2. 
  * **Sn2** Sample Size 2. 
  * **alpha** Significance Level. 







**Return**: [TTest::ResultType](/doxygen/Classes/structsam_1_1_t_test_1_1_result_type/)





**Note**: Obtained from [Boost Library Example](https://www.boost.org/doc/libs/1_69_0/libs/math/doc/html/math_toolkit/stat_tut/weg/st_eg/paired_st.html).














A Students t test applied to two sets of data with _unequal_ variance. We are testing the null hypothesis that the two samples have the same mean and that any difference is due to chance.




## Public Attributes Documentation

### variable params

```cpp
Parameters params;
```

































-------------------------------

Updated on 23 November 2020 at 14:03:44 CET