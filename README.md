# External Software for the DCAN Labs pipelines.
The repository contains the Dockerfile to create a Docker image
of external software used by a dcan-pipeline.

## Installation
In order to run this software via a container, you will need to acquire a copy
of the FreeSurfer License for yourself from:

'https://surfer.nmr.mgh.harvard.edu/fswiki/License'


## Using Docker
Before running, you will need to load the image onto your Docker service by
running the following command:
```
docker pull dcanlabs/external-software
```
If you receive a "no space left on device" error during this pull process, you
may need to clean up any old/dangling images and containers from the docker
registry, and possibly increase the amount of space allocated to Docker.

## Using Singularity
You can either pull the image from the Docker repository:
```
singularity pull docker://dcanlabs/abcd-hcp-pipeline
```
Or build it from the repository for the image to be saved in the working
directory:
```
singularity build abcd-hcp-pipeline.img docker://dcanlabs/abcd-hcp-pipeline
```
These are essentially the same, but in the latter case you have control over the
name of the file.

Notice that there is no entrypoint for this container. It is meant to be used to
build the next level of the DCAN pipelines: internal-tools.


