---
title: sam::Policy
summary: Implementation of the Policy class. 

---

# sam::Policy

**Module:** **[Policy-related Modules](/doxygen/Modules/group___policies/)**



Implementation of the [Policy]() class.  [More...](#detailed-description)


`#include <Policy.h>`

## Public Functions

|                | Name           |
| -------------- | -------------- |
| | **[Policy](/doxygen/Classes/structsam_1_1_policy/#function-policy)**() =default |
| | **[Policy](/doxygen/Classes/structsam_1_1_policy/#function-policy)**(const std::string & p_def, sol::state & lua)<br>Creates a policy, and registers it to the available lua state.  |
| template <typename ForwardIt \> <br>std::optional< std::pair< ForwardIt, ForwardIt > > | **[operator()](/doxygen/Classes/structsam_1_1_policy/#function-operator())**(ForwardIt begin, ForwardIt end)<br>Filters the range based on the given policy.  |
| bool | **[operator()](/doxygen/Classes/structsam_1_1_policy/#function-operator())**(const [Submission](/doxygen/Classes/classsam_1_1_submission/) & sub) const<br>Returns the result of applying the policy on a submission.  |
| bool | **[operator()](/doxygen/Classes/structsam_1_1_policy/#function-operator())**(const [DependentVariable](/doxygen/Classes/classsam_1_1_dependent_variable/) & dv) const<br>Returns the result of applying the policy on a dependent variable.  |
| bool | **[operator()](/doxygen/Classes/structsam_1_1_policy/#function-operator())**([DependentVariable](/doxygen/Classes/classsam_1_1_dependent_variable/) & dv) const |

## Public Attributes

|                | Name           |
| -------------- | -------------- |
| [PolicyType](/doxygen/Modules/group___policies/#enum-policytype) | **[type](/doxygen/Classes/structsam_1_1_policy/#variable-type)**  |
| PolicyDefinition | **[def](/doxygen/Classes/structsam_1_1_policy/#variable-def)**  |
| sol::function | **[func](/doxygen/Classes/structsam_1_1_policy/#variable-func)**  |

## Detailed Description

```cpp
struct sam::Policy;
```

Implementation of the [Policy]() class. 

A policy is a logical rule that it's being applied on an experiment, submission, or a set of submissions. A policy can be used to perform two type of operation on either of the mentioned data structures, selection or decision.



* To check whether a submission, a dependent variable satisfies a given [Policy](/doxygen/Classes/structsam_1_1_policy/), you must use the appropriate call operator in the form of `bool operator()`.
* To filter a list of submissions or dependent variables of the experiment based on the given [Policy](/doxygen/Classes/structsam_1_1_policy/), you must use the iterator-based operator. 

## Public Functions Documentation

### function Policy

```cpp
Policy() =default
```


### function Policy

```cpp
Policy(
    const std::string & p_def,
    sol::state & lua
)
```

Creates a policy, and registers it to the available lua state. 

**Parameters**: 

  * **p_def** The definition 
  * **lua** The lua state 


**Attention**: Since everything is happening via text processing, [Policy](/doxygen/Classes/structsam_1_1_policy/) is quite sensitive to the function definition and it rejects anythings with slightest of mistake in its definition.

This mostly performs some string search, and decided what type of function has been given as the input. Then, it uses a lua function template to construct the appropriate function definition. Finally, it registers the function to the given lua state.


### function operator()

```cpp
template <typename ForwardIt >
std::optional< std::pair< ForwardIt, ForwardIt > > operator()(
    ForwardIt begin,
    ForwardIt end
)
```

Filters the range based on the given policy. 

**Parameters**: 

  * **begin** The begin 
  * **end** The end


**Template Parameters**: 

  * **ForwardIt** This usually accepts [Submission](/doxygen/Classes/classsam_1_1_submission/)'s ForwardIt


**Return**: Return a tuple containing three variables. 

**Attention**: You can only use this on [DependentVariable](/doxygen/Classes/classsam_1_1_dependent_variable/) and [Submission](/doxygen/Classes/classsam_1_1_submission/) objects, since these are the two classes that are registered as lua usertype.

This applies the current policy on a range of values, and returns a subset of the range if it finds anything. If not, it will return an empty optional.


Shuffling the array and setting the end pointer to the first time, this basically mimic the process of selecting a random element from the list.


### function operator()

```cpp
inline bool operator()(
    const Submission & sub
) const
```

Returns the result of applying the policy on a submission. 

### function operator()

```cpp
inline bool operator()(
    const DependentVariable & dv
) const
```

Returns the result of applying the policy on a dependent variable. 

### function operator()

```cpp
inline bool operator()(
    DependentVariable & dv
) const
```


## Public Attributes Documentation

### variable type

```cpp
PolicyType type;
```


### variable def

```cpp
PolicyDefinition def;
```


### variable func

```cpp
sol::function func;
```


-------------------------------

Updated on  7 May 2021 at 14:51:32 CEST