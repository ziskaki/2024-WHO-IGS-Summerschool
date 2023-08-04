# 2023 Workshop MISSIoN Nanopore Bioinformatics - Day 01

## General information & Setup

* This GitHub repository will guide you through the whole workshop
    * That means, that we will also jump a bit around between this repository, slide decks, the terminal, demo examples, and hands-on sessions
* You will find example commands in this workshop repositroy
    * **keep in mind** that these are examples! You should always familiarize yourself with a bioinformatics tool (read the publication, the GitHub README, ...)
    * we will mostly use default parameter settings if not otherwise stated
    * remember that `--help` and google (and ChatGPT) are your friends! 
* Please raise your hand to ask a question at any time
* We continue to work with the laptops you already used in the Illumina part
* In the future, you might also use the HPC (High-performance Cluster) at RKI, which we can also give a try during the course
    * Details about HPC usage can be found in the intranet (Confluence)

## Short Linux and bash re-cap

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
