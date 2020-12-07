---
title: sam::Group
summary: Declartiong of Group class.  

---

# sam::Group




Declartiong of [Group]() class.  [More...](#detailed-description)


`#include <Group.h>`













## Public Functions

|                | Name           |
| -------------- | -------------- |
| std::vector< std::string > | **[Columns](/doxygen/Classes/classsam_1_1_group/#function-columns)**()  |
|  | **[Group](/doxygen/Classes/classsam_1_1_group/#function-group)**()  |
|  | **[Group](/doxygen/Classes/classsam_1_1_group/#function-group)**(int id_, GroupType type_)  |
|  | **[Group](/doxygen/Classes/classsam_1_1_group/#function-group)**(arma::Row< double > & data)  |
| arma::Row< double > & | **[measurements](/doxygen/Classes/classsam_1_1_group/#function-measurements)**() <br>Getter / Setter.  |
| const arma::Row< double > & | **[measurements](/doxygen/Classes/classsam_1_1_group/#function-measurements)**() const  |
| void | **[set_measurements](/doxygen/Classes/classsam_1_1_group/#function-set_measurements)**(const arma::Row< double > meas)  |
| void | **[add_measurements](/doxygen/Classes/classsam_1_1_group/#function-add_measurements)**(const arma::Row< double > new_meas)  |
| void | **[del_measurements](/doxygen/Classes/classsam_1_1_group/#function-del_measurements)**(const arma::uvec & idxs)  |
| auto | **[begin](/doxygen/Classes/classsam_1_1_group/#function-begin)**()  |
| auto | **[end](/doxygen/Classes/classsam_1_1_group/#function-end)**()  |
|  | **[operator arma::Row< double >](/doxygen/Classes/classsam_1_1_group/#function-operator-armarow<-double->)**()  |
| void | **[updateStats](/doxygen/Classes/classsam_1_1_group/#function-updatestats)**()  |
| void | **[testAgaist](/doxygen/Classes/classsam_1_1_group/#function-testagaist)**(const [Group](/doxygen/Classes/classsam_1_1_group/) & other_group, [TestStrategy](/doxygen/Classes/classsam_1_1_test_strategy/) & test_strategy)  |
| void | **[effectComparedTo](/doxygen/Classes/classsam_1_1_group/#function-effectcomparedto)**(const [Group](/doxygen/Classes/classsam_1_1_group/) & other_group, [EffectStrategy](/doxygen/Classes/classsam_1_1_effect_strategy/) & effect_strategy)  |
| void | **[clear](/doxygen/Classes/classsam_1_1_group/#function-clear)**()  |


## Public Attributes

|                | Name           |
| -------------- | -------------- |
| int | **[id_](/doxygen/Classes/classsam_1_1_group/#variable-id_)**  |
| GroupType | **[gtype](/doxygen/Classes/classsam_1_1_group/#variable-gtype)**  |
| std::optional< double > | **[true_nobs_](/doxygen/Classes/classsam_1_1_group/#variable-true_nobs_)**  |
| std::optional< double > | **[true_mean_](/doxygen/Classes/classsam_1_1_group/#variable-true_mean_)**  |
| std::optional< double > | **[true_std_](/doxygen/Classes/classsam_1_1_group/#variable-true_std_)**  |
| int | **[nobs_](/doxygen/Classes/classsam_1_1_group/#variable-nobs_)** <br>&mdash; Descriptive statistics  |
| double | **[mean_](/doxygen/Classes/classsam_1_1_group/#variable-mean_)**  |
| double | **[var_](/doxygen/Classes/classsam_1_1_group/#variable-var_)**  |
| double | **[stddev_](/doxygen/Classes/classsam_1_1_group/#variable-stddev_)**  |
| double | **[sei_](/doxygen/Classes/classsam_1_1_group/#variable-sei_)**  |
| bool | **[is_stats_up_to_date](/doxygen/Classes/classsam_1_1_group/#variable-is_stats_up_to_date)**  |
| double | **[stats_](/doxygen/Classes/classsam_1_1_group/#variable-stats_)**  |
| double | **[pvalue_](/doxygen/Classes/classsam_1_1_group/#variable-pvalue_)**  |
| double | **[effect_](/doxygen/Classes/classsam_1_1_group/#variable-effect_)**  |
| double | **[var_effect_](/doxygen/Classes/classsam_1_1_group/#variable-var_effect_)**  |
| double | **[se_effect_](/doxygen/Classes/classsam_1_1_group/#variable-se_effect_)**  |
| int | **[eff_side_](/doxygen/Classes/classsam_1_1_group/#variable-eff_side_)**  |
| bool | **[sig_](/doxygen/Classes/classsam_1_1_group/#variable-sig_)**  |
| bool | **[is_test_updated_](/doxygen/Classes/classsam_1_1_group/#variable-is_test_updated_)**  |
| bool | **[is_hacked_](/doxygen/Classes/classsam_1_1_group/#variable-is_hacked_)** <br>&mdash; Hacking Meta  |
| std::vector< HackingMethod > | **[hacking_history_](/doxygen/Classes/classsam_1_1_group/#variable-hacking_history_)**  |
| int | **[n_added_obs](/doxygen/Classes/classsam_1_1_group/#variable-n_added_obs)**  |
| int | **[n_removed_obs](/doxygen/Classes/classsam_1_1_group/#variable-n_removed_obs)**  |


## Friends

|                | Name           |
| -------------- | -------------- |
| OStream & | **[operator<<](/doxygen/Classes/classsam_1_1_group/#friend-operator<<)**(OStream & os, const [Group](/doxygen/Classes/classsam_1_1_group/) & data)  |




## Detailed Description

```cpp
class sam::Group;
```

Declartiong of [Group]() class. 


























The [Group](/doxygen/Classes/classsam_1_1_group/) class is an abstract representation of a dependant variable 









## Public Functions Documentation

### function Columns

```cpp
static std::vector< std::string > Columns()
```





























### function Group

```cpp
inline Group()
```





























### function Group

```cpp
inline Group(
    int id_,
    GroupType type_
)
```





























### function Group

```cpp
inline Group(
    arma::Row< double > & data
)
```





























### function measurements

```cpp
inline arma::Row< double > & measurements()
```

Getter / Setter. 




























### function measurements

```cpp
inline const arma::Row< double > & measurements() const
```





























### function set_measurements

```cpp
inline void set_measurements(
    const arma::Row< double > meas
)
```





























### function add_measurements

```cpp
inline void add_measurements(
    const arma::Row< double > new_meas
)
```





























### function del_measurements

```cpp
inline void del_measurements(
    const arma::uvec & idxs
)
```





























### function begin

```cpp
inline auto begin()
```





























### function end

```cpp
inline auto end()
```





























### function operator arma::Row< double >

```cpp
operator arma::Row< double >()
```





























### function updateStats

```cpp
void updateStats()
```




























TodoBring this back, I'm removing this because group is not being notified with some of the changes, and this leads to SAM not updating the statistics, i.e., the type of changes that Falsifying Data will cause 

### function testAgaist

```cpp
void testAgaist(
    const Group & other_group,
    TestStrategy & test_strategy
)
```





























### function effectComparedTo

```cpp
void effectComparedTo(
    const Group & other_group,
    EffectStrategy & effect_strategy
)
```





























### function clear

```cpp
void clear()
```































## Public Attributes Documentation

### variable id_

```cpp
int id_;
```





























### variable gtype

```cpp
GroupType gtype;
```





























### variable true_nobs_

```cpp
std::optional< double > true_nobs_ {0};
```



























&mdash; Distribution/Population Parameters These can be their own type, and determined by the DataStrategies 


### variable true_mean_

```cpp
std::optional< double > true_mean_ {0};
```





























### variable true_std_

```cpp
std::optional< double > true_std_ {0};
```





























### variable nobs_

```cpp
int nobs_ {0};
```

&mdash; Descriptive statistics 




























### variable mean_

```cpp
double mean_ {0};
```





























### variable var_

```cpp
double var_ {0};
```





























### variable stddev_

```cpp
double stddev_ {0};
```





























### variable sei_

```cpp
double sei_ {0};
```





























### variable is_stats_up_to_date

```cpp
bool is_stats_up_to_date {false};
```





























### variable stats_

```cpp
double stats_ {0};
```



























&mdash; Test statistics ... These can be their own type, and determined by the TestStrategies 


### variable pvalue_

```cpp
double pvalue_ {0};
```





























### variable effect_

```cpp
double effect_ {0};
```





























### variable var_effect_

```cpp
double var_effect_ {0};
```





























### variable se_effect_

```cpp
double se_effect_ {0};
```





























### variable eff_side_

```cpp
int eff_side_ {0};
```





























### variable sig_

```cpp
bool sig_ {false};
```





























### variable is_test_updated_

```cpp
bool is_test_updated_ {false};
```





























### variable is_hacked_

```cpp
bool is_hacked_ {false};
```

&mdash; Hacking Meta 




























### variable hacking_history_

```cpp
std::vector< HackingMethod > hacking_history_;
```





























### variable n_added_obs

```cpp
int n_added_obs {0};
```





























### variable n_removed_obs

```cpp
int n_removed_obs {0};
```































## Friends

### friend operator<<

```cpp
friend OStream & operator<<(
    OStream & os,
    const Group & data
);
```































-------------------------------

Updated on  7 December 2020 at 13:20:07 CET