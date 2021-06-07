---
title: sam::RankCorrelation::ResultType

---

# sam::RankCorrelation::ResultType



## Public Functions

|                | Name           |
| -------------- | -------------- |
| std::vector< std::string > | **[Columns](/doxygen/Classes/structsam_1_1_rank_correlation_1_1_result_type/#function-columns)**() |

## Public Attributes

|                | Name           |
| -------------- | -------------- |
| double | **[est](/doxygen/Classes/structsam_1_1_rank_correlation_1_1_result_type/#variable-est)** <br>Kendall's tau estimate.  |
| double | **[pval](/doxygen/Classes/structsam_1_1_rank_correlation_1_1_result_type/#variable-pval)** <br>The p-value of the test.  |
| bool | **[sig](/doxygen/Classes/structsam_1_1_rank_correlation_1_1_result_type/#variable-sig)** <br>The significance of the test.  |

## Public Functions Documentation

### function Columns

```cpp
static inline std::vector< std::string > Columns()
```


## Public Attributes Documentation

### variable est

```cpp
double est;
```

Kendall's tau estimate. 

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

-------------------------------

Updated on  7 June 2021 at 12:00:21 CEST