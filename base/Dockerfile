FROM centos:centos7

ENV http_proxy=http://10.101.112.70:8080
ENV https_proxy=http://10.101.112.70:8080

LABEL base.image="pipelinemanager_base:v0.1"
LABEL maintainer="lewis.gallagher@icr.ac.uk"

RUN yum -y update && \
    yum -y install bzip2 \
    bzip2-devel \
    g++ \
    gcc \
    git \
    java-1.8.0-openjdk \
    libbzip2-devel \
    liblzma-devel \
    make \
    perl \
    wget \
    xz-devel \
    zlib-devel

ENV SAMTOOLS_INSTALL_DIR=/opt/samtools

WORKDIR /tmp
RUN wget https://github.com/samtools/samtools/releases/download/1.10/samtools-1.10.tar.bz2 && \
    tar --bzip2 -xf samtools-1.10.tar.bz2

WORKDIR /tmp/samtools-1.10
RUN ./configure --without-curses --prefix=$SAMTOOLS_INSTALL_DIR && \
    make all all-htslib && \
    make install install-htslib

WORKDIR /
RUN ln -s $SAMTOOLS_INSTALL_DIR/bin/samtools /usr/bin/samtools && \
    rm -rf /tmp/samtools-1.9
