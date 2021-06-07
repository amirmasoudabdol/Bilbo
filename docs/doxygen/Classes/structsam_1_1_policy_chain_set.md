---
title: sam::PolicyChainSet

---

# sam::PolicyChainSet

**Module:** **[Policy-related Modules](/doxygen/Modules/group___policies/)**



 [More...](#detailed-description)


`#include <Policy.h>`

## Public Functions

|                | Name           |
| -------------- | -------------- |
| [PolicyChain](/doxygen/Classes/structsam_1_1_policy_chain/) & | **[operator[]](/doxygen/Classes/structsam_1_1_policy_chain_set/#function-operator[])**(std::size_t idx) |
| const [PolicyChain](/doxygen/Classes/structsam_1_1_policy_chain/) & | **[operator[]](/doxygen/Classes/structsam_1_1_policy_chain_set/#function-operator[])**(std::size_t idx) const |
| auto | **[begin](/doxygen/Classes/structsam_1_1_policy_chain_set/#function-begin)**() |
| auto | **[cbegin](/doxygen/Classes/structsam_1_1_policy_chain_set/#function-cbegin)**() const |
| auto | **[end](/doxygen/Classes/structsam_1_1_policy_chain_set/#function-end)**() |
| auto | **[cend](/doxygen/Classes/structsam_1_1_policy_chain_set/#function-cend)**() const |
| size_t | **[size](/doxygen/Classes/structsam_1_1_policy_chain_set/#function-size)**() const |
| bool | **[empty](/doxygen/Classes/structsam_1_1_policy_chain_set/#function-empty)**() const |
| | **[PolicyChainSet](/doxygen/Classes/structsam_1_1_policy_chain_set/#function-policychainset)**() =default |
| | **[PolicyChainSet](/doxygen/Classes/structsam_1_1_policy_chain_set/#function-policychainset)**(const PolicyChainSetDefinition & psets_defs, sol::state & lua)<br>[PolicyChainSet](/doxygen/Classes/structsam_1_1_policy_chain_set/) constructor.  |
| std::optional< std::vector< [Submission](/doxygen/Classes/classsam_1_1_submission/) > > | **[operator()](/doxygen/Classes/structsam_1_1_policy_chain_set/#function-operator())**([Experiment](/doxygen/Classes/classsam_1_1_experiment/) & expr)<br>Returns a list of submissions from DVs of an experiment.  |
| std::optional< std::vector< [Submission](/doxygen/Classes/classsam_1_1_submission/) > > | **[operator()](/doxygen/Classes/structsam_1_1_policy_chain_set/#function-operator())**(std::vector< [Submission](/doxygen/Classes/classsam_1_1_submission/) > & spool)<br>Returns a list of submissions from a list of submissions.  |

## Public Attributes

|                | Name           |
| -------------- | -------------- |
| std::vector< [PolicyChain](/doxygen/Classes/structsam_1_1_policy_chain/) > | **[pchains](/doxygen/Classes/structsam_1_1_policy_chain_set/#variable-pchains)**  |

## Detailed Description

```cpp
struct sam::PolicyChainSet;
```


[PolicyChainSet](/doxygen/Classes/structsam_1_1_policy_chain_set/) is a collection of PolicyChains

They are mainly being used and interpreted like a list of preferences, and will be executed chronologically. Most function will go through the list one by one, and will quit as soon as one of the PolicyChains find at least on outcome from a given list of options, e.g., SubmissionPool or [Experiment](/doxygen/Classes/classsam_1_1_experiment/). 

## Public Functions Documentation

### function operator[]

```cpp
inline PolicyChain & operator[](
    std::size_t idx
)
```


### function operator[]

```cpp
inline const PolicyChain & operator[](
    std::size_t idx
) const
```


### function begin

```cpp
inline auto begin()
```


### function cbegin

```cpp
inline auto cbegin() const
```


### function end

```cpp
inline auto end()
```


### function cend

```cpp
inline auto cend() const
```


### function size

```cpp
inline size_t size() const
```


### function empty

```cpp
inline bool empty() const
```


### function PolicyChainSet

```cpp
PolicyChainSet() =default
```


### function PolicyChainSet

```cpp
PolicyChainSet(
    const PolicyChainSetDefinition & psets_defs,
    sol::state & lua
)
```

[PolicyChainSet](/doxygen/Classes/structsam_1_1_policy_chain_set/) constructor. 

### function operator()

```cpp
std::optional< std::vector< Submission > > operator()(
    Experiment & expr
)
```

Returns a list of submissions from DVs of an experiment. 

**Parameters**: 

  * **expr** The experiment


**Return**: An optional list of submissions 

It chronologically applies all the available policy chains on the experiment and returns a list of submissions that are satisfies the **first**[PolicyChain](/doxygen/Classes/structsam_1_1_policy_chain/) in the list. If none of the chains were able to select any submissions, an empty `std::optional` will be returned.


### function operator()

```cpp
std::optional< std::vector< Submission > > operator()(
    std::vector< Submission > & spool
)
```

Returns a list of submissions from a list of submissions. 

**Parameters**: 

  * **spool** The pool of submissions


**Return**: An optional list of submissions 

It chronologically applies all the available policy chains on the submission pool and returns a list of submissions that are satisfies the **first**[PolicyChain](/doxygen/Classes/structsam_1_1_policy_chain/) in the list. If none of the chains were able to select any submissions, an empty `std::optional` will be returned.


## Public Attributes Documentation

### variable pchains

```cpp
std::vector< PolicyChain > pchains;
```


-------------------------------

Updated on  7 June 2021 at 12:00:21 CEST