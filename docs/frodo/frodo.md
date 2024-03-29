---
title: "Introduction"
---

# Frodo

<img src="/img/frodo-logo.png" width="120" align="right"/>

Frodo is a collection of scripts that facilitates the process of creating, managing and running SAM projects. With Frodo, you can create, remove, or archive your projects. In addition, when within your project, Frodo offers several useful tools to simplify the process of configuring and running your project.

!!! attention
    Frodo has developed as an internal tool to help us test and develop SAM with greater speed and precision. As the project grew, we realized that some of the tools might be useful to other developers too; so, we decided to package and release it as well.

## Requirement

Frodo is mainly written in [GNU Make](https://www.gnu.org/software/make/) and it should be available on most operation systems by default. On Windows, you may either install [Cygwin](https://www.cygwin.com) or if you are running newer version of Windows, e.g., Windows 10, you may install the [Windows Subsystem for Linux](https://docs.microsoft.com/en-us/windows/wsl/). 

Alternatively, if you find the method above tedious, you may opt for installing the [Anaconda](https://www.anaconda.com) package to get most of the tools needed to run Frodo and its dependent scripts. This is a valid alternative on all three mainstream operation systems if you do not currently have a development environment ready, or do not know how to set it up correctly. Often installing Anaconda is enough to get a proper and well-functioning scientific development environment.

## Getting Started with Frodo

After successfully preparing your system, you can download Frodo from GitHub using:

```bash
git clone https://github.com/amirmasoudabdol/Frodo.git
```

You may now `cd` into the Frodo folder, and simply type `make` on the command line to run Frodo. This should show some helpful information about available commands and parameters.

```
This is Frodo, a handy toolset for preparing a new project using SAM.
In the process of 'prepare'-ing a new project, this Makefile produces
several template files for configuring and running a SAM project on
your local machine or on Lisa cluster.

Make sure that this Makefile knows where SAM and other
dependencies are located. You can set their path through the
parameters defined in line 9 – 12 of the Makefile.

Usage:
  make <target> parameter=value
  help             Display this help

  [Parameters]
  project          Project name
  path             Project path, defaults to ./projects/

-----------------------------------------------------------

Build
  prepare          Create a new project by running <config> and <sam>
  config           Building necessary files and folders for a new project
  sam              Build SAMrun executable. Note: This will update SAM source directory and rebuild it
  compress         Zip everything in the <project>

Cleanup
  clean            Remove all output files, i.e., configs, outputs, logs, jobs
  veryclean        Remove all project files
  remove           Delete the entire project directory

Example Usage:
    make prepare project=apollo path=HOME/Projects/
    make remove  project=apollo
```

Start by preparing a project, and observing the output, e.g., `make prepare project=apollo`. This creates a folder in the `projects/` folder named `apollo`, and populates it with files and scripts necessary for running a SAM simulation. Notice the messages produced by Frodo during this process.

!!! example "Sample output of `make prepare project=apollo`"
    An example output of Frodo's `prepare` command:

    ```
    > Preparing apollo...
    > Prepare a copy of SAM for apollo...
    > Preparing project files...
    > Copying SAM...
    > Configuring SAM...
      ... some CMake messages ...
    > Building SAM...
      ... some CMake messages ...
      [100%] Built target SAMrun
    > Successfully prepared and saved "apollo" in "/projects" ...
    > `cd` into the project folder and start with the `make` command ...
    ```

!!! warning
    Frodo stores several template scripts in the `scripts/` folder, and it uses them to configure your projects correctly. It's recommended not to mess with these files unless you know what you are doing!

### Primary Commands

While Frodo offers a range of commands, there are a few important ones that you should know about:

#### The `prepare` command

Use the prepare command to create a new project, e.g., `make prepare project=your-project-name`. After using the `prepare` command, Frodo creates a new directory at `projects/your-project-name` and fill it with all the necessary files. Two files are particularity important:

- `your-project-name_prepare_config_files.py` is a project-specific script that describe the specification of your parameters space. You can find and modify this file at `projects/your-project-name/scripts/your-project-name_prepare_config_files.py`
- `your-project-name_post_processing.R` is another project-specific script that is being used by Frodo to perform post-processing analysis on SAM's output. You can find and modify this file at `projects/your-project-name/scripts/your-project-name_prepare_config_files.py`

[*Project Frodo*](#project-frodo) will cover the full list of these files and folders.

#### The `load` Command and `templates/` folder

With the `load` command, you are telling Frodo that you like to load your projects with some of your customized script files. 

The `templates/` folder is where Frodo looks for project-specific files and templates. Two of the most important template files that you should prepare for your projects are: `your-project-name_prepare_config_files.py` and `your-project-name_post_processing.R`. 

If you have created and placed these files for your projects in the `templates/` folder, running `make load project=your-project-name` will replace the default scripts with these two user-defined templates.

!!! example
    You may use the template folder for quickly setting up new projects. The general procedure looks something like this:

    - `make prepare project=discovery` to create a new project
    - Create two project-specific template files, e.g., `discovery_prepare_config_files.py` and `discovery_post_processing.R`
    - `make load project=discovery` 
    - `cd projects/discovery` to go into your project folder
    - `make parameters` to generate new configuration files based on the `discovery_prepare_config_files.py`

## Project Frodo

After preparing a project, you can head into the `projects/your-project-name`, and observe all the files created by Frodo for your projects. 

- **`Makefile`**, this is the *Project Frodo*!
- **`SAMrun`**, an instance of SAM program that you can use to run your simulation. Run `./SAMrun --help` for more info.
- **`configfilenames.pool`**, a list of all the configuration files to run using SAM.
- **`SAM/`**, a folder containing SAM's code and its dependencies.
- **`configs/`**, a folder containing all the configuration files.
- **`dbs/`**, a folder containing databases generated by Frodo.
- **`jobs/`**, a folder containing job scripts for running SAM on SURFSara's Lisa Cluster.
- **`logs/`**, a folder containing log files produced by SAM.
- **`outputs/`**, a folder containing output files produced by SAM.
- **`scripts/`**, a folder containing scripts used by Frodo to run, configure, and summarize SAM's results.

As you can see, each file and folder has its purpose and unless you know what you are doing you should not mess with them. The `SAMrun` executable is the most important item of this list. You can either use this file manually to run your simulation, `./SAMrun --config=your-config-file.json`, or use the *Project Frodo* to run a batch of configuration files.

### Using the Project Frodo

You can run the *Project Frodo* as before by running the `make` command inside your project folder. Executing the `make` command again shows a list of commands and parameters offered by Project Frodo.

```
This is Project Frodo, you can control your project using this Makefile. There are several commands are available for running your simulation locally or on a
cluster. It's also possible to run the simulation sequentially or in
parallel on your local machine.

Usage:
  make <target>
  help             Display this help

[Paramters]
  using            Path to a new parameter generator
  name             The name of the archive

--------------------------------------------------------------

Build
  sam-build        Rebuild the binaries, run this if you've modified the code
  parameters       Preparing config files for SAM

Post-processing
  csv              Create a set of files `*_prepared.csv` by adding all keys/values to them. Use this when the database is too big
  stack            Stack several CSV files into one CSV file
  stacker          Faster version of stacker. Use this for lager data files
  database         Aggregate output files into a SQLite database
  summary          Runinng the `post-processing.R` script on every file in output/ folder

Run
  run-seq-local    Running the simulation sequentially on the local machine
  run-par-local    Running the simulation in parallel on the local machine
  run-par-lisa     Running the simulation in parallel on the Lisa cluster
  run-par-lisa-batch  Running the simulation in parallel on the Lisa cluster

Packaging
  archive          Archiving the entire project directory to ../marjan_2012_all_test_archive/archive/CUREENT_DATE_TIME or ../marjan_2012_all_test_analysis/archive/<name>
  compress         Compress the outputs/*, logs/* and configs/*

Cleanup
  clean            Remove most project specific files, configs, jobs, logs, etc.
  veryclean        Remove all project files, including outputs

Example Usage:
    make parameters using=~/projects_config/2012_project.py
    make run-seq-local; make archive name=Feb_5.zip
```

Here, Frodo turns into a project-specific helper tool and helps you configure and run your simulation, as well as exporting and archiving your results. In order to run a big simulation with lots of configuration files using the Project Frodo, you first need to create a list of configuration files using `parameters`, and then execute SAM on every one of them using the `run-seq-local` command.

```bash
make parameters
make run-seq-local
```

- The `make parameters` first runs the `your-project-name_prepare_config_files.py` file to generates all your configuration files and store them into the `configs/` folder.
  - In addition, Frodo stores a list of all the generated configuration files into the `configfilenames.pool` file.
- After successfully running the `make parameters`, you can run your simulation on every files using `make run-seq-local`, or by manually running SAM on any of the available configuration files using `./SAMrun --config=configs/your-selected-config-file.json`.

!!! note
    Frodo assumes that you have already prepared the `your-project-name_prepare_config_files.py` file beforehand. If you have not, you may head into the `scripts/` folder, modify it based on your preferences and head back and run the `make parameters` again.

If you have already placed a customized version of the `your-project-name_prepare_config_files.py` script in the `templates/` folder, then you may simply `load` it to the project and speed up your process. 

```bash
make prepare project=discovery
make load project=discovery
cd projects/discovery
make parameters
make run-seq-local
```

This is specially a useful approach if you are planning to iterate over your design. In this case, you can run your simulation, process your results, then modify the `your-project-name_prepare_config_files.py` file, and head back to your project to repeat the process with new set of parameters and simulation specification.


#### Cleaning Up Your Project

You should be aware that after each run, most of the folders are filled with your project files, e.g., `configs/`, `outputs/`, `logs/`. If you plan to re-run your project, it is recommended to clean up the project before running Frodo/SAM again. This guarantees that your output files are corresponding to your configuration files, and no file from the previous run is lurking around in your project folder.

- `make clean` command removes all your project specific files but leaves the `outputs/` files intact.
- `make veryclean` command removes all your project files, **including your `outputs/` files.**

### Running the Simulations in Parallel

As you may have noticed, Frodo offers several run commands. The second part of the command indicates whether the simulations will be run sequentially; or they can run in parallel (e.g., 8 simulation at a time). 

- `run-seq-local`, runs 
- `run-par-local`
- `run-par-lisa`

In addition, if you are using the SURFsara Lisa cluster, you may use the last command to fully take advantage of the cluster system and distribute your simulation across the Lisa cluster. This command automatically creates a temporary folder on Lisa, request several nodes, distribute and run SAM across the cluster and finally collects all the output data and stores them into the `outputs/` folder.

## Post Processing

After running your simulation, Frodo stores all of the output files generated by SAM into the `outputs/` folder. At this stage, you may start extracting the output files and analyze your simulation data. While you can simply copy the files and process them using R, or any other programming language. The *Project Frodo* offers a few utilities to make your life a bit easier.

- `csv`
- `stack`
- `stacker`
- `database`
- `summary`

The `csv` command is maybe one of the most useful commands in Frodo. It essentially combines your configuration file with your outputs. This is very useful for when you are working with a large grid of parameters. For instance, if you are running a re-running your simulation setup for 10 different values of true effect size, μ, you will at least have 10 output files. While SAM names your output files similar to your config files, you simulation parameters are not listed in the output files. The `csv` command basically merge each configuration file with its appropriate output file. This is is very handy especially when you want to group your output files in R.