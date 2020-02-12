FROM centos:centos7

ENV http_proxy=http://10.101.112.70:8080
ENV https_proxy=http://10.101.112.70:8080

LABEL base.image="pipelinemanager_base:v0.1"
LABEL maintainer="lewis.gallagher@icr.ac.uk"

RUN yum -y update && \
    yum -y install g++ gcc git make java-1.8.0-openjdk perl samtools wget zlib-devel





