FROM centos:centos7

LABEL \
    author="lewis.gallagher@icr.ac.uk" \
    description="Installs Samtools 0.1.18 and dependencies"

# Software versions
ENV SAMTOOLS_VERSION 0.1.18

# Change working directory to root
WORKDIR /

# Install dependancies. Please try to maintain alphabetical order, it makes it easy to read :)
RUN yum -y update && \
     yum -y install \
        autoconf \
        automake \
        bzip2 \
        bzip2-devel \
        curl-devel \
        gcc \
        libcurl-devel \
        make \
        ncurses-devel \
        openssl-devel \
        unzip \
        wget \
        xz-devel \
        zlib-devel

# Install Samtools
RUN wget https://github.com/samtools/samtools/archive/refs/tags/${SAMTOOLS_VERSION}.tar.gz && \
    tar -xvf ${SAMTOOLS_VERSION}.tar.gz && \
    cd samtools-${SAMTOOLS_VERSION} && \
    make && \
    cp samtools /usr/local/bin && cp bcftools/bcftools /usr/local/bin
