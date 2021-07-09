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
| float | **[est](/doxygen/Classes/structsam_1_1_rank_correlation_1_1_result_type/#variable-est)** <br>Kendall's tau estimate.  |
| float | **[pval](/doxygen/Classes/structsam_1_1_rank_correlation_1_1_result_type/#variable-pval)** <br>The p-value of the test.  |
| bool | **[sig](/doxygen/Classes/structsam_1_1_rank_correlation_1_1_result_type/#variable-sig)** <br>The significance of the test.  |

## Public Functions Documentation

### function Columns

```cpp
static inline std::vector< std::string > Columns()
```


## Public Attributes Documentation

### variable est

```cpp
float est;
```

Kendall's tau estimate. 

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

-------------------------------

Updated on 29 June 2021 at 16:13:47 CEST