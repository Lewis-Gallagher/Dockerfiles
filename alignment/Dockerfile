FROM transgenmdx/base:v0.2


LABEL image="alignment_docker"
LABEL "description": "This is a docker container for bwa and the fgbio suite of tools."


ENV fgbio_version 0.6.1
ENV bwa_version v0.7.15
ENV picard_version 2.8.1

WORKDIR /

RUN git clone https://github.com/lh3/bwa && \
        cd bwa && \
        git checkout ${bwa_version} &&  \
        make && cp bwa /usr/local/bin/bwa

WORKDIR /usr/local/bin

RUN wget https://github.com/fulcrumgenomics/fgbio/releases/download/${fgbio_version}/fgbio-${fgbio_version}.jar && \
        mv fgbio-${fgbio_version}.jar fgbio.jar

RUN wget https://github.com/broadinstitute/picard/releases/download/${picard_version}/picard.jar
