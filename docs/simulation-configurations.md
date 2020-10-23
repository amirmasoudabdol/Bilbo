---
title: "Simulation"
---

# Simulation Configurations

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

