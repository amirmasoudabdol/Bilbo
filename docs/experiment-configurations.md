---
title: Introduction
---

# Experiment Configuration


## Experiment Parameters

Experiment parameters split into 4 different categories. First 4 paramters are mainly concenring with the experiment design, while each submodule gets its own set of parameters, [Data Strategy](data-strategies.md), [Test Strategies](test-strategies.md), and [Effect Strategies](effect-strategies.md).


- **`n_reps`**, *`int`*, Indicates the number of replications of the same research. 
- **`n_conditions`**, *`int`*, Indicates the number of conditions, n<sub>c</sub>. *Excluding the control group.* 
- **`n_dep_vars`**, *`int`*, Indicates the number of dependent variables in each condition, n<sub>d</sub>.
- **`n_obs`**, *`int`, `array`, `object`*, Indicates the number of observations per group 
- **`data_strategy`**, *`string`*, Specify the underlying [Data Strategy](data-strategies.md).
- **`test_strategy`**, *`string`*, Specify the underlying [Test Strategies](test-strategies.md).
- **`effect_strategy`**, *`string`*, Specify the underlying [Effect Strategies](effect-strategies.md).
