---
title: sam::PolicyChain


---

# sam::PolicyChain


**Module:** **[Policy-related Modules](/doxygen/Modules/group___policies/)**

 [More...](#detailed-description)


`#include <Policy.h>`













## Public Functions

|                | Name           |
| -------------- | -------------- |
|  | **[PolicyChain](/doxygen/Classes/structsam_1_1_policy_chain/#function-policychain)**() =default  |
|  | **[PolicyChain](/doxygen/Classes/structsam_1_1_policy_chain/#function-policychain)**(const std::vector< std::string > & pchain_defs, sol::state & lua)  |
|  | **[PolicyChain](/doxygen/Classes/structsam_1_1_policy_chain/#function-policychain)**(const std::vector< std::string > & pchain_defs, LogicType logic, sol::state & lua)  |
| Policy & | **[operator[]](/doxygen/Classes/structsam_1_1_policy_chain/#function-operator[])**(std::size_t idx)  |
| const Policy & | **[operator[]](/doxygen/Classes/structsam_1_1_policy_chain/#function-operator[])**(std::size_t idx) const  |
| auto | **[begin](/doxygen/Classes/structsam_1_1_policy_chain/#function-begin)**()  |
| auto | **[cbegin](/doxygen/Classes/structsam_1_1_policy_chain/#function-cbegin)**() const  |
| auto | **[end](/doxygen/Classes/structsam_1_1_policy_chain/#function-end)**()  |
| auto | **[cend](/doxygen/Classes/structsam_1_1_policy_chain/#function-cend)**() const  |
| bool | **[operator()](/doxygen/Classes/structsam_1_1_policy_chain/#function-operator())**(const [Submission](/doxygen/Classes/classsam_1_1_submission/) & sub) <br>Checks whether the given [Submission]() satisfies **all** listed policies.  |
| bool | **[operator()](/doxygen/Classes/structsam_1_1_policy_chain/#function-operator())**([Experiment](/doxygen/Classes/classsam_1_1_experiment/) * experiment) <br>Determine whether the experiment satisfies any of the given policies.  |
| std::optional< std::vector< [Submission](/doxygen/Classes/classsam_1_1_submission/) > > | **[operator()](/doxygen/Classes/structsam_1_1_policy_chain/#function-operator())**([Experiment](/doxygen/Classes/classsam_1_1_experiment/) & experiment)  |
| std::optional< [Submission](/doxygen/Classes/classsam_1_1_submission/) > | **[operator()](/doxygen/Classes/structsam_1_1_policy_chain/#function-operator())**(std::vector< [Submission](/doxygen/Classes/classsam_1_1_submission/) > & spool)  |
| bool | **[empty](/doxygen/Classes/structsam_1_1_policy_chain/#function-empty)**() const  |


## Public Attributes

|                | Name           |
| -------------- | -------------- |
| LogicType | **[ltype](/doxygen/Classes/structsam_1_1_policy_chain/#variable-ltype)**  |
| std::vector< std::string > | **[defs](/doxygen/Classes/structsam_1_1_policy_chain/#variable-defs)**  |
| std::vector< Policy > | **[pchain](/doxygen/Classes/structsam_1_1_policy_chain/#variable-pchain)**  |






## Detailed Description

```cpp
struct sam::PolicyChain;
```



























Implementation of [PolicyChain](/doxygen/Classes/structsam_1_1_policy_chain/)

[PolicyChain](/doxygen/Classes/structsam_1_1_policy_chain/) is a list of Policies that will be executed chronologically. They often being used to check whether an [Experiment](/doxygen/Classes/classsam_1_1_experiment/) or a [Submission](/doxygen/Classes/classsam_1_1_submission/) can satisfy the set of given rules. 









## Public Functions Documentation

### function PolicyChain

```cpp
PolicyChain() =default
```





























### function PolicyChain

```cpp
inline PolicyChain(
    const std::vector< std::string > & pchain_defs,
    sol::state & lua
)
```





























### function PolicyChain

```cpp
inline PolicyChain(
    const std::vector< std::string > & pchain_defs,
    LogicType logic,
    sol::state & lua
)
```





























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





























### function operator()

```cpp
inline bool operator()(
    const Submission & sub
)
```

Checks whether the given [Submission]() satisfies **all** listed policies. 

**Parameters**: 

  * **sub** The submission







**Return**: The result of applying all policies on the given submission 





















### function operator()

```cpp
inline bool operator()(
    Experiment * experiment
)
```

Determine whether the experiment satisfies any of the given policies. 












!!! note "Note"

    * Currently this only uses `all_of` meaning that all policies need to be satisfied for the check to be passed.
    * This is horrible, there are two methods, one gets the pointer and another one the ref. This is very confusing! 




**Todo**: I'm planning to implement the `logic` variable by which one can control which logic is going to be used











For every dependent variable, we check whether that dv satisfies any of the given rules, if so, we set the verdict to `true` meaning that at least part of the experiment satisfies all the policies. However, if after going through all outcomes, none satisfies all the rules `false` will be returned, meaning that none of the outcomes satisfied all the given rules


### function operator()

```cpp
inline std::optional< std::vector< Submission > > operator()(
    Experiment & experiment
)
```













!!! note "Note"

    * this is probably a better implementation but for now, I'll stay with the one above to get around the stopping condition implementation 
    * I'm not sure if I need this one 
















Todowe check the experiment, and return the submission 

We found a bunch

I don't think I actually need this

### function operator()

```cpp
inline std::optional< Submission > operator()(
    std::vector< Submission > & spool
)
```




























else: We are still looking. This happens when I'm testing a comparison

We found a bunch This is not a acceptable case for now! TodoBut it should be! 

### function empty

```cpp
inline bool empty() const
```































## Public Attributes Documentation

### variable ltype

```cpp
LogicType ltype = LogicType::AllOf;
```





























### variable defs

```cpp
std::vector< std::string > defs;
```





























### variable pchain

```cpp
std::vector< Policy > pchain;
```

































-------------------------------

Updated on  7 December 2020 at 13:20:10 CET