FROM centos:centos7

#ENV http_proxy=http://10.101.112.70:8080
#ENV https_proxy=http://10.101.112.70:8080

LABEL base.image="pipelinemanager_base:v0.3"
LABEL maintainer="lewis.gallagher@icr.ac.uk"

ENV SAMTOOLS_VERSION 1.9
ENV PICARD_VERSION 2.8.1

RUN yum -y -q update && \
     yum -y install \
     bzip2 \
     gcc \
     git \
     java-1.8.0-openjdk \
     java-1.8.0-openjdk-devel \
     libcurl-devel \
     make \
     perl \
     unzip \
     wget \
     xz-devel \
     zlib-devel

RUN wget https://github.com/samtools/samtools/releases/download/${SAMTOOLS_VERSION}/samtools-${SAMTOOLS_VERSION}.tar.bz2 -O samtools.tar.bz2 && \
	tar xjvf samtools.tar.bz2 && \
	cd samtools-${SAMTOOLS_VERSION} && \
	./configure --without-curses -prefix=/usr/local/bim && \
	make && \
	make install && \
	ln -s /samtools-${SAMTOOLS_VERSION}/samtools /usr/local/bin/. && \
	wget https://github.com/broadinstitute/picard/releases/download/${PICARD_VERSION}/picard.jar -O /usr/local/bin/picard.jar



