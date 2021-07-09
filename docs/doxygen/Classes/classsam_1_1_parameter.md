---
title: sam::Parameter
summary: An abstract representation of a random variable parameter. 

---

# sam::Parameter



An abstract representation of a random variable parameter.  [More...](#detailed-description)


`#include <Parameter.h>`

Inherits from arma::Row< T >

## Public Functions

|                | Name           |
| -------------- | -------------- |
| | **[Parameter](/doxygen/Classes/classsam_1_1_parameter/#function-parameter)**() |
| | **[Parameter](/doxygen/Classes/classsam_1_1_parameter/#function-parameter)**(const arma::Row< T > & X) |
| | **[Parameter](/doxygen/Classes/classsam_1_1_parameter/#function-parameter)**(std::initializer_list< T > l) |
| | **[Parameter](/doxygen/Classes/classsam_1_1_parameter/#function-parameter)**(const json & j, size_t size)<br>Constructs a parameter based on the given JSON object.  |
| | **[operator T](/doxygen/Classes/classsam_1_1_parameter/#function-operator-t)**()<br>Returns the _first_ element of the array.  |
| [Parameter](/doxygen/Classes/classsam_1_1_parameter/)< T > & | **[operator()](/doxygen/Classes/classsam_1_1_parameter/#function-operator())**()<br>Randomizes and returns the save [Parameter](/doxygen/Classes/classsam_1_1_parameter/).  |
| bool | **[isDist](/doxygen/Classes/classsam_1_1_parameter/#function-isdist)**()<br>Returns true if a distribution is assigned to the [Parameter](/doxygen/Classes/classsam_1_1_parameter/).  |

## Detailed Description

```cpp
template <typename T >
class sam::Parameter;
```

An abstract representation of a random variable parameter. 

**Template Parameters**: 

  * **T** Type of the parameter 


**Attention**: Parameter<T> is inherited from arma::Row<T>. This is quite useful and essential because I can pass it around easily, and use all the overloaded operators of the arma::Row<T>

This is designed to account for those setting parameters that can be configured in either of the following ways:



* An array of size _n_, with similar values
* An array of size _n_, with different values
* An array of size _n_, with values drawn from a distribution. This is the case where [Parameter](/doxygen/Classes/classsam_1_1_parameter/) can loosely resemble a random variable.

## Public Functions Documentation

### function Parameter

```cpp
inline Parameter()
```


### function Parameter

```cpp
inline explicit Parameter(
    const arma::Row< T > & X
)
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

Constructs a parameter based on the given JSON object. 

**Parameters**: 

  * **j** The configuration of the parameter 
  * **size** The size of the array


**Template Parameters**: 

  * **T** The type of the [Parameter](/doxygen/Classes/classsam_1_1_parameter/), a.k.a, the type of armadillo vector 


This constructs **and** initializes the [Parameter](/doxygen/Classes/classsam_1_1_parameter/) object based on the given JSON object.


### function operator T

```cpp
inline explicit operator T()
```

Returns the _first_ element of the array. 

**Todo**: Implement a copy constructor 

### function operator()

```cpp
inline Parameter< T > & operator()()
```

Randomizes and returns the save [Parameter](/doxygen/Classes/classsam_1_1_parameter/). 

### function isDist

```cpp
inline bool isDist()
```

Returns true if a distribution is assigned to the [Parameter](/doxygen/Classes/classsam_1_1_parameter/). 

-------------------------------

Updated on 29 June 2021 at 16:13:46 CEST