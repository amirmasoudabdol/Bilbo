---
title: "Simulation"
---

# Simulation Configurations

This section of configuration file specifies general parameters of the simulation. These parameters are mainly defining higher-level behaviors of SAM regarding input and outputs. 

```json linenums="1"
"simulation_parameters": {
    "n_sims": 1,
    "master_seed": "random",
    "log_level": "info",
    "progress": false,
    "output_path": "../outputs/",
    "output_prefix": "sample_sim",
    "update_config": true,
    "save_all_pubs": false,
    "save_meta": true,
    "save_overall_summaries": true,
    "save_pubs_per_sim_summaries": true,
    "save_rejected": false
}
```

The list below describes 

- **`n_sims`**, *`int`*, indicates total number of simulations.
- **`master_seed`**, *`int` / `"random"`*, indicates the intial seed of the RNG engine. If set to "random", a random number will be used in each run.
- **`log_level`**, *`string`*, indicates the [logging level](https://www.tutorialspoint.com/log4j/log4j_logging_levels.htm) of the simulation
- **`progress`**, *`boolean`*, indicates whether a progress bar should be displayed or not
- **`output_path`**, *`string`*, indicates a path to be used for output files
- **`output_prefix`**, *`string`*, a prefix to be added to *all* output filenames
- **`update_config`**, *`boolean`*, indicates whether the config file should be updated after the simulation. **Note:** This might overwrite `master_seed` or `output_path`
- **`save_all_pubs`**, *`boolean`*, indicates whether all publications should be saved.
	- One CSV file with the name of `output_prefix_Publications.csv`, containing all accepted publications across all simulations, will be created 
- **`save_meta`**, *`boolean`*, indicates whether data from meta-analyses should be saved.
	- One CSV file for each given meta-analysis method with the name of `output_prefix_MetaAnalysisMethodName.csv`, containing records of meta-analysis output from each simulation, will be created
- **`save_overall_summaries`**, *`boolean`*, indicates whether the summary of entire simulation should be calculated and saved
	- One CSV file for the entire simulation with the name of `output_prefix_Publications_Summaries.csv`, containing one record of several statistics from all publications, will be created
		- for each output parameters, SAM calcuate the overall *mean, standard deviation, variance, min, max, range*
	- One CSV file for the entire simulation with the name of `output_prefix_MetaAnalysisMethodName_Summaries.csv`, containing one record of several statistics from all meta analysis outputs, will be created.  
- **`save_pubs_per_sim_summaries`**, *`boolean`*, indicates whether the summary of each simulation run should be calucated and saved.
	- One CSV file for the entire simulation with the name of `output_prefix_Publications_Per_Sim_Summaries.csv`, containing records of several statistics from each publications list, will be created.
- **`save_rejected`**, *`boolean`*, Indicates whether rejected publications should be stored and saved.
	- One CSV file for the entire simulation with the name of `output_prefix_Rejected.csv`, containing all rejected publications across all simulations, will be created

