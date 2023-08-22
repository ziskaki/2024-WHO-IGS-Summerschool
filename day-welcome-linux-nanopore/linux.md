# Workshop, Linux re-cap

## Short Linux and bash re-cap

* Linux/Bash basics + conda setup ([slides](https://docs.google.com/presentation/d/14xELo7lDbd-FYuy144ZDK1tV_ZBdBYun_COelrKYWps/edit?usp=sharing))
* Another good resource: [Introduction to the UNIX command line](https://ngs-docs.github.io/2021-august-remote-computing/introduction-to-the-unix-command-line.html)
* small Bash cheat sheet:

```bash
# Print your user name
echo $USER
# change directory to your user home directory (all of these are the same)
cd /home/$USER
cd $HOME
cd ~  # <- the shortest version, I like this one
# show content of current directory
ls
# make a new directory called 'myfolder'
mkdir myfolder
# make conda environment and activate it
mamba create -n nanoplot
conda activate nanoplot
mamba install nanoplot
# run a program
NanoPlot reads.fq.gz ...
```

## Install mamba (if done already on your machine: skip)

* Mamba is a packaging manager that will help us to install bioinformatics tools and to handle their dependencies automatically
* Mamba works together with the conda package manager, and makes installing packages faster
* You will use the mamba command to create environments and install packages, and conda command for some other package management tasks like configuration and activating environments (yes it can be a bit confusing)
* In the terminal enter:

```bash
# Switch to a directory with enough space
cd /scratch/$USER

# make a new folder called 'workshop'
mkdir workshop

# switch to this folder
cd workshop

# Download mamba installer
wget "https://github.com/conda-forge/miniforge/releases/latest/download/Mambaforge-Linux-x86_64.sh"

# ATTENTION: the space in your home directory might be limited (e.g. 10 GB) and per default conda installs tools into ~/.conda/envs
# Thus, take care of your disk space!
# On the HPC you can take care of this by moving ~/.conda to /scratch and making a symlink from your home directory:
# mv ~/.conda /scratch/dot-conda
# ln -s /scratch/dot-conda ~/.conda

# Run installer
bash Mambaforge-Linux-x86_64
# Use space to scroll down the license agreement
# then type 'yes'
# accept the default install location with ENTER
# when asked whether to initialize mamba type 'yes'

# Now start a new shell or simply reload your current shell via
bash

# You should now be able to create environments, install tools and run them
```

* Set up mamba

```bash
# add repository channels for bioconda
conda config --add channels defaults
conda config --add channels bioconda
conda config --add channels conda-forge
```

* Create and activate a new conda environment

```bash
# -n parameter to specify the name
mamba create -n workshop

# activate this environment
conda activate workshop

# You should now see (workshop) at the start of each line.
# You switched from the default 'base' environment to the 'workshop' environment.
```

Next: [Long-read Nanopore Introduction & Quality Control](nanopore.md)
