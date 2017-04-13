---
layout: post
title: "Create Virtual enviornments using Anaconda"
date: 2017-04-13 09:39
categories: Anaconda virutal_environment
---



# Create Virtual Environments for Python with Conda

[from Here](https://uoa-eresearch.github.io/eresearch-cookbook/recipe/2014/11/20/conda/)

How to setup a virtual environments using conda for the Anaconda Python Distribution.

> A virtual environment is a named, isolated, working copy of Python that maintains its own files, directories, and paths so that you can work with specific version of libraries or Python itself without affecting other Python projects. 
>
> Virtual environments make it easy to cleanly separate different projects and avoid problems with different dependencies and version requirements across components. The `conda` command is the preferred interface for manaing installations and virtual environments with the Anaconda Python distribution. 

[TOC]

##  Check conda is installed and in your Path

1. Open a terminal client
2. Enter `conda -v` into the terminal command line and press enter
3. If conda is installed you should see something like the following.

```CQL
$ conda -V
conda 4.3.13
```

## Check conda is up to date

1. In ther terminal client enter

```
conda update conda
```

1. Update any packages if necessary by typing `y` to proceed.

## Create a virtual environment for your project

1. In the terminal client enter the following where *your_env_name* is the name you want to call your environment, and replace *x.x* with the Python version you wish to use (To see a list of available python version first, type `conda search "^python$"` and press enter).

```
conda create -n your_env_name python=x.x anaconda
```

1. Press `y` to proceed. This will install the Python version and all the associated anaconda packaged libraries at `path_to_your_anaconda_location/anaconda/envs/your_env_name`. 

## Activate your virtual environment

1. To activate or switch into your virtual enviornment, simply type the following where *your_env_name* is the name you gave to your environment at create

```
source activate your_env_name
```

1. Activating a conda environment modifeis the PATH and shell variables to point to the specific isolated Python set-up you created. The command prompt will change to indicate which conda environment you are currently in by pretending `(your_env_name)`. To see a list of your environments, use the command `conda info -e`.

## Install Additional Python Package to a virtual environment

1. To install additional packages only to your virtual environment, enter the following command where *your_env_name* is the name of your environment, and *[package]* is the name of the package you wish to install. **Failure to specify `-n your_env_name` will install the package to the root Python installation**.

```
conda install -n your_env_name [package]
```

In order to install tensorflow, enter the following command in the terminal.

```
pip install tensorflow
```

## Deactive Your virtual environment

1. To end a session in the current environment, enter the following. There is no need to specify the envname - which ever is currently active will be deactivated, and the PATH and shell variables will be returned to normal.

```
source deactivate
```

## Delete a no longer needed virtual environment

1. To delete a conda environment, enter the following, where `your_env_name` is the name of the environment you wish to delete.

```
conda remove -n your_env_name -all
```
## List up all available environments.

Use the conda environment infor command to find out:

```
conda info --envs
```

You can also use the conda environments list command as follows

```
conda env list
```

## Clone an evrionment

Make an exact copy of an environment by creating a clone of it. 

```
conda create --name <src env name> --clone <cloned env name>
```