---
title: sam::WilcoxonTest

---

# sam::WilcoxonTest

**Module:** **[Test Strategies](/doxygen/Modules/group___test_strategies/)**



Inherits from [sam::TestStrategy](/doxygen/Classes/classsam_1_1_test_strategy/)

## Public Classes

|                | Name           |
| -------------- | -------------- |
| struct | **[Parameters](/doxygen/Classes/structsam_1_1_wilcoxon_test_1_1_parameters/)**  |
| struct | **[ResultType](/doxygen/Classes/structsam_1_1_wilcoxon_test_1_1_result_type/)**  |

## Public Functions

|                | Name           |
| -------------- | -------------- |
| | **[WilcoxonTest](/doxygen/Classes/classsam_1_1_wilcoxon_test/#function-wilcoxontest)**(const [Parameters](/doxygen/Classes/structsam_1_1_wilcoxon_test_1_1_parameters/) & p) |
| virtual void | **[run](/doxygen/Classes/classsam_1_1_wilcoxon_test/#function-run)**([Experiment](/doxygen/Classes/classsam_1_1_experiment/) * experiment) override |
| virtual void | **[run](/doxygen/Classes/classsam_1_1_wilcoxon_test/#function-run)**([DependentVariable](/doxygen/Classes/classsam_1_1_dependent_variable/) & group_1, [DependentVariable](/doxygen/Classes/classsam_1_1_dependent_variable/) & group_2) override |
| [ResultType](/doxygen/Classes/structsam_1_1_wilcoxon_test_1_1_result_type/) | **[wilcoxon_test](/doxygen/Classes/classsam_1_1_wilcoxon_test/#function-wilcoxon_test)**(const arma::Row< float > & x, const arma::Row< float > & y, float alpha, float use_continuity, const [TestStrategy::TestAlternative](/doxygen/Classes/classsam_1_1_test_strategy/#enum-testalternative) alternative) |

## Public Attributes

|                | Name           |
| -------------- | -------------- |
| [Parameters](/doxygen/Classes/structsam_1_1_wilcoxon_test_1_1_parameters/) | **[params](/doxygen/Classes/classsam_1_1_wilcoxon_test/#variable-params)**  |

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

### function WilcoxonTest

```cpp
inline WilcoxonTest(
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


### function wilcoxon_test

```cpp
static ResultType wilcoxon_test(
    const arma::Row< float > & x,
    const arma::Row< float > & y,
    float alpha,
    float use_continuity,
    const TestStrategy::TestAlternative alternative
)
```


## Public Attributes Documentation

### variable params

```cpp
Parameters params;
```


-------------------------------

Updated on 29 June 2021 at 16:13:48 CEST