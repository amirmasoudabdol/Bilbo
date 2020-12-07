---
title: sam::GRMDataStrategy::Parameters


---

# sam::GRMDataStrategy::Parameters



















## Public Functions

|                | Name           |
| -------------- | -------------- |
|  | **[Parameters](/doxygen/Classes/structsam_1_1_g_r_m_data_strategy_1_1_parameters/#function-parameters)**() =default  |


## Public Attributes

|                | Name           |
| -------------- | -------------- |
| DataModel | **[name](/doxygen/Classes/structsam_1_1_g_r_m_data_strategy_1_1_parameters/#variable-name)**  |
| int | **[n_dims](/doxygen/Classes/structsam_1_1_g_r_m_data_strategy_1_1_parameters/#variable-n_dims)**  |
| int | **[n_items](/doxygen/Classes/structsam_1_1_g_r_m_data_strategy_1_1_parameters/#variable-n_items)**  |
| int | **[n_categories](/doxygen/Classes/structsam_1_1_g_r_m_data_strategy_1_1_parameters/#variable-n_categories)**  |
| std::string | **[response_function](/doxygen/Classes/structsam_1_1_g_r_m_data_strategy_1_1_parameters/#variable-response_function)**  |
| std::optional< MultivariateDistribution > | **[m_diff_dist](/doxygen/Classes/structsam_1_1_g_r_m_data_strategy_1_1_parameters/#variable-m_diff_dist)**  |
| std::optional< MultivariateDistribution > | **[m_abil_dist](/doxygen/Classes/structsam_1_1_g_r_m_data_strategy_1_1_parameters/#variable-m_abil_dist)**  |
| std::optional< std::vector< Distribution > > | **[diff_dists](/doxygen/Classes/structsam_1_1_g_r_m_data_strategy_1_1_parameters/#variable-diff_dists)**  |
| std::optional< std::vector< Distribution > > | **[abil_dists](/doxygen/Classes/structsam_1_1_g_r_m_data_strategy_1_1_parameters/#variable-abil_dists)**  |














## Public Functions Documentation

### function Parameters

```cpp
Parameters() =default
```































## Public Attributes Documentation

### variable name

```cpp
DataModel name {DataModel::GradedResponseModel};
```





























### variable n_dims

```cpp
int n_dims;
```





























### variable n_items

```cpp
int n_items;
```





























### variable n_categories

```cpp
int n_categories;
```





























### variable response_function

```cpp
std::string response_function {"Rasch"};
```





























### variable m_diff_dist

```cpp
std::optional< MultivariateDistribution > m_diff_dist;
```





























### variable m_abil_dist

```cpp
std::optional< MultivariateDistribution > m_abil_dist;
```





























### variable diff_dists

```cpp
std::optional< std::vector< Distribution > > diff_dists;
```





























### variable abil_dists

```cpp
std::optional< std::vector< Distribution > > abil_dists;
```

































-------------------------------

Updated on  7 December 2020 at 13:20:09 CET