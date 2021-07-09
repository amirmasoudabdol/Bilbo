---
title: sam::YuenTest

---

# sam::YuenTest

**Module:** **[Test Strategies](/doxygen/Modules/group___test_strategies/)**



Inherits from [sam::TestStrategy](/doxygen/Classes/classsam_1_1_test_strategy/)

## Public Classes

|                | Name           |
| -------------- | -------------- |
| struct | **[Parameters](/doxygen/Classes/structsam_1_1_yuen_test_1_1_parameters/)**  |
| struct | **[ResultType](/doxygen/Classes/structsam_1_1_yuen_test_1_1_result_type/)**  |

## Public Functions

|                | Name           |
| -------------- | -------------- |
| | **[YuenTest](/doxygen/Classes/classsam_1_1_yuen_test/#function-yuentest)**(const [Parameters](/doxygen/Classes/structsam_1_1_yuen_test_1_1_parameters/) & p) |
| virtual void | **[run](/doxygen/Classes/classsam_1_1_yuen_test/#function-run)**([Experiment](/doxygen/Classes/classsam_1_1_experiment/) * experiment) override |
| virtual void | **[run](/doxygen/Classes/classsam_1_1_yuen_test/#function-run)**([DependentVariable](/doxygen/Classes/classsam_1_1_dependent_variable/) & group_1, [DependentVariable](/doxygen/Classes/classsam_1_1_dependent_variable/) & group_2) override |
| [ResultType](/doxygen/Classes/structsam_1_1_yuen_test_1_1_result_type/) | **[yuen_t_test_one_sample](/doxygen/Classes/classsam_1_1_yuen_test/#function-yuen_t_test_one_sample)**(const arma::Row< float > & x, float alpha, const [TestStrategy::TestAlternative](/doxygen/Classes/classsam_1_1_test_strategy/#enum-testalternative) alternative, float trim, float mu) |
| [ResultType](/doxygen/Classes/structsam_1_1_yuen_test_1_1_result_type/) | **[yuen_t_test_paired](/doxygen/Classes/classsam_1_1_yuen_test/#function-yuen_t_test_paired)**(const arma::Row< float > & x, const arma::Row< float > & y, float alpha, const [TestStrategy::TestAlternative](/doxygen/Classes/classsam_1_1_test_strategy/#enum-testalternative) alternative, float trim, float mu) |
| [ResultType](/doxygen/Classes/structsam_1_1_yuen_test_1_1_result_type/) | **[yuen_t_test_two_samples](/doxygen/Classes/classsam_1_1_yuen_test/#function-yuen_t_test_two_samples)**(const arma::Row< float > & x, const arma::Row< float > & y, float alpha, const [TestStrategy::TestAlternative](/doxygen/Classes/classsam_1_1_test_strategy/#enum-testalternative) alternative, float trim, float mu) |

## Public Attributes

|                | Name           |
| -------------- | -------------- |
| [Parameters](/doxygen/Classes/structsam_1_1_yuen_test_1_1_parameters/) | **[params](/doxygen/Classes/classsam_1_1_yuen_test/#variable-params)**  |

## Additional inherited members

**Public Types inherited from [sam::TestStrategy](/doxygen/Classes/classsam_1_1_test_strategy/)**

|                | Name           |
| -------------- | -------------- |
| enum| **[TestMethod](/doxygen/Classes/classsam_1_1_test_strategy/#enum-testmethod)** { TTest, FTest, YuenTest, WilcoxonTest} |
| enum| **[TestAlternative](/doxygen/Classes/classsam_1_1_test_strategy/#enum-testalternative)** { Less, Greater, TwoSided} |

**Public Functions inherited from [sam::TestStrategy](/doxygen/Classes/classsam_1_1_test_strategy/)**

|                | Name           |
| -------------- | -------------- |
| virtual | **[~TestStrategy](/doxygen/Classes/classsam_1_1_test_strategy/#function-~teststrategy)**() =0 |
| virtual float | **[alpha](/doxygen/Classes/classsam_1_1_test_strategy/#function-alpha)**() |
| std::unique_ptr< [TestStrategy](/doxygen/Classes/classsam_1_1_test_strategy/) > | **[build](/doxygen/Classes/classsam_1_1_test_strategy/#function-build)**(json & test_strategy_config) |

**Public Attributes inherited from [sam::TestStrategy](/doxygen/Classes/classsam_1_1_test_strategy/)**

|                | Name           |
| -------------- | -------------- |
| float | **[alpha_](/doxygen/Classes/classsam_1_1_test_strategy/#variable-alpha_)**  |


## Public Functions Documentation

### function YuenTest

```cpp
inline YuenTest(
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


### function run

```cpp
inline virtual void run(
    DependentVariable & group_1,
    DependentVariable & group_2
) override
```


**Reimplements**: [sam::TestStrategy::run](/doxygen/Classes/classsam_1_1_test_strategy/#function-run)


### function yuen_t_test_one_sample

```cpp
static ResultType yuen_t_test_one_sample(
    const arma::Row< float > & x,
    float alpha,
    const TestStrategy::TestAlternative alternative,
    float trim,
    float mu
)
```


### function yuen_t_test_paired

```cpp
static ResultType yuen_t_test_paired(
    const arma::Row< float > & x,
    const arma::Row< float > & y,
    float alpha,
    const TestStrategy::TestAlternative alternative,
    float trim,
    float mu
)
```


### function yuen_t_test_two_samples

```cpp
static ResultType yuen_t_test_two_samples(
    const arma::Row< float > & x,
    const arma::Row< float > & y,
    float alpha,
    const TestStrategy::TestAlternative alternative,
    float trim,
    float mu
)
```


## Public Attributes Documentation

### variable params

```cpp
Parameters params;
```


-------------------------------

Updated on 29 June 2021 at 16:13:48 CEST