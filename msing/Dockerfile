FROM ubuntu:18.04

LABEL 
    author="lewis.gallagher@icr.ac.uk" \
    description="Installs v3.1 (b8c10cf) of mSINGS, and VarScan v2.3.7.  Dependencies installed via miniconda."

# Install base dependencies.
RUN apt-get -y update && apt-get -y install --no-install-recommends \
    build-essential \
    ca-certificates \
    cmake \
    g++ \
    gfortran \
    git \
    libgsl0-dev \
    libncurses5-dev \
    make \
    scons \
    software-properties-common \
    wget

#RUN apt-get -y install scons g++ cmake libgsl0-dev libncurses5-dev gfortran

# Get java.
ENV JAVA_HOME=/usr/lib/jvm/java-8-openjdk-amd64

RUN add-apt-repository ppa:openjdk-r/ppa -y && \
    apt-get update && \
    apt-get install -y --no-install-recommends \
        openjdk-8-jdk && \
        rm -rf /var/lib/apt/lists/*

# Get miniconda.
RUN wget https://repo.anaconda.com/miniconda/Miniconda2-4.6.14-Linux-x86_64.sh

RUN sh Miniconda2-4.6.14-Linux-x86_64.sh -b -p /usr/local/anaconda/PYTHON2

# Install msings dependencies via miniconda.
RUN /usr/local/anaconda/PYTHON2/bin/conda install \
    -c anaconda  \
    -c conda-forge \
    -c bioconda \
    -c r \
        samtools==0.1.18 \
        varscan==2.3.7 	\
        numpy==1.11.1 \
        virtualenv==15.1.0 \
        pandas==0.19.2

# Add miniconda bin folder to path.
ENV PATH=/usr/local/anaconda/PYTHON2/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin

RUN cd /usr/local/bin && \
    git clone  https://bitbucket.org/uwlabmed/msings.git && \
    cd msings && \
    git checkout v3.1 && \
    python setup.py install

