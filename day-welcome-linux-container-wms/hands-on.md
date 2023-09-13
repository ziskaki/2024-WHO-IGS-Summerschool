# Workshop: Linux re-cap, Container, and WMS

## Hands-on

### Install and use analysis tools

* **Note**: Bioinformatics tools are regulary updated and input parameters might change (use `--help` or `-h` to see the manual for a tool!)
* Install most of them into our environment
    * we will already install many tools that we will use over the next days!

```bash
mkdir envs
mamba create -y -p envs/workshop fastqc nanoplot filtlong flye bandage minimap2 tablet racon samtools igv
conda activate envs/workshop
# test
NanoPlot --help
flye --version
```

__Reminder: You can also install specific versions of a tool!__
* important for full reproducibility
* e.g. `mamba install flye==2.9.0`
* per default, `mamba` will try to install the newest tool version based on your configured channels and system architecture and dependencies to other tools

### Create a folder for the hands-on work

Below are just example paths, you can also adjust them and use other folder names! Assuming you are on a Linux system on a local machine (laptop, workstation):

```sh
# Switch to a path on your system where you want to store your data and results
cd /scratch/$USER
# Create new folder
mkdir nanopore-workshop
cd nanopore-workshop
```

### Container and WMS (brief intro)

Check the small example at [https://github.com/hoelzer/nf_example](https://github.com/hoelzer/nf_example). Clone the repository using `git`. 

Then investigate the `Dockerfile` and try to build the container image locally using `docker build .`. Remember that you can also give your container image a specific name using the `-t` parameter. 

Install `nextflow`, for example directly from [https://nextflow.io/](https://nextflow.io/) or using `conda` or `mamba`. 

Try to get the little `nextflow` example workflow running. The workflow is using `sourmash` so you either need to install the dependency or provide an available container image, see these [code lines](https://github.com/hoelzer/nf_example/blob/master/main.nf#L14-L18). 
