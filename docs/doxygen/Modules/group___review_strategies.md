---
title: Review Strategies

---

# Review Strategies

## Classes

|                | Name           |
| -------------- | -------------- |
| class | **[sam::PolicyBasedSelection](/doxygen/Classes/classsam_1_1_policy_based_selection/)** <br>Policy-based Selection Strategy.  |
| class | **[sam::SignificantSelection](/doxygen/Classes/classsam_1_1_significant_selection/)** <br>Significant-based Selection Strategy.  |
| class | **[sam::RandomSelection](/doxygen/Classes/classsam_1_1_random_selection/)** <br>Random Selection Strategy.  |
| class | **[sam::FreeSelection](/doxygen/Classes/classsam_1_1_free_selection/)** <br>[FreeSelection]() doesn't pose any restriction on the submission and all submissions will be accepted.  |

## Functions

|                | Name           |
| -------------- | -------------- |
| | **[NLOHMANN_JSON_SERIALIZE_ENUM](/doxygen/Modules/group___review_strategies/#function-nlohmann_json_serialize_enum)**(SelectionMethod , {{SelectionMethod::PolicyBasedSelection, "PolicyBasedSelection"}, {SelectionMethod::SignificantSelection, "SignificantSelection"}, {SelectionMethod::RandomSelection, "RandomSelection"}, {SelectionMethod::FreeSelection, "FreeSelection"}} )<br>Abstract class for [Journal](/doxygen/Classes/classsam_1_1_journal/)'s selection strategies.  |


## Functions Documentation

### function NLOHMANN_JSON_SERIALIZE_ENUM

```cpp
NLOHMANN_JSON_SERIALIZE_ENUM(
    SelectionMethod ,
    {{SelectionMethod::PolicyBasedSelection, "PolicyBasedSelection"}, {SelectionMethod::SignificantSelection, "SignificantSelection"}, {SelectionMethod::RandomSelection, "RandomSelection"}, {SelectionMethod::FreeSelection, "FreeSelection"}} 
)
```

Abstract class for [Journal](/doxygen/Classes/classsam_1_1_journal/)'s selection strategies. 



```
        A Journal will decide if a Submission is going to be accepted or
        rejected. This decision can be made based on different criteria
        or formula. A ReviewStrategy provides an interface for
        implementing different selection strategies.
```


Pure destructors of the base class

Lua's state

Selection method's name

Constructs the Review Strategy

Factory method for building a ReviewStrategy

The abstract _review_ method 

```
        It reviews the submissions and decides if it's going to be
        accepted or rejected. When deriving from ReviewStrategy,
        `review` is the main interface and `Journal` relies on its
        output
```

sA reference to a [Submission](/doxygen/Classes/classsam_1_1_submission/)

Returns 'true' if the any of the submissions are going to be accepted.


The abstract _review_ method. 

```
        Like the method above, but this one reviews the entire
        Experiment instead.
```

It's not yet been used anywhere though SAM, but it will eventually replace the submission review method.

exprThe experiment

Returns `true` if the [Experiment](/doxygen/Classes/classsam_1_1_experiment/) is going to be accepted.






-------------------------------

Updated on  7 May 2021 at 14:51:32 CEST