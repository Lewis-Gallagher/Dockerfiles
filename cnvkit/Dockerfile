FROM ubuntu:18.04

LABEL \
    description="Custom container to install version 0.3.5 of CNVkit not available on the author's dockerhub as well as pip and R dependencies" \
    maintainer="lewis.gallagher@icr.ac.uk" 

ENV CNVKIT_VERSION 0.3.5
# Removes need to choose region information when selecting mirrors on command-line
ENV DEBIAN_FRONTEND=noninteractive 

# Change working directory to root
WORKDIR /

# Install dependancies. Please try to maintain alphabetical order, it makes it easy to read :)
RUN apt -y update && \
    apt -y install \
        libz-dev \
        libfreetype6-dev \
        python-pip \
        python-tk \
        r-base

# Install numpy. Ensuring pip and setuptools are up to date.
RUN pip install --upgrade pip && pip install --upgrade setuptools && \
    pip install numpy==1.6

# Install the rest of the dependencies
RUN pip install \
        biopython==1.76 \
        cnvkit==0.3.5 \
        matplotlib==1.1 \
        pysam==0.8.4 \
        reportlab==3.0

# Set up R dependencies
RUN R -e "options(needs.promptUser = FALSE); \
    source('http://bioconductor.org/biocLite.R'); \
    biocLite('DNAcopy'); \
    biocLite('aroma.light'); \
    install.packages(c('PSCBS', 'matrixStats', 'cghFLasso'))"

