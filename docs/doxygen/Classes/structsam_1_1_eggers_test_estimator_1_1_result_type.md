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
| | **[operator arma::Row< double >](/doxygen/Classes/structsam_1_1_eggers_test_estimator_1_1_result_type/#function-operator-armarow<-double->)**() |

## Public Attributes

|                | Name           |
| -------------- | -------------- |
| double | **[slope](/doxygen/Classes/structsam_1_1_eggers_test_estimator_1_1_result_type/#variable-slope)** <br>The slope of the fitted line.  |
| double | **[se](/doxygen/Classes/structsam_1_1_eggers_test_estimator_1_1_result_type/#variable-se)** <br>The standard error of the slope.  |
| double | **[tstat](/doxygen/Classes/structsam_1_1_eggers_test_estimator_1_1_result_type/#variable-tstat)** <br>The t-statistic of the test.  |
| double | **[pval](/doxygen/Classes/structsam_1_1_eggers_test_estimator_1_1_result_type/#variable-pval)** <br>The p-value of the test.  |
| bool | **[sig](/doxygen/Classes/structsam_1_1_eggers_test_estimator_1_1_result_type/#variable-sig)** <br>The significance of the test.  |
| double | **[df](/doxygen/Classes/structsam_1_1_eggers_test_estimator_1_1_result_type/#variable-df)** <br>The degree-of-freedom of the test.  |

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


### function operator arma::Row< double >

```cpp
inline operator arma::Row< double >()
```


## Public Attributes Documentation

### variable slope

```cpp
double slope;
```

The slope of the fitted line. 

### variable se

```cpp
double se;
```

The standard error of the slope. 

### variable tstat

```cpp
double tstat;
```

The t-statistic of the test. 

### variable pval

```cpp
double pval;
```

The p-value of the test. 

### variable sig

```cpp
bool sig;
```

The significance of the test. 

### variable df

```cpp
double df;
```

The degree-of-freedom of the test. 

-------------------------------

Updated on  7 May 2021 at 14:51:32 CEST