---
title: sam::GRMDataStrategy::Parameters

---

# sam::GRMDataStrategy::Parameters



## Public Functions

|                | Name           |
| -------------- | -------------- |
| | **[Parameters](/doxygen/Classes/structsam_1_1_g_r_m_data_strategy_1_1_parameters/#function-parameters)**() =default |

## Public Attributes

|                | Name           |
| -------------- | -------------- |
| DataModel | **[name](/doxygen/Classes/structsam_1_1_g_r_m_data_strategy_1_1_parameters/#variable-name)**  |
| int | **[n_items](/doxygen/Classes/structsam_1_1_g_r_m_data_strategy_1_1_parameters/#variable-n_items)** <br>Number of items.  |
| int | **[n_categories](/doxygen/Classes/structsam_1_1_g_r_m_data_strategy_1_1_parameters/#variable-n_categories)** <br>Number of categories.  |
| std::string | **[response_function](/doxygen/Classes/structsam_1_1_g_r_m_data_strategy_1_1_parameters/#variable-response_function)** <br>Indicates the Response Function.  |
| std::optional< MultivariateDistribution > | **[m_diff_dist](/doxygen/Classes/structsam_1_1_g_r_m_data_strategy_1_1_parameters/#variable-m_diff_dist)**  |
| std::optional< MultivariateDistribution > | **[m_abil_dist](/doxygen/Classes/structsam_1_1_g_r_m_data_strategy_1_1_parameters/#variable-m_abil_dist)**  |
| std::optional< std::vector< UnivariateDistribution > > | **[diff_dists](/doxygen/Classes/structsam_1_1_g_r_m_data_strategy_1_1_parameters/#variable-diff_dists)**  |
| std::optional< std::vector< UnivariateDistribution > > | **[abil_dists](/doxygen/Classes/structsam_1_1_g_r_m_data_strategy_1_1_parameters/#variable-abil_dists)**  |

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


### variable n_items

```cpp
int n_items;
```

Number of items. 

### variable n_categories

```cpp
int n_categories;
```

Number of categories. 

### variable response_function

```cpp
std::string response_function {"Rasch"};
```

Indicates the Response Function. 

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
std::optional< std::vector< UnivariateDistribution > > diff_dists;
```


### variable abil_dists

```cpp
std::optional< std::vector< UnivariateDistribution > > abil_dists;
```


-------------------------------

Updated on  7 June 2021 at 12:00:21 CEST