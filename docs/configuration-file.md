---
title: Introduction
---

Configuration File
==================

SAM uses a [JSON](https://www.json.org) file to load and save all simulation parameters. The code block below shows a general configuration file used by SAM to prepare the simulation and all its components. As shown, the config file is separated into 4 different sections, each corresponding to one of SAM's components discussed previously. In this chapter, we will discuss each part, and learn how to configure each parts separately in order to be able to simulate a full research as described in [Flow](flow.md) and [Research Workflow](research-workflow.md) sections.

<!--After customizing your own configuration file, you can load it to SAM using `./SAMpp --config=your-configuration-file.json`. This will start the simulation as described in the `flow`{.interpreted-text role="doc"} section.-->

??? example "Sample Configuration File"
	```json
	{
	    "experiment_parameters": {
	        "n_reps": 1,
	        "n_conditions": 2,
	        "n_dep_vars": 2,
	        "n_obs": 25,
	        "data_strategy": {
	            "name": "LinearModel",
	            "measurements": {
	                "dist": "mvnorm_distribution",
	                "means": [0.0, 0.0, 0.4, 0.4],
	                "covs": 0.5,
	                "stddevs": 1.0
	            }
	        },
	        "effect_strategy": {
	            "name": "MeanDifference"
	        },
	        "test_strategy": {
	            "name": "TTest",
	            "alpha": 0.005,
	            "alternative": "TwoSided",
	            "var_equal": true
	        }
	    },
	    "journal_parameters": {
	        "max_pubs": 24,
	        "selection_strategy": {
	            "name": "SignificantSelection",
	            "alpha": 0.05,
	            "pub_bias": 0.1,
	            "side": 0
	        }
	    },
	    "researcher_parameters": {
	        "decision_strategy": {
	            "name": "DefaultDecisionMaker",
	            "initial_selection_policies": [
	                ["sig", "min(pvalue)"]
	            ],
	            "will_start_hacking_decision_policies": [
	                "!sig"
	            ],
	            "stashing_policy": [
	                ""
	            ],
	            "between_hacks_selection_policies": [
	                [""]
	            ],
	            "between_replications_selection_policies": [
	                [""]
	            ],
	            "will_continue_replicating_decision_policy": [
	                ""
	            ],
	            "submission_decision_policies": [
	                ""
	            ]
	        },
	        "probability_of_being_a_hacker": 1,
	        "probability_of_committing_a_hack": 1,
	        "hacking_strategies": [],
	        "is_pre_processing": false,
	        "pre_processing_methods": [
	            ""
	        ]
	    },
	    "simulation_parameters": {
	        "log_level": "info",
	        "master_seed": "random",
	        "n_sims": 1,
	        "output_path": "../outputs/",
	        "output_prefix": "sample_sim",
	        "update_config": true,
	        "progress": false,
	        "save_all_pubs": false,
	        "save_meta": true,
	        "save_overall_summaries": true,
	        "save_pubs_per_sim_summaries": true,
	        "save_rejected": false
	    }
	}
	```

??? info "About JSON"
    For the introduction to JSON, see [here](https://learnxinyminutes.com/docs/json/) or [here](https://en.wikipedia.org/wiki/JSON).

## Simulation Parameters

This section specifies general parameters of the simulation. These parameters are not necessarily influencing SAM's modules. Table below summarizes simulations parameters, and their functions.


- **`log_level`**, *`string`*, Indicates level of logging during the simulation.
- **`progress`**, *`boolean`*, Indicates whether a progress bar is displayed or not.
- **`master_seed`**, *`int` / `"random"`*, An integer indicating the intial seed of the RNG engine. If set to "random", a random number will be used in each run.
- **`n_sims`**, *`int`*, Number of simulation repeated simulation r given parameters.
- **`save_output`**, *`boolean`*, Tells SAM to export the simulation data to CSV file 
- **`output_path`**, *`string`*, A path for output files.
- **`output_prefix`**, *`string`*, A prefix to be added to output filenames. .label} Raw simulation data files ends th `_sim.csv`, and meta-analysis data les ends with `_meta.csv`
- **`update_config`**, *`boolean`*, Indicates whether the config file should be updated after the simulation. This might overwrite `master_seed` or `output_path`
- **`save_all_pubs`**, *`boolean`*, Indicates whether all publications should be saved.
- **`save_meta`**, *`boolean`*, Indicates whether data from meta-analyses should be saved.
- **`save_overall_summaries`**, *`boolean`*, Indicates whether the summary of entire simulation should be calculated and saved.
- **`save_pubs_per_sim_summaries`**, *`boolean`*, Indicates whether the summary of each simulation run should be calucated and saved.
- **`save_rejected`**, *`boolean`*, Indicates whether rejected publications should be stored and saved.


## Experiment Parameters

Experiment parameters split into 4 different categories. First 4 paramters are mainly concenring with the experiment design, while each submodule gets its own set of parameters, [Data Strategy](data-strategies.md), [Test Strategies](test-strategies.md), and [Effect Strategies](effect-strategies.md).


- **`n_reps`**, *`int`*, Indicates the number of replications of the same research. 
- **`n_conditions`**, *`int`*, Indicates the number of conditions, n<sub>c</sub>. *Excluding the control group.* 
- **`n_dep_vars`**, *`int`*, Indicates the number of dependent variables in each condition, n<sub>d</sub>.
- **`n_obs`**, *`int`, `array`, `object`*, Indicates the number of observations per group 
- **`data_strategy`**, *`string`*, Specify the underlying [Data Strategy](data-strategies.md).
- **`test_strategy`**, *`string`*, Specify the underlying [Test Strategies](test-strategies.md).
- **`effect_strategy`**, *`string`*, Specify the underlying [Effect Strategies](effect-strategies.md).


## Researcher Parameters

This section defines the behavior of the Researcher. Researcher's parameters can be separated into three main parts, [Hacking Behaviors](hacking-behaviors.md), [Hacking Strategies](hacking-strategies.md), and [Decision Strategies](decision-strategies.md). The table below lists a few of the parameters, while each part's parameters will be discussed in more details later.


- **`decision_strategy`**, *`dict`*, Specification of a `DecisionStrategy`. See more `decision-strategies`.
- **`probability_of_being_a_hacker`**, *`number`*, Indicates the probability of a researcher deciding to apply any of the hacking strategies. [Hacking Behaviors](hacking-behaviors.md).
- **`hacking_strategies`**, *`list`*, A list of `list`, each indicating a chain of `HackingStrategy`.
- **`is_pre_processing`**, *`boolean`*, Indicates whether any pre-processing procedure is being performed on the data before passing the data to the researcher for analysis. 
- **`pre_processing_methods`**, *`list`*, Similar to `p_hacking_methods`. See [Pre-processing]: hacking-strategies.md#hacking-pre-processing  


## Journal Parameters

Journal parameters are less elaborate than other modules and are divivded into three main parts, [Selection Strategy](selection-strategies.md) and [Meta Analysis](meta_analyses.md).


- **`max_pubs`**, *`double`*, Maximum number of publications that will be cepted by the `Journal`.
- **`selection_strategy`**, *`string`*, The `SelectionStrategy` of the journal. 
- **`meta_analysis_metrics`**, *`list`*, List of meta anlysis methods with their parameters, see [Meta Analysis](meta-analyses.md)
