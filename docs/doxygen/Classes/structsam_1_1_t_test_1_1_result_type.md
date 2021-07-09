---
title: sam::TTest::ResultType

---

# sam::TTest::ResultType



## Public Attributes

|                | Name           |
| -------------- | -------------- |
| float | **[tstat](/doxygen/Classes/structsam_1_1_t_test_1_1_result_type/#variable-tstat)**  |
| float | **[df](/doxygen/Classes/structsam_1_1_t_test_1_1_result_type/#variable-df)**  |
| float | **[pvalue](/doxygen/Classes/structsam_1_1_t_test_1_1_result_type/#variable-pvalue)**  |
| int | **[side](/doxygen/Classes/structsam_1_1_t_test_1_1_result_type/#variable-side)**  |
| bool | **[sig](/doxygen/Classes/structsam_1_1_t_test_1_1_result_type/#variable-sig)**  |

## Friends

|                | Name           |
| -------------- | -------------- |
| std::ostream & | **[operator<<](/doxygen/Classes/structsam_1_1_t_test_1_1_result_type/#friend-operator<<)**(std::ostream & os, const [ResultType](/doxygen/Classes/structsam_1_1_t_test_1_1_result_type/) & type)  |

## Public Attributes Documentation

### variable tstat

```cpp
float tstat;
```


### variable df

```cpp
float df;
```


### variable pvalue

```cpp
float pvalue;
```


### variable side

```cpp
int side;
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