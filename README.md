# PSDI AiiDA GPCR Workshop

[aiida-gpcr](https://github.com/ccpbiosim/aiida-gpcr-workshop)
[![ci](https://github.com/ccpbiosim/aiida-gpcr-workshop/actions/workflows/build.yaml/badge.svg?branch=main)](https://github.com/ccpbiosim/aiida-gpcr-workshop/actions/workflows/build.yaml)
[![latest](https://img.shields.io/badge/dynamic/json?url=https%3A%2F%2Fccpbiosim.github.io%2Fworkshop.json&query=%24.containers.aiida-gpcr-workshop.latest&labelColor=grey&logo=github&logoColor=white&label=latest&color=purple)](https://github.com/ccpbiosim/aiida-gpcr-workshop/pkgs/container/aiida-gpcr-workshop)
[![issues](https://img.shields.io/github/issues/ccpbiosim/aiida-gpcr-workshop?logo=github&labelColor=grey)](https://github.com/CCPBioSim/aiida-gpcr-workshop/issues)
[![pr](https://img.shields.io/github/issues-pr/ccpbiosim/aiida-gpcr-workshop?logo=github&labelColor=grey)](https://github.com/CCPBioSim/aiida-gpcr-workshop/pulls)

This workshop source repository contains the build recipe for a docker container derived from the CCPBioSim JupyterHub image. This container adds the necessary software packages and notebook content to form a deployable course container. The source content for this course can be found at https://github.com/PSDI-UK/aiida-gromacs

## How to Use

This training course is deployed on the [CCPBioSim](www.ccpbiosim.ac.uk) website via our cloud infrastructure, however you can deploy on your own machine with docker.

Pull the container from our repository::

    docker pull ghcr.io/ccpbiosim/aiida-gpcr-workshop:latest

In our containers we are using the JupyterHub default port 8888, so you should
forward this port when deploying locally::

    docker run -p 8888:8888 ghcr.io/ccpbiosim/aiida-gpcr-workshop:latest

## Authors

Workshop Content Authors:

- Jas Kalayan

## Contact

Please direct all comments and queries to [Jas Kalayan](mailto:jas.kalayan@stfc.ac.uk)
