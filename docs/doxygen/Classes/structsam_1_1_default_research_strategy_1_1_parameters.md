---
title: sam::DefaultResearchStrategy::Parameters
summary: The parameters of the strategy. 

---

# sam::DefaultResearchStrategy::Parameters

**Module:** **[Parameters of the Research Strategies](/doxygen/Modules/group___research_strategy_parameters/)**



The parameters of the strategy. 
`#include <ResearchStrategy.h>`

## Public Attributes

|                | Name           |
| -------------- | -------------- |
| DecisionMethod | **[name](/doxygen/Classes/structsam_1_1_default_research_strategy_1_1_parameters/#variable-name)**  |
| std::vector< std::vector< std::string > > | **[initial_selection_policies_defs](/doxygen/Classes/structsam_1_1_default_research_strategy_1_1_parameters/#variable-initial_selection_policies_defs)** <br>Initial Selection [Policy](/doxygen/Classes/structsam_1_1_policy/).  |
| std::vector< std::string > | **[will_not_start_hacking_decision_policies_def](/doxygen/Classes/structsam_1_1_default_research_strategy_1_1_parameters/#variable-will_not_start_hacking_decision_policies_def)** <br>Will Start Hacking Decision [Policy](/doxygen/Classes/structsam_1_1_policy/).  |
| std::vector< std::vector< std::string > > | **[between_stashed_selection_policies_defs](/doxygen/Classes/structsam_1_1_default_research_strategy_1_1_parameters/#variable-between_stashed_selection_policies_defs)** <br>Between Stashed Selection [Policy](/doxygen/Classes/structsam_1_1_policy/).  |
| std::vector< std::string > | **[will_not_continue_replicating_decision_policy_def](/doxygen/Classes/structsam_1_1_default_research_strategy_1_1_parameters/#variable-will_not_continue_replicating_decision_policy_def)** <br>Will Continue Replicating Decision [Policy](/doxygen/Classes/structsam_1_1_policy/).  |
| std::vector< std::vector< std::string > > | **[between_replications_selection_policies_defs](/doxygen/Classes/structsam_1_1_default_research_strategy_1_1_parameters/#variable-between_replications_selection_policies_defs)** <br>Between Replication Selection [Policy](/doxygen/Classes/structsam_1_1_policy/).  |
| std::vector< std::string > | **[stashing_policy_def](/doxygen/Classes/structsam_1_1_default_research_strategy_1_1_parameters/#variable-stashing_policy_def)** <br>Stashing Selection [Policy](/doxygen/Classes/structsam_1_1_policy/).  |
| std::vector< std::string > | **[submission_decision_policies_defs](/doxygen/Classes/structsam_1_1_default_research_strategy_1_1_parameters/#variable-submission_decision_policies_defs)** <br>Submissions Decision [Policy](/doxygen/Classes/structsam_1_1_policy/).  |

## Public Attributes Documentation

### variable name

```cpp
DecisionMethod name = DecisionMethod::DefaultResearchStrategy;
```


### variable initial_selection_policies_defs

```cpp
std::vector< std::vector< std::string > > initial_selection_policies_defs;
```

Initial Selection [Policy](/doxygen/Classes/structsam_1_1_policy/). 

### variable will_not_start_hacking_decision_policies_def

```cpp
std::vector< std::string > will_not_start_hacking_decision_policies_def;
```

Will Start Hacking Decision [Policy](/doxygen/Classes/structsam_1_1_policy/). 

### variable between_stashed_selection_policies_defs

```cpp
std::vector< std::vector< std::string > > between_stashed_selection_policies_defs;
```

Between Stashed Selection [Policy](/doxygen/Classes/structsam_1_1_policy/). 

### variable will_not_continue_replicating_decision_policy_def

```cpp
std::vector< std::string > will_not_continue_replicating_decision_policy_def;
```

Will Continue Replicating Decision [Policy](/doxygen/Classes/structsam_1_1_policy/). 

### variable between_replications_selection_policies_defs

```cpp
std::vector< std::vector< std::string > > between_replications_selection_policies_defs;
```

Between Replication Selection [Policy](/doxygen/Classes/structsam_1_1_policy/). 

### variable stashing_policy_def

```cpp
std::vector< std::string > stashing_policy_def;
```

Stashing Selection [Policy](/doxygen/Classes/structsam_1_1_policy/). 

### variable submission_decision_policies_defs

```cpp
std::vector< std::string > submission_decision_policies_defs;
```

Submissions Decision [Policy](/doxygen/Classes/structsam_1_1_policy/). 

-------------------------------

Updated on 29 June 2021 at 16:13:48 CEST