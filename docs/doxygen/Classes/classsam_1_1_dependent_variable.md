---
title: sam::DependentVariable
summary: Declaration of DependentVariable class. 

---

# sam::DependentVariable



Declaration of [DependentVariable]() class.  [More...](#detailed-description)


`#include <DependentVariable.h>`

## Public Functions

|                | Name           |
| -------------- | -------------- |
| bool | **[isModified](/doxygen/Classes/classsam_1_1_dependent_variable/#function-ismodified)**() const |
| bool | **[isHacked](/doxygen/Classes/classsam_1_1_dependent_variable/#function-ishacked)**() const |
| bool | **[isCandidate](/doxygen/Classes/classsam_1_1_dependent_variable/#function-iscandidate)**() const |
| auto | **[begin](/doxygen/Classes/classsam_1_1_dependent_variable/#function-begin)**() |
| auto | **[end](/doxygen/Classes/classsam_1_1_dependent_variable/#function-end)**() |
| float & | **[operator[]](/doxygen/Classes/classsam_1_1_dependent_variable/#function-operator[])**(std::size_t idx) |
| const float & | **[operator[]](/doxygen/Classes/classsam_1_1_dependent_variable/#function-operator[])**(std::size_t idx) const |
| | **[DependentVariable](/doxygen/Classes/classsam_1_1_dependent_variable/#function-dependentvariable)**() =default |
| | **[DependentVariable](/doxygen/Classes/classsam_1_1_dependent_variable/#function-dependentvariable)**(const arma::Row< float > & data) |
| void | **[setHackedStatus](/doxygen/Classes/classsam_1_1_dependent_variable/#function-sethackedstatus)**(const bool status)<br>Sets the hacking status.  |
| void | **[setCandidateStatus](/doxygen/Classes/classsam_1_1_dependent_variable/#function-setcandidatestatus)**(const bool status)<br>Sets the candidacy status.  |
| arma::Row< float > & | **[measurements](/doxygen/Classes/classsam_1_1_dependent_variable/#function-measurements)**()<br>Getter / Setter.  |
| const arma::Row< float > & | **[measurements](/doxygen/Classes/classsam_1_1_dependent_variable/#function-measurements)**() const |
| void | **[setMeasurements](/doxygen/Classes/classsam_1_1_dependent_variable/#function-setmeasurements)**(const arma::Row< float > & meas)<br>Sets the raw measurements values.  |
| void | **[addNewMeasurements](/doxygen/Classes/classsam_1_1_dependent_variable/#function-addnewmeasurements)**(const arma::Row< float > & new_meas)<br>Adds new measurements to the currently available data.  |
| void | **[removeMeasurements](/doxygen/Classes/classsam_1_1_dependent_variable/#function-removemeasurements)**(const arma::uvec & idxs)<br>Removes the measurements by their indices.  |
| void | **[updateStats](/doxygen/Classes/classsam_1_1_dependent_variable/#function-updatestats)**()<br>Updates the descriptive statistics of the dependent variable.  |
| void | **[clear](/doxygen/Classes/classsam_1_1_dependent_variable/#function-clear)**()<br>Reset the internal state of the dependent variable.  |
| std::vector< std::string > | **[Columns](/doxygen/Classes/classsam_1_1_dependent_variable/#function-columns)**()<br>List the name of all avaliable variables.  |

## Public Attributes

|                | Name           |
| -------------- | -------------- |
| float | **[true_nobs_](/doxygen/Classes/classsam_1_1_dependent_variable/#variable-true_nobs_)**  |
| float | **[true_mean_](/doxygen/Classes/classsam_1_1_dependent_variable/#variable-true_mean_)**  |
| float | **[true_std_](/doxygen/Classes/classsam_1_1_dependent_variable/#variable-true_std_)**  |
| int | **[nobs_](/doxygen/Classes/classsam_1_1_dependent_variable/#variable-nobs_)**  |
| float | **[mean_](/doxygen/Classes/classsam_1_1_dependent_variable/#variable-mean_)**  |
| float | **[var_](/doxygen/Classes/classsam_1_1_dependent_variable/#variable-var_)**  |
| float | **[stddev_](/doxygen/Classes/classsam_1_1_dependent_variable/#variable-stddev_)**  |
| float | **[sei_](/doxygen/Classes/classsam_1_1_dependent_variable/#variable-sei_)**  |
| float | **[stats_](/doxygen/Classes/classsam_1_1_dependent_variable/#variable-stats_)**  |
| float | **[pvalue_](/doxygen/Classes/classsam_1_1_dependent_variable/#variable-pvalue_)**  |
| bool | **[sig_](/doxygen/Classes/classsam_1_1_dependent_variable/#variable-sig_)**  |
| float | **[effect_](/doxygen/Classes/classsam_1_1_dependent_variable/#variable-effect_)**  |
| float | **[var_effect_](/doxygen/Classes/classsam_1_1_dependent_variable/#variable-var_effect_)**  |
| float | **[se_effect_](/doxygen/Classes/classsam_1_1_dependent_variable/#variable-se_effect_)**  |
| int | **[eff_side_](/doxygen/Classes/classsam_1_1_dependent_variable/#variable-eff_side_)**  |
| bool | **[is_hacked_](/doxygen/Classes/classsam_1_1_dependent_variable/#variable-is_hacked_)**  |
| int | **[n_added_obs](/doxygen/Classes/classsam_1_1_dependent_variable/#variable-n_added_obs)**  |
| int | **[n_removed_obs](/doxygen/Classes/classsam_1_1_dependent_variable/#variable-n_removed_obs)**  |
| int | **[id_](/doxygen/Classes/classsam_1_1_dependent_variable/#variable-id_)**  |
| bool | **[is_candidate_](/doxygen/Classes/classsam_1_1_dependent_variable/#variable-is_candidate_)** <br>[Submission]() Meta Data.  |

## Detailed Description

```cpp
class sam::DependentVariable;
```

Declaration of [DependentVariable]() class. 

This class is an abstract representation of a dependant variable. It contains raw data, test statistics, and effect size measurements as well as some meta data for keeping track of true nobs, mean, and std values. 

## Public Functions Documentation

### function isModified

```cpp
inline bool isModified() const
```


### function isHacked

```cpp
inline bool isHacked() const
```


### function isCandidate

```cpp
inline bool isCandidate() const
```


### function begin

```cpp
inline auto begin()
```


### function end

```cpp
inline auto end()
```


### function operator[]

```cpp
inline float & operator[](
    std::size_t idx
)
```


### function operator[]

```cpp
inline const float & operator[](
    std::size_t idx
) const
```


### function DependentVariable

```cpp
DependentVariable() =default
```


### function DependentVariable

```cpp
inline explicit DependentVariable(
    const arma::Row< float > & data
)
```


### function setHackedStatus

```cpp
inline void setHackedStatus(
    const bool status
)
```

Sets the hacking status. 

### function setCandidateStatus

```cpp
inline void setCandidateStatus(
    const bool status
)
```

Sets the candidacy status. 

### function measurements

```cpp
inline arma::Row< float > & measurements()
```

Getter / Setter. 

### function measurements

```cpp
inline const arma::Row< float > & measurements() const
```


### function setMeasurements

```cpp
inline void setMeasurements(
    const arma::Row< float > & meas
)
```

Sets the raw measurements values. 

### function addNewMeasurements

```cpp
inline void addNewMeasurements(
    const arma::Row< float > & new_meas
)
```

Adds new measurements to the currently available data. 

### function removeMeasurements

```cpp
inline void removeMeasurements(
    const arma::uvec & idxs
)
```

Removes the measurements by their indices. 

### function updateStats

```cpp
void updateStats()
```

Updates the descriptive statistics of the dependent variable. 

This updates all the descriptive statistics of the dependent variable. 


### function clear

```cpp
void clear()
```

Reset the internal state of the dependent variable. 

This clears and resets the internal state of the class. 


### function Columns

```cpp
static std::vector< std::string > Columns()
```

List the name of all avaliable variables. 

This is being used by the [PersistenceManager::Writer](/doxygen/Classes/classsam_1_1_persistence_manager_1_1_writer/) to determine the name and number of columns 


## Public Attributes Documentation

### variable true_nobs_

```cpp
float true_nobs_ {0};
```


### variable true_mean_

```cpp
float true_mean_ {0};
```


### variable true_std_

```cpp
float true_std_ {0};
```


### variable nobs_

```cpp
int nobs_ {0};
```


### variable mean_

```cpp
float mean_ {0};
```


### variable var_

```cpp
float var_ {0};
```


### variable stddev_

```cpp
float stddev_ {0};
```


### variable sei_

```cpp
float sei_ {0};
```


### variable stats_

```cpp
float stats_ {0};
```


### variable pvalue_

```cpp
float pvalue_ {0};
```


### variable sig_

```cpp
bool sig_ {false};
```


### variable effect_

```cpp
float effect_ {0};
```


### variable var_effect_

```cpp
float var_effect_ {0};
```


### variable se_effect_

```cpp
float se_effect_ {0};
```


### variable eff_side_

```cpp
int eff_side_ {0};
```


### variable is_hacked_

```cpp
bool is_hacked_ {false};
```


### variable n_added_obs

```cpp
int n_added_obs {0};
```


### variable n_removed_obs

```cpp
int n_removed_obs {0};
```


### variable id_

```cpp
int id_;
```


Dependent variable's ID. This is being used by [Policy](/doxygen/Classes/structsam_1_1_policy/) to perform some searches 


### variable is_candidate_

```cpp
bool is_candidate_ {false};
```

[Submission]() Meta Data. 

-------------------------------

Updated on 29 June 2021 at 16:13:46 CEST