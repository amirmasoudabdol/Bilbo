---
title: sam::LinearModelStrategy::Parameters
summary: Parameters of LinearModelStrategy. 

---

# sam::LinearModelStrategy::Parameters



[Parameters]() of [LinearModelStrategy](/doxygen/Classes/classsam_1_1_linear_model_strategy/). 
`#include <DataStrategy.h>`

## Public Functions

|                | Name           |
| -------------- | -------------- |
| | **[Parameters](/doxygen/Classes/structsam_1_1_linear_model_strategy_1_1_parameters/#function-parameters)**() =default |

## Public Attributes

|                | Name           |
| -------------- | -------------- |
| std::optional< std::vector< UnivariateDistribution > > | **[meas_dists](/doxygen/Classes/structsam_1_1_linear_model_strategy_1_1_parameters/#variable-meas_dists)**  |
| std::optional< MultivariateDistribution > | **[m_meas_dist](/doxygen/Classes/structsam_1_1_linear_model_strategy_1_1_parameters/#variable-m_meas_dist)**  |
| std::optional< std::vector< UnivariateDistribution > > | **[erro_dists](/doxygen/Classes/structsam_1_1_linear_model_strategy_1_1_parameters/#variable-erro_dists)**  |
| std::optional< MultivariateDistribution > | **[m_erro_dist](/doxygen/Classes/structsam_1_1_linear_model_strategy_1_1_parameters/#variable-m_erro_dist)**  |
| DataModel | **[name](/doxygen/Classes/structsam_1_1_linear_model_strategy_1_1_parameters/#variable-name)**  |

## Public Functions Documentation

### function Parameters

```cpp
Parameters() =default
```


## Public Attributes Documentation

### variable meas_dists

```cpp
std::optional< std::vector< UnivariateDistribution > > meas_dists;
```


Distributions of main effects 


### variable m_meas_dist

```cpp
std::optional< MultivariateDistribution > m_meas_dist;
```


### variable erro_dists

```cpp
std::optional< std::vector< UnivariateDistribution > > erro_dists;
```


Distributions of error. 


### variable m_erro_dist

```cpp
std::optional< MultivariateDistribution > m_erro_dist;
```


### variable name

```cpp
DataModel name {DataModel::LinearModel};
```


-------------------------------

Updated on  7 June 2021 at 12:00:21 CEST