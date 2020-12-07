---
title: sam::TestOfObsOverExptSig::ResultType


---

# sam::TestOfObsOverExptSig::ResultType



















## Public Functions

|                | Name           |
| -------------- | -------------- |
| std::vector< std::string > | **[Columns](/doxygen/Classes/structsam_1_1_test_of_obs_over_expt_sig_1_1_result_type/#function-columns)**()  |
|  | **[operator arma::Row< double >](/doxygen/Classes/structsam_1_1_test_of_obs_over_expt_sig_1_1_result_type/#function-operator-armarow<-double->)**()  |


## Public Attributes

|                | Name           |
| -------------- | -------------- |
| double | **[E](/doxygen/Classes/structsam_1_1_test_of_obs_over_expt_sig_1_1_result_type/#variable-e)** <br>Sum of the expected probabilities.  |
| double | **[A](/doxygen/Classes/structsam_1_1_test_of_obs_over_expt_sig_1_1_result_type/#variable-a)** <br>The chi-square statistic of the test.  |
| double | **[pval](/doxygen/Classes/structsam_1_1_test_of_obs_over_expt_sig_1_1_result_type/#variable-pval)** <br>The p-value of the test.  |
| bool | **[sig](/doxygen/Classes/structsam_1_1_test_of_obs_over_expt_sig_1_1_result_type/#variable-sig)** <br>The significance of the test.  |














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

### variable E

```cpp
double E;
```

Sum of the expected probabilities. 




























### variable A

```cpp
double A;
```

The chi-square statistic of the test. 




























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

Updated on  7 December 2020 at 13:20:10 CET