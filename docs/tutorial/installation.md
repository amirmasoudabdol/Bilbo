This page helps you setup your system, install the required packages, and finally build and run SAM.

## Dependencies

SAM depends on several packages:

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


### Windows (WLS)

Microsoft has recently started to embrace Linux (and open-source) by offering a first party Linux environment inside the Windows. [Windows Linux Subsystem](https://docs.microsoft.com/en-us/windows/wsl/about), WLS, is an example of this enviroment. As Microsoft puts it, "_The Windows Subsystem for Linux lets developers run a GNU/Linux environment — including most command-line tools, utilities, and applications — directly on Windows, unmodified, without the overhead of a traditional virtual machine or dualboot setup._"

In our tests, this in facts works better than alternatives, e.g., Cygwin, and allows you to quickly and correctly deploy an Ubuntu instance on your system. We recommend you to give this approach a try if you are a Windows user since it offers the cleanest and most robust solutions to build and run SAM in your Windows machine. If you decide to give the WLS a try, you can simply head to the Linux (Ubuntu) section of this guide and follow the same procedure without any issues. 

### Windows (Anaconda)

If you are using Windows, in order to avoid unneccessary complications and compilation issues, we recommend setting up your development enviroment by installing [Anaconda](https://www.anaconda.com/products/individual). By installing Anaconda, you get a full-featured scientific enviroment that simplifies the process of building and managing SAM's dependencies tremendously. 
	
After installing anaconda, open the Anaconda Navigator and open the CMD.exe prompt. Here you can install the required packages using the `conda` command. It is advised to enter each command separately.

```bash
conda install -c conda-forge cmake
conda install -c conda-forge boost-cpp
conda install -c conda-forge nlohmann_json
conda install -c conda-forge armadillo
conda install -c conda-forge mlpack
conda install -c conda-forge ensmallen
conda install -c conda-forge spdlog
conda install -c conda-forge fmt
conda install -c conda-forge lua
```

!!! note
	You can choose to use Anaconda on macOS and Linux as well. If you go with Anaconda, then you can simply ignore the following steps.

### macOS

Before you start, you need to download and install the Xcode from [Mac App Store](https://apps.apple.com/us/app/xcode/id497799835?mt=12). In addition, you need to install the Command Line Tools, by running `xcode-select --install` in your Terminal, **after successfully installing Xcode.**

Now, if you do not have Homebrew already installed, you may download and install from [here](https://brew.sh), and after successful installation of Homebrew, you can run the following commands to install all the requirements. This may takes a few minutes...

```shell
brew install cmake
brew install Lua
brew install boost
brew install armadillo
brew install ensmallen
brew install mlpack
brew install fmt
brew install spdlog
brew tap nlohmann/json; brew install nlohmann-json
```

### Linux (Debian/Ubuntu)

On Ubuntu, you can install most of the dependencies using the `apt` tool. 

```bash
sudo apt update
sudo apt install build-essential
sudo apt install cmake
sudo apt install liblapack-dev libblas-dev
sudo apt install libboost-all-dev
sudo apt install libarmadillo-dev
sudo apt install lua5.3 liblua5.3-dev
```

For `nlohmann/json`, `mlpack`, `ensmallen`, `fmt`, and `spdlog`, you need to build and install these packages manually. This is due to the fact that sometimes there required version of them are not yet deployed in different Linux distros.  Please follow the link to their homepage, and follow their instruction. 

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
