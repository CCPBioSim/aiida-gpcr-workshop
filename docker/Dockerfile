# Start with BioSim base image.
ARG BASE_IMAGE=latest@sha256:5eb67b09e3fdf64b3128bd9501e08a0cbb007804b678f2096728d8c1260e6217
FROM ghcr.io/ccpbiosim/jupyterhub-base:$BASE_IMAGE

LABEL maintainer="James Gebbie-Rayet <james.gebbie@stfc.ac.uk>"
ARG TARGETPLATFORM

# Install curl and unzip
RUN apt-get update --yes && \
    apt-get install --yes --no-install-recommends \
    curl \
    unzip && \
    apt-get clean && rm -rf /var/lib/apt/lists/* && \

USER $NB_USER
WORKDIR $HOME

# Python Dependencies for the md_workshop
RUN conda install -y -c conda-forge \
    conda-forge::aiida-core=2.9.2 \
    conda-forge::aiida-gromacs=2.2.2 \
    conda-forge::gromacs=2026.3=nompi_*
RUN pip install --no-cache-dir \
    mdtraj==1.11.1.post2 \
    vermouth==0.15.0

RUN git clone https://github.com/PSDI-UK/aiida-gromacs.git && \
    mv aiida-gromacs/examples/PTH2R_coarse-grained_files . && \
    mv aiida-gromacs/notebooks/PTH2R_coarse-grained_tutorial.ipynb . && \
    rm -rf aiida-gromacs

RUN echo "./aiida-start" >> ~/.bashrc
COPY --chown=1000:100 docker/default-37a8.jupyterlab-workspace /home/jovyan/.jupyter/lab/workspaces/default-37a8.jupyterlab-workspace

# Always finish with non-root user as a precaution.
USER $NB_USER
