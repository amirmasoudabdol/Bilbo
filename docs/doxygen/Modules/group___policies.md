---
title: Policy-related Modules
summary: List of available policy-related modules.  

---

# Policy-related Modules




List of available policy-related modules.  [More...](#detailed-description)






## Classes

|                | Name           |
| -------------- | -------------- |
| struct | **[sam::PolicyChain](/doxygen/Classes/structsam_1_1_policy_chain/)**  |
| struct | **[sam::PolicyChainSet](/doxygen/Classes/structsam_1_1_policy_chain_set/)**  |




## Functions

|                | Name           |
| -------------- | -------------- |
|  | **[NLOHMANN_JSON_SERIALIZE_ENUM](/doxygen/Modules/group___policies/#function-nlohmann_json_serialize_enum)**(LogicType , {{LogicType::AllOf, "all_of"}, {LogicType::AnyOf, "any_of"}, {LogicType::NoneOf, "none_of"}} ) <br>Implementation of the Policy.  |




## Detailed Description

List of available policy-related modules. 


























Description to come! 




## Functions Documentation

### function NLOHMANN_JSON_SERIALIZE_ENUM

```cpp
NLOHMANN_JSON_SERIALIZE_ENUM(
    LogicType ,
    {{LogicType::AllOf, "all_of"}, {LogicType::AnyOf, "any_of"}, {LogicType::NoneOf, "none_of"}} 
)
```

Implementation of the Policy. 


























A policy is a logical rule that it's being applied on an experiment, submission, or a set of submissions.



* In the case of submission, policy checks whether the given submission satisfies the given policy.
* In the case of set of submissions, or an experiment, policy checks whether the any of the items, ie., dvs or sub, will satisfy the given policy, if so, it'll return those items, otherwise, the output will be empty. 

Given the forward iterator, it applies `func` on each item, and returns a subset of the range where all items satisfy the `func` criteria

beginThe begin 

endThe end

ForwardItThis usually accepts [Submission](/doxygen/Classes/classsam_1_1_submission/)'s ForwardIt

Return a tuple containing three variables.

This can take care of either [Group](/doxygen/Classes/classsam_1_1_group/) or [Submission](/doxygen/Classes/classsam_1_1_submission/) because the Lua instance is aware of them!


Shuffling the array and setting the end pointer to the first time, this basically mimic the process of selecting a random element from the list.

Returns the result of applying the policy on a submission

Todoto be implemented 

Todoto be implemented 

Todothese should be joined, they're technically the same! 





-------------------------------

Updated on  7 December 2020 at 13:20:10 CET