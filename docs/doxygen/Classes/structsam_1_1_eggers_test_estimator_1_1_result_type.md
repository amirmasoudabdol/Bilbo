---
title: sam::EggersTestEstimator::ResultType

---

# sam::EggersTestEstimator::ResultType



 [More...](#detailed-description)


`#include <MetaAnalysis.h>`

## Public Functions

|                | Name           |
| -------------- | -------------- |
| std::vector< std::string > | **[Columns](/doxygen/Classes/structsam_1_1_eggers_test_estimator_1_1_result_type/#function-columns)**() |

## Public Attributes

|                | Name           |
| -------------- | -------------- |
| float | **[slope](/doxygen/Classes/structsam_1_1_eggers_test_estimator_1_1_result_type/#variable-slope)** <br>The slope of the fitted line.  |
| float | **[se](/doxygen/Classes/structsam_1_1_eggers_test_estimator_1_1_result_type/#variable-se)** <br>The standard error of the slope.  |
| float | **[tstat](/doxygen/Classes/structsam_1_1_eggers_test_estimator_1_1_result_type/#variable-tstat)** <br>The t-statistic of the test.  |
| float | **[pval](/doxygen/Classes/structsam_1_1_eggers_test_estimator_1_1_result_type/#variable-pval)** <br>The p-value of the test.  |
| bool | **[sig](/doxygen/Classes/structsam_1_1_eggers_test_estimator_1_1_result_type/#variable-sig)** <br>The significance of the test.  |
| float | **[df](/doxygen/Classes/structsam_1_1_eggers_test_estimator_1_1_result_type/#variable-df)** <br>The degree-of-freedom of the test.  |

## Detailed Description

```cpp
struct sam::EggersTestEstimator::ResultType;
```


Egger's Test Output 

## Public Functions Documentation

### function Columns

```cpp
static inline std::vector< std::string > Columns()
```


## Public Attributes Documentation

### variable slope

```cpp
float slope;
```

The slope of the fitted line. 

### variable se

```cpp
float se;
```

The standard error of the slope. 

### variable tstat

```cpp
float tstat;
```

The t-statistic of the test. 

### variable pval

```cpp
float pval;
```

The p-value of the test. 

### variable sig

```cpp
bool sig;
```

The significance of the test. 

### variable df

```cpp
float df;
```

The degree-of-freedom of the test. 

-------------------------------

Updated on 29 June 2021 at 16:13:47 CEST