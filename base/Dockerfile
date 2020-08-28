FROM centos:centos7

#ENV http_proxy=http://10.101.112.70:8080
#ENV https_proxy=http://10.101.112.70:8080

LABEL maintainer="lewis.gallagher@icr.ac.uk"

ENV SAMTOOLS_VERSION 1.9
ENV BCFTOOLS_VERSION 1.10.2
ENV PICARD_VERSION 2.8.1

WORKDIR /

RUN yum -y update && \
     yum -y install \
        autoconf \
        automake \
        bzip2 \
        bzip2-devel \
        curl-devel \
        gcc \
        git \
        gsl-devel \
        java-1.8.0-openjdk \
        java-1.8.0-openjdk-devel \
        libbzip2-devel \
        libcurl-devel \
        make \
        ncurses-devel \
        openssl-devel \
        perl \
        perl-Data-Dumper \
        perl-ExtUtils-Embed \
        r-base \
        tabix \
        unzip \
        wget \
        xz-devel \
        zlib-devel

RUN wget https://github.com/samtools/samtools/releases/download/${SAMTOOLS_VERSION}/samtools-${SAMTOOLS_VERSION}.tar.bz2 && \
	tar xjvf samtools-${SAMTOOLS_VERSION}.tar.bz2 && \
	cd samtools-${SAMTOOLS_VERSION} && \
	./configure && \
	make all all-htslib && \
	make install install-htslib



RUN wget https://github.com/samtools/bcftools/releases/download/${BCFTOOLS_VERSION}/bcftools-${BCFTOOLS_VERSION}.tar.bz2 && \
    tar xjvf bcftools-${BCFTOOLS_VERSION}.tar.bz2 && \
    cd bcftools-${BCFTOOLS_VERSION} && \
    ./configure --prefix=/usr/local && \
    make && \
    make install
#    ln -s bcftools-${BCFTOOLS_VERSION}/htslib-${BCFTOOLS_VERSION}/bgzip /usr/local/bin && \
#    ln -s bcftools-${BCFTOOLS_VERSION}/htslib-${BCFTOOLS_VERSION}/tabix /usr/local/bin

RUN wget https://github.com/broadinstitute/picard/releases/download/${PICARD_VERSION}/picard.jar -O /usr/local/bin/picard.jar
