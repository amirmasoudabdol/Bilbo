---
title: sam::TestStrategy
summary: Abstract class for defining test strategies. 

---

# sam::TestStrategy



Abstract class for defining test strategies.  [More...](#detailed-description)


`#include <TestStrategy.h>`

Inherited by [sam::FTest](/doxygen/Classes/classsam_1_1_f_test/), [sam::TTest](/doxygen/Classes/classsam_1_1_t_test/), [sam::WilcoxonTest](/doxygen/Classes/classsam_1_1_wilcoxon_test/), [sam::YuenTest](/doxygen/Classes/classsam_1_1_yuen_test/)

## Public Types

|                | Name           |
| -------------- | -------------- |
| enum| **[TestMethod](/doxygen/Classes/classsam_1_1_test_strategy/#enum-testmethod)** { TTest, FTest, YuenTest, WilcoxonTest} |
| enum| **[TestAlternative](/doxygen/Classes/classsam_1_1_test_strategy/#enum-testalternative)** { Less, Greater, TwoSided} |

## Public Functions

|                | Name           |
| -------------- | -------------- |
| virtual | **[~TestStrategy](/doxygen/Classes/classsam_1_1_test_strategy/#function-~teststrategy)**() =0 |
| virtual void | **[run](/doxygen/Classes/classsam_1_1_test_strategy/#function-run)**([Experiment](/doxygen/Classes/classsam_1_1_experiment/) * experiment) =0 |
| virtual void | **[run](/doxygen/Classes/classsam_1_1_test_strategy/#function-run)**([DependentVariable](/doxygen/Classes/classsam_1_1_dependent_variable/) & group_1, [DependentVariable](/doxygen/Classes/classsam_1_1_dependent_variable/) & group_2) =0 |
| virtual float | **[alpha](/doxygen/Classes/classsam_1_1_test_strategy/#function-alpha)**() |
| std::unique_ptr< [TestStrategy](/doxygen/Classes/classsam_1_1_test_strategy/) > | **[build](/doxygen/Classes/classsam_1_1_test_strategy/#function-build)**(json & test_strategy_config) |

## Public Attributes

|                | Name           |
| -------------- | -------------- |
| float | **[alpha_](/doxygen/Classes/classsam_1_1_test_strategy/#variable-alpha_)**  |

## Detailed Description

```cpp
class sam::TestStrategy;
```

Abstract class for defining test strategies. 

Statistical test strategies will investigate if there is a meaningful difference between means of two samples. Every test strategy should provide a `run()` method. The `run()` method will accept a pointer to the experiment and update necessary variables, e.g., _statistics_ & _p-value_. 

## Public Types Documentation

### enum TestMethod

| Enumerator | Value | Description |
| ---------- | ----- | ----------- |
| TTest | | [TTest]().   |
| FTest | | [FTest]().   |
| YuenTest | | [YuenTest]().   |
| WilcoxonTest | | [WilcoxonTest]().   |




Specifying the significant testing method 


### enum TestAlternative

| Enumerator | Value | Description |
| ---------- | ----- | ----------- |
| Less | |   |
| Greater | |   |
| TwoSided | |   |




Specify the side of the test 


## Public Functions Documentation

### function ~TestStrategy

```cpp
virtual ~TestStrategy() =0
```


### function run

```cpp
virtual void run(
    Experiment * experiment
) =0
```


**Reimplemented by**: [sam::TTest::run](/doxygen/Classes/classsam_1_1_t_test/#function-run), [sam::FTest::run](/doxygen/Classes/classsam_1_1_f_test/#function-run), [sam::YuenTest::run](/doxygen/Classes/classsam_1_1_yuen_test/#function-run), [sam::WilcoxonTest::run](/doxygen/Classes/classsam_1_1_wilcoxon_test/#function-run)


### function run

```cpp
virtual void run(
    DependentVariable & group_1,
    DependentVariable & group_2
) =0
```


**Reimplemented by**: [sam::TTest::run](/doxygen/Classes/classsam_1_1_t_test/#function-run), [sam::FTest::run](/doxygen/Classes/classsam_1_1_f_test/#function-run), [sam::YuenTest::run](/doxygen/Classes/classsam_1_1_yuen_test/#function-run), [sam::WilcoxonTest::run](/doxygen/Classes/classsam_1_1_wilcoxon_test/#function-run)


### function alpha

```cpp
inline virtual float alpha()
```


### function build

```cpp
static std::unique_ptr< TestStrategy > build(
    json & test_strategy_config
)
```


## Public Attributes Documentation

### variable alpha_

```cpp
float alpha_;
```


-------------------------------

Updated on 29 June 2021 at 16:13:47 CEST