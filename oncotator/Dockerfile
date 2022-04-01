FROM ubuntu:18.04

LABEL \
    author="lewis.gallagher@icr.ac.uk" \
    description="Installs version 1.9.9.0 of Oncotator via miniconda"

# Install base dependencies.
RUN apt-get -y update && apt-get -y install --no-install-recommends \
    make \
    git \
    ca-certificates \
    build-essential \
    software-properties-common \
    wget

# Get miniconda - miniconda over anaconda to keep this as light-weight as possible.
RUN wget https://repo.anaconda.com/miniconda/Miniconda2-4.6.14-Linux-x86_64.sh

# Set up miniconda.
RUN sh Miniconda2-4.6.14-Linux-x86_64.sh -b -p /usr/local/anaconda/PYTHON2

# Only version 1.9.9.0 is available however this shouldn't matter.
RUN /usr/local/anaconda/PYTHON2/bin/conda install \
    -c anaconda \
    -c conda-forge \
    -c bioconda \
        oncotator==1.9.9.0

# Add our miniconda bin folder to container's path.
ENV PATH /usr/local/anaconda/PYTHON2/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
