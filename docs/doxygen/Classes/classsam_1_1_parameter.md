---
title: sam::Parameter
summary: An abstract class for a random variable parameter.  

---

# sam::Parameter




An abstract class for a random variable parameter.  [More...](#detailed-description)


`#include <Parameter.h>`


Inherits from arma::Row< T >











## Public Functions

|                | Name           |
| -------------- | -------------- |
|  | **[Parameter](/doxygen/Classes/classsam_1_1_parameter/#function-parameter)**()  |
|  | **[Parameter](/doxygen/Classes/classsam_1_1_parameter/#function-parameter)**(std::initializer_list< T > l)  |
|  | **[Parameter](/doxygen/Classes/classsam_1_1_parameter/#function-parameter)**(const json & j, size_t size)  |
| void | **[randomize](/doxygen/Classes/classsam_1_1_parameter/#function-randomize)**()  |
|  | **[operator T](/doxygen/Classes/classsam_1_1_parameter/#function-operator-t)**()  |
| bool | **[isDist](/doxygen/Classes/classsam_1_1_parameter/#function-isdist)**()  |








## Detailed Description

```cpp
template <typename T >
class sam::Parameter;
```

An abstract class for a random variable parameter. 















**Todo**: 

  * Implement a copy constructor that can handle the copy from arma::Row<T> 
  * Implement a double operator()() 












This is designed to capture the encapsulate a distribution and therefore mimic the behavior or a random variable.









## Public Functions Documentation

### function Parameter

```cpp
inline Parameter()
```





























### function Parameter

```cpp
inline Parameter(
    std::initializer_list< T > l
)
```





























### function Parameter

```cpp
Parameter(
    const json & j,
    size_t size
)
```




























Multivariante Distribution

Univariate Distribution

### function randomize

```cpp
void randomize()
```





























### function operator T

```cpp
inline operator T()
```





























### function isDist

```cpp
inline bool isDist()
```



































-------------------------------

Updated on  2 December 2020 at 14:48:54 CET