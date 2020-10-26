---
title: Introduction
---

# Experiment Configurations

Experiment parameters split into 4 different categories. First 4 paramters are mainly concenring with the experiment design, while each submodule gets its own set of parameters, [Data Strategy](/data-strategies.md), [Test Strategies](test-strategies.md), and [Effect Strategies](effect-strategies.md).


- **`n_reps`**, *`int`*, Indicates the number of replications of the same research. 
- **`n_conditions`**, *`int`*, Indicates the number of conditions, n<sub>c</sub>. *Excluding the control group.* 
- **`n_dep_vars`**, *`int`*, Indicates the number of dependent variables in each condition, n<sub>d</sub>.
- **`n_obs`**, *`int`, `array`, `object`*, Indicates the number of observations per group 
- **`data_strategy`**, *`string`*, Specify the underlying [Data Strategy](/data-strategies.md).
- **`test_strategy`**, *`string`*, Specify the underlying [Test Strategies](test-strategies.md).
- **`effect_strategy`**, *`string`*, Specify the underlying [Effect Strategies](effect-strategies.md).


The code snippet below showcases a sample of Experiment's parameters that's being used in [Bakker et al., 2012](/examples/bakker_et_al_2012.md).


!!! experiment "Experiment's Configurations"
	```json
      "experiment_parameters": {
        "n_obs": 20,
        "n_conditions": 2,
        "n_dep_vars": 2,
        "data_strategy": {
          "name": "LinearModel",
          "measurements": {
              "dist": "mvnorm_distribution",
              "means": [0, 0, 0.25, 0.25],
              "sigma": [[1.0,   0.5,   0.0,   0.0],
                        [0.5,   1.0,   0.0,   0.0],
                        [0.0,   0.0,   1.0,   0.5],
                        [0.0,   0.0,   0.5,   1.0]]
        },
        "test_strategy": {
          "name": "TTest",
          "alpha": 0.05,
          "alternative": "TwoSided",
          "var_equal": true
        },
        "effect_strategy": {
          "name": "MeanDifference"
        }
      }
    }
	```