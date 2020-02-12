FROM lewis_base:v0.1


LABEL image="bwa_docker"
LABEL "description": "This is a docker container for the fgbio suite of tools."


ENV fgbio_version 1.1.0
ENV bwa_version v0.7.15


RUN git clone https://github.com/lh3/bwa && \
        cd bwa && \
        git checkout ${bwa_version} &&  \
        make && cp bwa /usr/bin/bwa

WORKDIR /usr/bin


RUN wget https://github.com/fulcrumgenomics/fgbio/releases/download/${fgbio_version}/fgbio-${fgbio_version}.jar && \
        mv fgbio-${fgbio_version}.jar fgbio.jar


WORKDIR /usr/bin
