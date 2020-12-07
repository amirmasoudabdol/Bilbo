---
title: sam::LinearModelStrategy::Parameters


---

# sam::LinearModelStrategy::Parameters



















## Public Functions

|                | Name           |
| -------------- | -------------- |
|  | **[Parameters](/doxygen/Classes/structsam_1_1_linear_model_strategy_1_1_parameters/#function-parameters)**() =default  |


## Public Attributes

|                | Name           |
| -------------- | -------------- |
| DataModel | **[name](/doxygen/Classes/structsam_1_1_linear_model_strategy_1_1_parameters/#variable-name)**  |
| std::optional< std::vector< Distribution > > | **[meas_dists](/doxygen/Classes/structsam_1_1_linear_model_strategy_1_1_parameters/#variable-meas_dists)**  |
| std::optional< std::vector< Distribution > > | **[erro_dists](/doxygen/Classes/structsam_1_1_linear_model_strategy_1_1_parameters/#variable-erro_dists)**  |
| std::optional< MultivariateDistribution > | **[m_meas_dist](/doxygen/Classes/structsam_1_1_linear_model_strategy_1_1_parameters/#variable-m_meas_dist)**  |
| std::optional< MultivariateDistribution > | **[m_erro_dist](/doxygen/Classes/structsam_1_1_linear_model_strategy_1_1_parameters/#variable-m_erro_dist)**  |














## Public Functions Documentation

### function Parameters

```cpp
Parameters() =default
```































## Public Attributes Documentation

### variable name

```cpp
DataModel name {DataModel::LinearModel};
```





























### variable meas_dists

```cpp
std::optional< std::vector< Distribution > > meas_dists;
```





























### variable erro_dists

```cpp
std::optional< std::vector< Distribution > > erro_dists;
```





























### variable m_meas_dist

```cpp
std::optional< MultivariateDistribution > m_meas_dist;
```





























### variable m_erro_dist

```cpp
std::optional< MultivariateDistribution > m_erro_dist;
```

































-------------------------------

Updated on  7 December 2020 at 13:20:09 CET