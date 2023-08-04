# 2023 Workshop MISSIoN Nanopore Bioinformatics - Day 01

## General information & Setup

* This GitHub repository will guide you through the whole workshop
    * That means, that we will also jump a bit around between this repository, slide decks, the terminal, demo examples, and hands-on sessions
* You will find example commands in this workshop repository
    * **keep in mind** that these are examples! You should always familiarize yourself with a bioinformatics tool (read the publication, the GitHub README, ...)
    * we will mostly use default parameter settings if not otherwise stated, which might be not optimal for your own data!
    * remember that `--help` and google (and ChatGPT) are your friends! 
* Please raise your hand to ask a question at any time
* There will be always "lecture" parts followed by practical hands-on 
* We continue to work with the laptops you already used in the Illumina part
* In the future, you might also use the HPC (High-performance Cluster) at RKI, which we can also give a try during the course
    * Details about HPC usage can be found in the intranet (Confluence)

## Short Linux and bash re-cap (srry, again)

* Linux/Bash basics + conda setup ([slides](https://docs.google.com/presentation/d/14W8YPnMPd0GUmL6HvzHJTCjrigfbz9z1EUHr2P9-200/edit?usp=sharing))
* Another good resource: [Introduction to the UNIX command line](https://ngs-docs.github.io/2021-august-remote-computing/introduction-to-the-unix-command-line.html)
* small Bash cheat sheet:

```bash
# Print your user name
echo $USER
# change directory to your user home directory
cd /home/$USER
# show content of current directory
ls
# make a new directory called 'myfolder'
mkdir myfolder
# make conda environment and activate it
conda create -n nanoplot
conda activate nanoplot
# run a program
NanoPlot reads.fq.gz ...
```

## Install conda (should be already done, skip)

* Conda is a packaging manager that will help us to install bioinformatics tools and to handle their dependencies automatically
* In the terminal enter:

```bash
# Switch to a directory with enough space
cd /scratch/$USER

# make a new folder called 'workshop'
mkdir workshop

# switch to this folder
cd workshop

# Download conda installer
wget https://repo.anaconda.com/miniconda/Miniconda3-latest-Linux-x86_64.sh 

# Run conda installer
bash Miniconda3-latest-Linux-x86_64.sh
# Use space to scroll down the license agreement
# then type 'yes'
# accept the default install location with ENTER
# when asked whether to initialize Miniconda3 type 'yes'
# ATTENTION: the space in your home directory might be limited (e.g. 10 GB) and per default conda installs tools into ~/.conda/envs
# Thus, take care of your disk space! 

# Now start a new shell or simply reload your current shell via
bash

# You should now be able to create environments, install tools and run them
```

* Set up conda

```bash
# add repository channels for bioconda
conda config --add channels defaults
conda config --add channels bioconda
conda config --add channels conda-forge
```

* Create and activate a new conda environment

```bash
# -n parameter to specify the name
conda create -n workshop

# activate this environment
conda activate workshop

# You should now see (workshop) at the start of each line.
# You switched from the default 'base' environment to the 'workshop' environment.
```

__Hint:__ An often faster and more stable alternative to `conda` is `mamba`. Funningly, `mamba` can be installed via `conda` and then used in the similar way. Just replace `conda` then with `mamba` (like shown in the bioinformatics tool slides, linked below).

## Bacterial _de novo_ genome assembly from Nanopore data

__[Slides: Intro](https://docs.google.com/presentation/d/1hb3P6RIPsmyRiJkZoSQHQMf6FgFJrORhB4Pjk0FZTO4/edit?usp=sharing)__