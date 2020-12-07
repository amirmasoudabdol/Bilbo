---
title: sam::HackingProbabilityStrategy


---

# sam::HackingProbabilityStrategy









Inherited by [sam::FrankenbachStrategy](/doxygen/Classes/classsam_1_1_frankenbach_strategy/)










## Public Functions

|                | Name           |
| -------------- | -------------- |
| virtual  | **[~HackingProbabilityStrategy](/doxygen/Classes/classsam_1_1_hacking_probability_strategy/#function-~hackingprobabilitystrategy)**() =0  |
| virtual double | **[estimate](/doxygen/Classes/classsam_1_1_hacking_probability_strategy/#function-estimate)**([Experiment](/doxygen/Classes/classsam_1_1_experiment/) * experiment) =0  |
|  | **[operator double](/doxygen/Classes/classsam_1_1_hacking_probability_strategy/#function-operator-double)**()  |
|  | **[operator arma::rowvec](/doxygen/Classes/classsam_1_1_hacking_probability_strategy/#function-operator-armarowvec)**()  |
| std::unique_ptr< [HackingProbabilityStrategy](/doxygen/Classes/classsam_1_1_hacking_probability_strategy/) > | **[build](/doxygen/Classes/classsam_1_1_hacking_probability_strategy/#function-build)**(json & config)  |


## Public Attributes

|                | Name           |
| -------------- | -------------- |
| double | **[prob](/doxygen/Classes/classsam_1_1_hacking_probability_strategy/#variable-prob)**  |
| arma::rowvec | **[probabilities](/doxygen/Classes/classsam_1_1_hacking_probability_strategy/#variable-probabilities)**  |














## Public Functions Documentation

### function ~HackingProbabilityStrategy

```cpp
virtual ~HackingProbabilityStrategy() =0
```





























### function estimate

```cpp
virtual double estimate(
    Experiment * experiment
) =0
```


























**Reimplemented by**: [sam::FrankenbachStrategy::estimate](/doxygen/Classes/classsam_1_1_frankenbach_strategy/#function-estimate)




### function operator double

```cpp
inline operator double()
```





























### function operator arma::rowvec

```cpp
inline operator arma::rowvec()
```





























### function build

```cpp
static std::unique_ptr< HackingProbabilityStrategy > build(
    json & config
)
```































## Public Attributes Documentation

### variable prob

```cpp
double prob;
```





























### variable probabilities

```cpp
arma::rowvec probabilities;
```

































-------------------------------

Updated on  7 December 2020 at 13:20:07 CET