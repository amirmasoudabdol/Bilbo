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
|  | **[PolicyChainSet](/doxygen/Classes/structsam_1_1_policy_chain_set/#function-policychainset)**() =default  |
|  | **[PolicyChainSet](/doxygen/Classes/structsam_1_1_policy_chain_set/#function-policychainset)**(const std::vector< std::vector< std::string >> & psets_defs, sol::state & lua)  |
| auto | **[begin](/doxygen/Classes/structsam_1_1_policy_chain_set/#function-begin)**()  |
| auto | **[cbegin](/doxygen/Classes/structsam_1_1_policy_chain_set/#function-cbegin)**() const  |
| auto | **[end](/doxygen/Classes/structsam_1_1_policy_chain_set/#function-end)**()  |
| auto | **[cend](/doxygen/Classes/structsam_1_1_policy_chain_set/#function-cend)**() const  |
| std::optional< [Submission](/doxygen/Classes/classsam_1_1_submission/) > | **[operator()](/doxygen/Classes/structsam_1_1_policy_chain_set/#function-operator())**(const [Experiment](/doxygen/Classes/classsam_1_1_experiment/) * expr)  |
| [PolicyChain](/doxygen/Classes/structsam_1_1_policy_chain/) & | **[operator[]](/doxygen/Classes/structsam_1_1_policy_chain_set/#function-operator[])**(std::size_t idx)  |
| const [PolicyChain](/doxygen/Classes/structsam_1_1_policy_chain/) & | **[operator[]](/doxygen/Classes/structsam_1_1_policy_chain_set/#function-operator[])**(std::size_t idx) const  |
| size_t | **[size](/doxygen/Classes/structsam_1_1_policy_chain_set/#function-size)**() const  |
| bool | **[empty](/doxygen/Classes/structsam_1_1_policy_chain_set/#function-empty)**() const  |


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

### function PolicyChainSet

```cpp
PolicyChainSet() =default
```





























### function PolicyChainSet

```cpp
inline PolicyChainSet(
    const std::vector< std::vector< std::string >> & psets_defs,
    sol::state & lua
)
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





























### function operator()

```cpp
inline std::optional< Submission > operator()(
    const Experiment * expr
)
```




























Todo: Check and return, 

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





























### function size

```cpp
inline size_t size() const
```





























### function empty

```cpp
inline bool empty() const
```































## Public Attributes Documentation

### variable pchains

```cpp
std::vector< PolicyChain > pchains;
```

































-------------------------------

Updated on  3 December 2020 at 12:37:29 CET