# Workshop: Container and WMS

## Hands-on

Check the small example at [https://github.com/hoelzer/nf_example](https://github.com/hoelzer/nf_example). Clone the repository using `git`. 

Then investigate the `Dockerfile` and try to build the container image locally using `docker build .`. Remember that you can also give your container image a specific name using the `-t` parameter. 

Install `nextflow`, for example directly from [https://nextflow.io/](https://nextflow.io/) or using `conda` or `mamba`. 

Try to get the little `nextflow` example workflow running. The workflow is using `sourmash` so you either need to install the dependency or provide an available container image, see these [code lines](https://github.com/hoelzer/nf_example/blob/master/main.nf#L14-L18). 
