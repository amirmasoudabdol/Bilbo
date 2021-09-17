---
title: Introduction
---

!!! note
	The contents of this documentation might slightly differ from the information published by Abdol et al., 2021 [@Abdol_2021]. For general introduction to SAM, please refer to the main publication while we sync the two sources.

# Configuration File

SAM uses a [JSON](https://www.json.org) file to load and save all simulation parameters. The code block below shows a general configuration file used by SAM. As highlighted, the config file is separated into 4 different sections, each corresponding to one of SAM's component discussed previously. In this chapter, we will discuss each section, and learn how to configure each module separately; in order to be able to customize and configure all processes of [execution](execution-flow.md), [research](research-workflow.md) and [hacking](hacking-wrokflow.md) workflows.

<!-- entire  a full research as described in [Execution Flow](execution-flow.md) and [Research Workflow](research-workflow.md). Moreover, we will discuss how processes of execution,  -->

!!! example "Sample Configuration File"
	```json hl_lines="2 26 59 68"
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
	    "journal_parameters": {
	        "max_pubs": 24,
	        "selection_strategy": {
	            "name": "SignificantSelection",
	            "alpha": 0.05,
	            "pub_bias": 0.1,
	            "side": 0
	        }
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




\bibliography