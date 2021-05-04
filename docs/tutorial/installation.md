This page helps you setup your system, install the required packages, and finally build and run SAM.

## Dependencies

SAM dependes on several packages:

- [CMake](https://cmake.org) (need to be installed)
- [Boost](https://www.boost.org) (need to be installed)
- [nlohmanh/json](https://github.com/nlohmann/json) (need to be installed)
- [Armadillo](http://arma.sourceforge.net) (need to be installed)
	- [LAPACK](http://performance.netlib.org/lapack/) (need to be installed)
	- [BLAS](http://www.netlib.org/blas/) (need to be installed)
- [mlpack](https://www.mlpack.org) (need to be installed)
- [ensmallen](http://ensmallen.org) (need to be installed)
- [spdlog](https://github.com/gabime/spdlog) (need to be installed)
- [fmt](https://fmt.dev/latest/index.html). (need to be installed)
- [Lua](https://www.lua.org) (need to be installed)
- [sol2](https://github.com/ThePhD/sol2) (included)
- [indicators](https://github.com/p-ranav/indicators) (included)
- [baaraan](https://github.com/amirmasoudabdol/baaraan) (included as a submodule)
- [effolkronium/random](https://github.com/effolkronium/random) (included)
- [rang](https://github.com/agauniyal/rang) (included)

Below you can find an instruction on how to install all these dependencies based on your operation system.

### Windows

If you are using Windows, in order to avoid unneccessary complications and compilation issues, we recommend setting up your development enviroment by installing [Anaconda](https://www.anaconda.com/products/individual). By installing Anaconda, you get a full-featured scientific enviroment that simplifies the process of building and managing SAM's dependencies tremendously. 

After installing anaconda, you can install the required packages using the `conda` command.

```bash
conda install -c conda-forge cmake
conda install -c conda-forge boost-cpp
conda install -c conda-forge armadillo
conda install -c conda-forge mlpack
conda install -c conda-forge ensmallen
conda install -c conda-forge lua
conda install -c conda-forge fmt
conda install -c conda-forge spdlog
```


!!! note
	You can choose to use Anaconda on macOS and Linux as well. If you go with Anaconda, then you can simply ignore the following steps.

### macOS

Before you start, you need to download and install the Xcode from [Mac App Store](https://apps.apple.com/us/app/xcode/id497799835?mt=12). In addition, you need to install the Command Line Tools, by running `xcode-select --install` in your Terminal, **after successfully installing Xcode.**

Now, if you do not have Homebrew already installed, you may download and install from [here](https://brew.sh), and after successful installation of Homebrew, you can run the following commands to install all the requirements. This may takes a few minutes...

```shell
brew install cmake
brew install boost armadillo ensmallen mlpack fmt spdlog
brew install Lua
brew tap nlohmann/json; brew install nlohmann-json
```

### Linux (Debian/Ubuntu)

On Ubuntu, you can install most of the dependencies using the `apt` tool. 

```bash
sudo apt update
sudo apt install cmake
sudo apt install liblapack-dev libblas-dev
sudo apt install libboost-all-dev
sudo apt install libarmadillo-dev
sudo apt install lua5.3
```

For nlohmann/json, mlpack, ensmallen, fmt, and spdlog, you need to build and install these packages manually. Please follow the link to their homepage, and follow their instruction. 

!!! note
	Based on your distribution and version, these commands may be different, or you may end up having different versions of these packages available to you.

## Building SAM

In order to build SAM, you can follow the following steps:

```bash
mkdir SAM_Project
cd SAM_Project
git clone https://amirmasoudabdol.github.com/SAM
cd SAM
git submodule init; git submodule update;
mkdir build
cd build
cmake ..
make
```

If this process is successful, you should have a file name `SAMrun` in your `build/` directory. You can test whether SAM is built correctly and completely by running this command, `./SAMrun --help`.

<!-- ### Installing SAM

You may install the `./SAMrun` executable in your system by running:

```bash
cd SAM_Project/SAM/build
sudo make install
```
 -->