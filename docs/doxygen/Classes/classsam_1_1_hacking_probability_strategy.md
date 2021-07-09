---
title: sam::HackingProbabilityStrategy

---

# sam::HackingProbabilityStrategy



Inherited by [sam::FrankenbachStrategy](/doxygen/Classes/classsam_1_1_frankenbach_strategy/)

## Public Functions

|                | Name           |
| -------------- | -------------- |
| virtual | **[~HackingProbabilityStrategy](/doxygen/Classes/classsam_1_1_hacking_probability_strategy/#function-~hackingprobabilitystrategy)**() =0 |
| virtual float | **[estimate](/doxygen/Classes/classsam_1_1_hacking_probability_strategy/#function-estimate)**([Experiment](/doxygen/Classes/classsam_1_1_experiment/) * experiment) =0 |
| | **[operator float](/doxygen/Classes/classsam_1_1_hacking_probability_strategy/#function-operator-float)**() |
| std::unique_ptr< [HackingProbabilityStrategy](/doxygen/Classes/classsam_1_1_hacking_probability_strategy/) > | **[build](/doxygen/Classes/classsam_1_1_hacking_probability_strategy/#function-build)**(json & config) |

## Public Attributes

|                | Name           |
| -------------- | -------------- |
| float | **[prob](/doxygen/Classes/classsam_1_1_hacking_probability_strategy/#variable-prob)**  |
| arma::Row< float > | **[probabilities](/doxygen/Classes/classsam_1_1_hacking_probability_strategy/#variable-probabilities)**  |

## Public Functions Documentation

### function ~HackingProbabilityStrategy

```cpp
virtual ~HackingProbabilityStrategy() =0
```


### function estimate

```cpp
virtual float estimate(
    Experiment * experiment
) =0
```


**Reimplemented by**: [sam::FrankenbachStrategy::estimate](/doxygen/Classes/classsam_1_1_frankenbach_strategy/#function-estimate)


### function operator float

```cpp
inline operator float()
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
float prob;
```


### variable probabilities

```cpp
arma::Row< float > probabilities;
```


-------------------------------

Updated on 29 June 2021 at 16:13:46 CEST