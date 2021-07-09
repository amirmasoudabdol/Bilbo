---
title: sam::FTest::ResultType

---

# sam::FTest::ResultType



## Public Attributes

|                | Name           |
| -------------- | -------------- |
| float | **[fstat](/doxygen/Classes/structsam_1_1_f_test_1_1_result_type/#variable-fstat)**  |
| unsigned | **[df1](/doxygen/Classes/structsam_1_1_f_test_1_1_result_type/#variable-df1)**  |
| unsigned | **[df2](/doxygen/Classes/structsam_1_1_f_test_1_1_result_type/#variable-df2)**  |
| float | **[pvalue](/doxygen/Classes/structsam_1_1_f_test_1_1_result_type/#variable-pvalue)**  |
| bool | **[sig](/doxygen/Classes/structsam_1_1_f_test_1_1_result_type/#variable-sig)**  |

## Friends

|                | Name           |
| -------------- | -------------- |
| std::ostream & | **[operator<<](/doxygen/Classes/structsam_1_1_f_test_1_1_result_type/#friend-operator<<)**(std::ostream & os, const [ResultType](/doxygen/Classes/structsam_1_1_f_test_1_1_result_type/) & type)  |

## Public Attributes Documentation

### variable fstat

```cpp
float fstat;
```


### variable df1

```cpp
unsigned df1;
```


### variable df2

```cpp
unsigned df2;
```


### variable pvalue

```cpp
float pvalue;
```


### variable sig

```cpp
bool sig;
```


## Friends

### friend operator<<

```cpp
friend std::ostream & operator<<(
    std::ostream & os,

    const ResultType & type
);
```


-------------------------------

Updated on 29 June 2021 at 16:13:48 CEST