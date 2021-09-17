---
title: Getting Started
---

After successfully installing and building SAM, you should be able to located the SAM executable, `SAMrun`, in your `build/` folder. First thing to do at this point is to run `SAMrun --help` and check all its available commands and features.

```
SAMrun Options:
  -h [ --help ]           produce help message
  -v [ --version ]        print version string
  --debug arg             Print debugging information
  --update-config         Update the config file with the drawn seeds
  --progress              Shows the progress bar
  --master-seed arg (=42) Set the master seed
  --output-prefix arg     Output prefix used for saving files
  --output-path arg       Output path
  --config arg            JSON config file
```

!!! note
	Keep in mind that, you may see a slightly different command set based on the version that you are running. You can check `SAMrun`'s using the `-v` flag.

## Sample Run

In your build folder you can find a sample configuration file, `sample_config_file.json`. You can use this file to test your simulation and check whether you've successfully build and configured SAM before running your simulation study. 

```bash
./SAMrun --config=sample_config_file.json --debug=info
```

The above command will produce an output like this:

```
[11:23] [info] Processing the configuration file...
[11:23] [info] Initializing the Researcher...
[11:23] [info] Starting the simulation...
[11:23] [info] Saving Overall Statistics Summaries...
[11:23] [info] Saved ../outputs/sample_simulation_Publications.csv
[11:23] [info] Saved ../outputs/sample_simulation_Publications_Summaries.csv
```

Notice the last two lines where `SAMrun` informs you about the type and place of output files storing your results. In this case, there are two output files have been generated, and they are saved in the `../outputs/` folder.
 
??? note
	You can use the `--debug` command to control the amount of information emitted by `SAMrun` during the execution process. For instance, running the command above with `--debug=debug` will generate much larger output.

	```
	[11:24] [info] Processing the configuration file...
	[11:24] [info] Initializing the Researcher...
	[11:24] [debug] Building a Data Strategy
	[11:24] [debug] Initializing the Journal.
	[11:24] [info] Starting the simulation...
	[11:24] [debug] Executing the Research Workflow!
	[11:24] [debug] Checking whether the Final Submission is going to be submitted to Journal...
	[11:24] [debug] Executing the Research Workflow!
	[11:24] [debug] Checking whether the Final Submission is going to be submitted to Journal...
	[11:24] [debug] Executing the Research Workflow!
	[11:24] [debug] Checking whether the Final Submission is going to be submitted to Journal...
	[11:24] [debug] Executing the Research Workflow!
	[11:24] [debug] Checking whether the Final Submission is going to be submitted to Journal...
	[11:24] [debug] Executing the Research Workflow!
	[11:24] [debug] Checking whether the Final Submission is going to be submitted to Journal...
	[11:24] [debug] Executing the Research Workflow!
	[11:24] [debug] Checking whether the Final Submission is going to be submitted to Journal...
	[11:24] [debug] Executing the Research Workflow!
	[11:24] [debug] Checking whether the Final Submission is going to be submitted to Journal...
	[11:24] [debug] Executing the Research Workflow!
	[11:24] [debug] Checking whether the Final Submission is going to be submitted to Journal...
	[11:24] [debug] Executing the Research Workflow!
	[11:24] [debug] Checking whether the Final Submission is going to be submitted to Journal...
	[11:24] [debug] Executing the Research Workflow!
	[11:24] [debug] Checking whether the Final Submission is going to be submitted to Journal...
	[11:24] [debug] Executing the Research Workflow!
	[11:24] [debug] Checking whether the Final Submission is going to be submitted to Journal...
	[11:24] [debug] Executing the Research Workflow!
	[11:24] [debug] Checking whether the Final Submission is going to be submitted to Journal...
	[11:24] [debug] Executing the Research Workflow!
	[11:24] [debug] Checking whether the Final Submission is going to be submitted to Journal...
	[11:24] [debug] Executing the Research Workflow!
	[11:24] [debug] Checking whether the Final Submission is going to be submitted to Journal...
	[11:24] [debug] Executing the Research Workflow!
	[11:24] [debug] Checking whether the Final Submission is going to be submitted to Journal...
	[11:24] [debug] Executing the Research Workflow!
	[11:24] [debug] Checking whether the Final Submission is going to be submitted to Journal...
	[11:24] [debug] Executing the Research Workflow!
	[11:24] [debug] Checking whether the Final Submission is going to be submitted to Journal...
	[11:24] [debug] Executing the Research Workflow!
	[11:24] [debug] Checking whether the Final Submission is going to be submitted to Journal...
	[11:24] [debug] Executing the Research Workflow!
	[11:24] [debug] Checking whether the Final Submission is going to be submitted to Journal...
	[11:24] [debug] Executing the Research Workflow!
	[11:24] [debug] Checking whether the Final Submission is going to be submitted to Journal...
	[11:24] [debug] Executing the Research Workflow!
	[11:24] [debug] Checking whether the Final Submission is going to be submitted to Journal...
	[11:24] [debug] Executing the Research Workflow!
	[11:24] [debug] Checking whether the Final Submission is going to be submitted to Journal...
	[11:24] [debug] Executing the Research Workflow!
	[11:24] [debug] Checking whether the Final Submission is going to be submitted to Journal...
	[11:24] [debug] Executing the Research Workflow!
	[11:24] [debug] Checking whether the Final Submission is going to be submitted to Journal...
	[11:24] [debug] Executing the Research Workflow!
	[11:24] [debug] Checking whether the Final Submission is going to be submitted to Journal...
	[11:24] [debug] Executing the Research Workflow!
	[11:24] [debug] Checking whether the Final Submission is going to be submitted to Journal...
	[11:24] [debug] Executing the Research Workflow!
	[11:24] [debug] Checking whether the Final Submission is going to be submitted to Journal...
	[11:24] [debug] Executing the Research Workflow!
	[11:24] [debug] Checking whether the Final Submission is going to be submitted to Journal...
	[11:24] [debug] Executing the Research Workflow!
	[11:24] [debug] Checking whether the Final Submission is going to be submitted to Journal...
	[11:24] [debug] Executing the Research Workflow!
	[11:24] [debug] Checking whether the Final Submission is going to be submitted to Journal...
	[11:24] [debug] Executing the Research Workflow!
	[11:24] [debug] Checking whether the Final Submission is going to be submitted to Journal...
	[11:24] [debug] Executing the Research Workflow!
	[11:24] [debug] Checking whether the Final Submission is going to be submitted to Journal...
	[11:24] [debug] Executing the Research Workflow!
	[11:24] [debug] Checking whether the Final Submission is going to be submitted to Journal...
	[11:24] [debug] Executing the Research Workflow!
	[11:24] [debug] Checking whether the Final Submission is going to be submitted to Journal...
	[11:24] [debug] Executing the Research Workflow!
	[11:24] [debug] Checking whether the Final Submission is going to be submitted to Journal...
	[11:24] [debug] Executing the Research Workflow!
	[11:24] [debug] Checking whether the Final Submission is going to be submitted to Journal...
	[11:24] [debug] Executing the Research Workflow!
	[11:24] [debug] Checking whether the Final Submission is going to be submitted to Journal...
	[11:24] [debug] Executing the Research Workflow!
	[11:24] [debug] Checking whether the Final Submission is going to be submitted to Journal...
	[11:24] [debug] Executing the Research Workflow!
	[11:24] [debug] Checking whether the Final Submission is going to be submitted to Journal...
	[11:24] [debug] Executing the Research Workflow!
	[11:24] [debug] Checking whether the Final Submission is going to be submitted to Journal...
	[11:24] [debug] Executing the Research Workflow!
	[11:24] [debug] Checking whether the Final Submission is going to be submitted to Journal...
	[11:24] [debug] Executing the Research Workflow!
	[11:24] [debug] Checking whether the Final Submission is going to be submitted to Journal...
	[11:24] [debug] Executing the Research Workflow!
	[11:24] [debug] Checking whether the Final Submission is going to be submitted to Journal...
	[11:24] [debug] Executing the Research Workflow!
	[11:24] [debug] Checking whether the Final Submission is going to be submitted to Journal...
	[11:24] [debug] Executing the Research Workflow!
	[11:24] [debug] Checking whether the Final Submission is going to be submitted to Journal...
	[11:24] [debug] Executing the Research Workflow!
	[11:24] [debug] Checking whether the Final Submission is going to be submitted to Journal...
	[11:24] [debug] Executing the Research Workflow!
	[11:24] [debug] Checking whether the Final Submission is going to be submitted to Journal...
	[11:24] [debug] Executing the Research Workflow!
	[11:24] [debug] Checking whether the Final Submission is going to be submitted to Journal...
	[11:24] [debug] Executing the Research Workflow!
	[11:24] [debug] Checking whether the Final Submission is going to be submitted to Journal...
	[11:24] [debug] Executing the Research Workflow!
	[11:24] [debug] Checking whether the Final Submission is going to be submitted to Journal...
	[11:24] [info] Saving Overall Statistics Summaries...
	[11:24] [info] Saved ../outputs/sample_simulation_Publications.csv
	[11:24] [info] Saved ../outputs/sample_simulation_Publications_Summaries.csv
	```


## Running More Simulation

As you get more comfortable with how `SAMrun` process your configuration file, you may want to exlore your parameters space by creating your configuration files, and feeding them to `SAMrun`. 

For instance, if you are interested in checking the effect of a specific Hacking Strategy on the full range of true effect sizes, you start by preparing a template configuration file that describes your Experiment Setup, Research, Research Workflow, and Journal. Then, you use this template file to create new configuration files each differing slightly from your original setup. In this case, you can create 10 different files to cover a range of true effect sizes from 0 to 1.

!!! experiment "Data Strategy of Configuration Files"

	=== "0.0"
		```json
		{
	        "data_strategy": {
	            "name": "LinearModel",
	            "measurements": {
	                "dist": "mvnorm_distribution",
	                "means": [0.0, 0.0, 0.0, 0.0],
	                "covs": 0.5,
	                "stddevs": 1
	            }
	        }
	    }
		```
	=== "0.1"
		```json
		{
	        "data_strategy": {
	            "name": "LinearModel",
	            "measurements": {
	                "dist": "mvnorm_distribution",
	                "means": [0.0, 0.0, 0.1, 0.1],
	                "covs": 0.5,
	                "stddevs": 1
	            }
	        }
	    }
		```
	=== "0.2"
		```json
		{
	        "data_strategy": {
	            "name": "LinearModel",
	            "measurements": {
	                "dist": "mvnorm_distribution",
	                "means": [0.0, 0.0, 0.2, 0.2],
	                "covs": 0.5,
	                "stddevs": 1
	            }
	        }
	    }
		```
	=== "0.3"
		```json
		{
	        "data_strategy": {
	            "name": "LinearModel",
	            "measurements": {
	                "dist": "mvnorm_distribution",
	                "means": [0.0, 0.0, 0.3, 0.3],
	                "covs": 0.5,
	                "stddevs": 1
	            }
	        }
	    }
		```
	=== "0.4"
		```json
		{
	        "data_strategy": {
	            "name": "LinearModel",
	            "measurements": {
	                "dist": "mvnorm_distribution",
	                "means": [0.0, 0.0, 0.4, 0.4],
	                "covs": 0.5,
	                "stddevs": 1
	            }
	        }
	    }
		```
	=== "0.5"
		```json
		{
	        "data_strategy": {
	            "name": "LinearModel",
	            "measurements": {
	                "dist": "mvnorm_distribution",
	                "means": [0.0, 0.0, 0.5, 0.5],
	                "covs": 0.5,
	                "stddevs": 1
	            }
	        }
	    }
		```
	=== "0.6"
		```json
		{
	        "data_strategy": {
	            "name": "LinearModel",
	            "measurements": {
	                "dist": "mvnorm_distribution",
	                "means": [0.0, 0.0, 0.6, 0.6],
	                "covs": 0.5,
	                "stddevs": 1
	            }
	        }
	    }
		```
	=== "0.7"
		```json
		{
	        "data_strategy": {
	            "name": "LinearModel",
	            "measurements": {
	                "dist": "mvnorm_distribution",
	                "means": [0.0, 0.0, 0.7, 0.7],
	                "covs": 0.5,
	                "stddevs": 1
	            }
	        }
	    }
		```
	=== "0.8"
		```json
		{
	        "data_strategy": {
	            "name": "LinearModel",
	            "measurements": {
	                "dist": "mvnorm_distribution",
	                "means": [0.0, 0.0, 0.8, 0.8],
	                "covs": 0.5,
	                "stddevs": 1
	            }
	        }
	    }
		```
	=== "0.9"
		```json
		{
	        "data_strategy": {
	            "name": "LinearModel",
	            "measurements": {
	                "dist": "mvnorm_distribution",
	                "means": [0.0, 0.0, 0.9, 0.9],
	                "covs": 0.5,
	                "stddevs": 1
	            }
	        }
	    }
		```
	=== "1.0"
		```json
		{
	        "data_strategy": {
	            "name": "LinearModel",
	            "measurements": {
	                "dist": "mvnorm_distribution",
	                "means": [0.0, 0.0, 1.0, 1.0],
	                "covs": 0.5,
	                "stddevs": 1
	            }
	        }
	    }
		```

Assuming that you are not planning to change other parameters of your simulation, these 10 configurations are all you need to run to study the influece of your Hacking Strategy and Research Workflow on the range of true effect sizes. You can run your simulation by individually passing each configuration file to `SAMrun`:

```bash
./SAMrun --config=sample_simulation_mu_0.0.json
./SAMrun --config=sample_simulation_mu_0.1.json
./SAMrun --config=sample_simulation_mu_0.2.json
./SAMrun --config=sample_simulation_mu_0.3.json
./SAMrun --config=sample_simulation_mu_0.4.json
./SAMrun --config=sample_simulation_mu_0.5.json
./SAMrun --config=sample_simulation_mu_0.6.json
./SAMrun --config=sample_simulation_mu_0.7.json
./SAMrun --config=sample_simulation_mu_0.8.json
./SAMrun --config=sample_simulation_mu_0.9.json
./SAMrun --config=sample_simulation_mu_1.0.json
```

After running all the simulations, you find your `outputs/` folder filled with several output files based on your preferences. In this case, `SAMrun` generates two output files for each configuration file, `sample_simulation_mu_μ_Publications.csv` and `sample_simulation_mu_μ_Publications_Summaries.csv`. Therefore, in total, there will be 20 output files ready for pre-processing. You can move these files to your preferred folder, and start analyzing them using R, or any other programming language or software.

## Running Even More Simulation

As you may have realized, the process of creating new configuration files is a cumbersome and error-prone process, especially if you are planning to run thousands of different configuration files. In address this issues, we developed Frodo to be SAM's project management companion. Frodo streamlines the process of automatically creating thousands and thousands of configuration files. In addition, it helps you to run your entire simulation, deal with the complexity of naming several configuration files, and it helps you summarize and process your simulation's results.

Read more about [Frodo](https://sam.amirmasoudabdol.name/frodo).