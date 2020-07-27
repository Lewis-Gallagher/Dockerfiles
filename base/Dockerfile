FROM centos:centos7

#ENV http_proxy=http://10.101.112.70:8080
#ENV https_proxy=http://10.101.112.70:8080

LABEL base.image="pipelinemanager_base:v0.1"
LABEL maintainer="lewis.gallagher@icr.ac.uk"

ENV samtools_version=1.9

RUN yum -yq update && \
    yum -y install \
    bzip2 \
    bzip2-devel \
    g++ \
    gcc \
    git \
    java-1.8.0-openjdk \
    libcurl-devel \
    libbzip2-devel \
    liblzma-devel \
    make \
    perl \
    samtools-devel \
    samtools \
    wget \
    xz-devel \
    zlib-devel


RUN wget https://github.com/samtools/samtools/releases/download/${samtools_version}/samtools-${samtools_version}.tar.bz2 -O samtools.tar.bz2 && \
	tar xjvf samtools.tar.bz2 && \
	cd samtools-${samtools_version} && \
	./configure --without-curses -prefix=/usr/local/bim && \
	make && \
	make install && \
	ln -s /samtools-${samtools_version}/samtools /usr/local/bin/.


