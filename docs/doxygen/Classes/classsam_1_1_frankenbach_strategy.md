---
title: sam::FrankenbachStrategy


---

# sam::FrankenbachStrategy








Inherits from [sam::HackingProbabilityStrategy](/doxygen/Classes/classsam_1_1_hacking_probability_strategy/)



## Public Classes

|                | Name           |
| -------------- | -------------- |
| struct | **[Parameters](/doxygen/Classes/structsam_1_1_frankenbach_strategy_1_1_parameters/)**  |








## Public Functions

|                | Name           |
| -------------- | -------------- |
|  | **[FrankenbachStrategy](/doxygen/Classes/classsam_1_1_frankenbach_strategy/#function-frankenbachstrategy)**() =default  |
|  | **[FrankenbachStrategy](/doxygen/Classes/classsam_1_1_frankenbach_strategy/#function-frankenbachstrategy)**([Parameters](/doxygen/Classes/structsam_1_1_frankenbach_strategy_1_1_parameters/) & p)  |
| virtual double | **[estimate](/doxygen/Classes/classsam_1_1_frankenbach_strategy/#function-estimate)**([Experiment](/doxygen/Classes/classsam_1_1_experiment/) * experiment) override  |


## Public Attributes

|                | Name           |
| -------------- | -------------- |
| [Parameters](/doxygen/Classes/structsam_1_1_frankenbach_strategy_1_1_parameters/) | **[params](/doxygen/Classes/classsam_1_1_frankenbach_strategy/#variable-params)**  |




## Additional inherited members










**Public Functions inherited from [sam::HackingProbabilityStrategy](/doxygen/Classes/classsam_1_1_hacking_probability_strategy/)**

|                | Name           |
| -------------- | -------------- |
| virtual  | **[~HackingProbabilityStrategy](/doxygen/Classes/classsam_1_1_hacking_probability_strategy/#function-~hackingprobabilitystrategy)**() =0  |
|  | **[operator double](/doxygen/Classes/classsam_1_1_hacking_probability_strategy/#function-operator-double)**()  |
|  | **[operator arma::rowvec](/doxygen/Classes/classsam_1_1_hacking_probability_strategy/#function-operator-armarowvec)**()  |
| std::unique_ptr< [HackingProbabilityStrategy](/doxygen/Classes/classsam_1_1_hacking_probability_strategy/) > | **[build](/doxygen/Classes/classsam_1_1_hacking_probability_strategy/#function-build)**(json & config)  |


**Public Attributes inherited from [sam::HackingProbabilityStrategy](/doxygen/Classes/classsam_1_1_hacking_probability_strategy/)**

|                | Name           |
| -------------- | -------------- |
| double | **[prob](/doxygen/Classes/classsam_1_1_hacking_probability_strategy/#variable-prob)**  |
| arma::rowvec | **[probabilities](/doxygen/Classes/classsam_1_1_hacking_probability_strategy/#variable-probabilities)**  |













## Public Functions Documentation

### function FrankenbachStrategy

```cpp
FrankenbachStrategy() =default
```





























### function FrankenbachStrategy

```cpp
inline FrankenbachStrategy(
    Parameters & p
)
```





























### function estimate

```cpp
virtual double estimate(
    Experiment * experiment
) override
```


























**Reimplements**: [sam::HackingProbabilityStrategy::estimate](/doxygen/Classes/classsam_1_1_hacking_probability_strategy/#function-estimate)



We have something in the middle now, so, we are calculating based on the p-value we check for significance, if sig, then we return 0. else, then we assign a value

I have a feeling this is a very inefficneit implementation

If the hacking probablity is 1, then everything in this range is going to be hacked, a.k.a, hp = 1; Update: I think I had this wrong previously, where I assing the probability to everything, while it should only be assigned to those studies that are passing the effect test in the first place

TodoRemember that you should consider some option here. At the moment, I'm returning the maximum of all probabilities, but that's not neceassirly the best things to do, also, it works just fine in Frankenbach simulation because they have only one one outcome anyway 



## Public Attributes Documentation

### variable params

```cpp
Parameters params;
```

































-------------------------------

Updated on  2 December 2020 at 14:48:53 CET