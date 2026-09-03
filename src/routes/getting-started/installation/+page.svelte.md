---
layout: default
title: 'MIA Lab: Installation'
---

# Installation

## Python installation

To start with the installation, download the [Anaconda installer](https://www.anaconda.com/distribution/) for your operating system with Python >= 3.8.

### Initial steps

These steps need to be performed for all operating systems.

1. Create a [GitHub account](https://github.com/signup) (the free account is sufficient).
2. Fork the MIA Lab repository:
   1. Go to the MIA Lab repository: [https://github.com/ubern-mialab/mialab](https://github.com/ubern-mialab/mialab)
   2. Fork the repository by clicking on the `Fork` button in the right upper corner.
   3. Follow the instructions on GitHub.
   4. Go to your MIALab fork (you are at the right location if the text in the left upper corner is of the structure `[yourgithubaccount]/mialab`).
   5. Click on the green `Clone` button and copy the URL (`https://github.com/[yourgithubaccount]/mialab.git`) shown. You will later use it for cloning your fork to your local machine, and probably to [UBELIX](/getting-started/tools/ubelix-hpc/).

Continue with the operating system specific installation instructions below.

## Operating system specific installation steps

### macOS

The installation has not been tested.

**git installation**

Download [git](https://git-scm.com/downloads) and install it. Then, clone your MIALab repository fork:

```
cd /path/to/where/you/want/the/code
git clone https://github.com/[yourgithubaccount]/MIALab.git
```

**Anaconda installation**

Follow the instructions on the [official website](https://docs.anaconda.com/anaconda/install/mac-os/), and then verify the installation:

```
conda list # which should list all installed Anaconda packages
```

Create a new Python 3.10 environment with the name mialab (confirm with `y` when prompted during creation):

```
conda create -n mialab python=3.10
```

Activate the environment:

```
conda activate mialab
```

**Install required packages**

```
cd /path/to/MIALab/repository
pip install -r requirements.txt # will install all required packages
```

### Windows

The installation has been tested on Windows 10.

**git installation**

Download [git](https://git-scm.com/downloads) and install it. Then, clone your MIALab repository fork - open "Git Bash":

```
cd \path\to\where\you\want\the\code
git clone https://github.com/[yourgithubaccount]/MIALab.git
```

**Anaconda installation**

Follow the instructions on the [official website](https://docs.anaconda.com/anaconda/install/windows/).

Verify the installation - open "Anaconda Prompt":

```
conda list # which should list all installed Anaconda packages
```

Create a new Python 3.10 environment with the name mialab (confirm with `y` when prompted during creation):

```
conda create -n mialab python=3.10
```

Activate the environment by:

```
conda activate mialab
```

**Install required packages**

```
cd \path\to\MIALab\repository
pip install -r requirements.txt # will install all required packages
```

### Linux

Run the following commands in the terminal (tested on Ubuntu 16.04 LTS and 18.04 LTS).

**git installation**

```
sudo apt-get install git
```

Clone your MIALab repository fork:

```
cd /path/to/where/you/want/the/code
git clone https://github.com/[yourgithubaccount]/MIALab.git
```

**Anaconda installation**

Follow the instructions on the [official website](https://docs.anaconda.com/anaconda/install/linux/), and then verify the installation:

```
conda list # which should list all installed Anaconda packages
```

Create a new Python 3.10 environment with the name mialab (confirm with `y` when prompted during creation):

```
conda create -n mialab python=3.10
```

Activate the environment by:

```
conda activate mialab
```

**Install required packages**

```
cd /path/to/MIALab/repository
pip install -r requirements.txt # will install all required packages
```

## Testing the installation

Finally, if all of the above works without issues, execute the installation test script to verify that all the dependencies are set up correctly:

```
python ./test/test_install.py
```

## Setting up the IDE

Next, move to the [IDE page](/getting-started/tools/ide/) to set up your favorite development environment, to be maximally productive with the code involved with this course.

## MATLAB installation

Follow the instructions on the [MathWorks website](https://ch.mathworks.com/academia/tah-portal/universitat-bern-40639324.html) to install MATLAB on your computer. Operating system specific requirements are [here](https://ch.mathworks.com/support/requirements/matlab-system-requirements.html). Once you have MATLAB installed, read through the [MATLAB section of the IDE page](/getting-started/tools/ide/#matlab) to learn more about working with this program.
