---
title: sam::PolicyChain
summary: Implementation of the PolicyChain class. 

---

# sam::PolicyChain

**Module:** **[Policy-related Modules](/doxygen/Modules/group___policies/)**



Implementation of the [PolicyChain]() class.  [More...](#detailed-description)


`#include <Policy.h>`

## Public Functions

|                | Name           |
| -------------- | -------------- |
| [Policy](/doxygen/Classes/structsam_1_1_policy/) & | **[operator[]](/doxygen/Classes/structsam_1_1_policy_chain/#function-operator[])**(std::size_t idx) |
| const [Policy](/doxygen/Classes/structsam_1_1_policy/) & | **[operator[]](/doxygen/Classes/structsam_1_1_policy_chain/#function-operator[])**(std::size_t idx) const |
| auto | **[begin](/doxygen/Classes/structsam_1_1_policy_chain/#function-begin)**() |
| auto | **[cbegin](/doxygen/Classes/structsam_1_1_policy_chain/#function-cbegin)**() const |
| auto | **[end](/doxygen/Classes/structsam_1_1_policy_chain/#function-end)**() |
| auto | **[cend](/doxygen/Classes/structsam_1_1_policy_chain/#function-cend)**() const |
| bool | **[empty](/doxygen/Classes/structsam_1_1_policy_chain/#function-empty)**() const |
| | **[PolicyChain](/doxygen/Classes/structsam_1_1_policy_chain/#function-policychain)**() =default |
| | **[PolicyChain](/doxygen/Classes/structsam_1_1_policy_chain/#function-policychain)**(const PolicyChainDefinition & pchain_defs, [PolicyChainType](/doxygen/Modules/group___policies/#enum-policychaintype) type, sol::state & lua)<br>[PolicyChain](/doxygen/Classes/structsam_1_1_policy_chain/) constructor.  |
| bool | **[operator()](/doxygen/Classes/structsam_1_1_policy_chain/#function-operator())**(const [Submission](/doxygen/Classes/classsam_1_1_submission/) & sub)<br>Checks whether the given [Submission]() satisfies **all** all policies.  |
| bool | **[operator()](/doxygen/Classes/structsam_1_1_policy_chain/#function-operator())**(const [DependentVariable](/doxygen/Classes/classsam_1_1_dependent_variable/) & dv)<br>Checks whether the given [DependentVariable](/doxygen/Classes/classsam_1_1_dependent_variable/) satisfies **all** the policies.  |
| bool | **[operator()](/doxygen/Classes/structsam_1_1_policy_chain/#function-operator())**([DependentVariable](/doxygen/Classes/classsam_1_1_dependent_variable/) & dv) |
| bool | **[operator()](/doxygen/Classes/structsam_1_1_policy_chain/#function-operator())**([Experiment](/doxygen/Classes/classsam_1_1_experiment/) * experiment)<br>Determines whether the experiment satisfies any of the given policies.  |
| std::optional< std::vector< [Submission](/doxygen/Classes/classsam_1_1_submission/) > > | **[operator()](/doxygen/Classes/structsam_1_1_policy_chain/#function-operator())**([Experiment](/doxygen/Classes/classsam_1_1_experiment/) & experiment)<br>Returns a list of submission satisfying the policy chain.  |
| std::optional< std::vector< [Submission](/doxygen/Classes/classsam_1_1_submission/) > > | **[operator()](/doxygen/Classes/structsam_1_1_policy_chain/#function-operator())**(std::vector< [Submission](/doxygen/Classes/classsam_1_1_submission/) > & spool)<br>Returns a list of submissions satisfying the policy chain.  |

## Public Attributes

|                | Name           |
| -------------- | -------------- |
| [PolicyChainType](/doxygen/Modules/group___policies/#enum-policychaintype) | **[type_](/doxygen/Classes/structsam_1_1_policy_chain/#variable-type_)**  |
| PolicyChainDefinition | **[defs](/doxygen/Classes/structsam_1_1_policy_chain/#variable-defs)**  |
| std::vector< [Policy](/doxygen/Classes/structsam_1_1_policy/) > | **[pchain](/doxygen/Classes/structsam_1_1_policy_chain/#variable-pchain)**  |

## Detailed Description

```cpp
struct sam::PolicyChain;
```

Implementation of the [PolicyChain]() class. 

PolicyChains are a list of Policies that will be executed chronologically. They are often being used to check whether an [Experiment](/doxygen/Classes/classsam_1_1_experiment/) or a [Submission](/doxygen/Classes/classsam_1_1_submission/) can satisfy all the given policies.

PolicyChains can be defined in two different ways. They are either a _selection_ or _decision_ chains. The `::Selection` chains are used to filter an experiment or a list of submissions based on the given policies. The `::Decision` chains are used to check whether any of the submissions or dependent variables are satisfying all the available policies in the given chain. 

## Public Functions Documentation

### function operator[]

```cpp
inline Policy & operator[](
    std::size_t idx
)
```


### function operator[]

```cpp
inline const Policy & operator[](
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


### function empty

```cpp
inline bool empty() const
```


### function PolicyChain

```cpp
PolicyChain() =default
```


### function PolicyChain

```cpp
PolicyChain(
    const PolicyChainDefinition & pchain_defs,
    PolicyChainType type,
    sol::state & lua
)
```

[PolicyChain](/doxygen/Classes/structsam_1_1_policy_chain/) constructor. 

It constructs a [PolicyChain](/doxygen/Classes/structsam_1_1_policy_chain/) object, and it also takes care of a few other things like making sure that no comparison operator comes after any of the function calls. It also sets the type of the [PolicyChain](/doxygen/Classes/structsam_1_1_policy_chain/), as described in PolicyChainType. 


### function operator()

```cpp
bool operator()(
    const Submission & sub
)
```

Checks whether the given [Submission]() satisfies **all** all policies. 

**Parameters**: 

  * **sub** The submission


**Return**: The result of applying all policies on the given submission 

### function operator()

```cpp
bool operator()(
    const DependentVariable & dv
)
```

Checks whether the given [DependentVariable](/doxygen/Classes/classsam_1_1_dependent_variable/) satisfies **all** the policies. 

**Parameters**: 

  * **dv** The dependent variable


**Return**: The result of applying all policies on the given dv 

### function operator()

```cpp
bool operator()(
    DependentVariable & dv
)
```


### function operator()

```cpp
bool operator()(
    Experiment * experiment
)
```

Determines whether the experiment satisfies any of the given policies. 

**Return**: Returns `true` if at least one DV satisfies all the policies, otherwise `false`. 

**Todo**: Refactor this such that it accepts a reference

This checks whether any of the DependentVariable(s) are satisfying all the policies of the chain.


### function operator()

```cpp
std::optional< std::vector< Submission > > operator()(
    Experiment & experiment
)
```

Returns a list of submission satisfying the policy chain. 

**Parameters**: 

  * **expr** The experiment


**Return**: An optional list of submissions 

**Note**: Only dependent variables of the treatment group will be considered.

This applies the policy chain on the [Experiment](/doxygen/Classes/classsam_1_1_experiment/) and returns a list of submissions (constructed from dependent variables of the experiment) that are satisfying all the available policies.


### function operator()

```cpp
std::optional< std::vector< Submission > > operator()(
    std::vector< Submission > & spool
)
```

Returns a list of submissions satisfying the policy chain. 

**Parameters**: 

  * **spool** The list of submissions


**Return**: A subset of `spool`, if any 

This applies all the available policies of the chain on the given pool of submissions and if there were any hit, it returns those. If not, it will report an empty list.


## Public Attributes Documentation

### variable type_

```cpp
PolicyChainType type_;
```


### variable defs

```cpp
PolicyChainDefinition defs;
```


### variable pchain

```cpp
std::vector< Policy > pchain;
```


-------------------------------

Updated on 29 June 2021 at 16:13:48 CEST