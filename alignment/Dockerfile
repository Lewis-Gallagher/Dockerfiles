FROM transgenmdx/base:v0.3

LABEL image="alignment_docker"
LABEL "description": "This is a docker container for bwa and the fgbio suite of tools."

ENV FGBIO_VERSION 0.6.1
ENV BWA_VERSION 0.7.15

WORKDIR /

RUN git clone https://github.com/lh3/bwa && \
    cd bwa && \
    git checkout ${BWA_VERSION} &&  \
    make && \
    ln -s bwa /usr/local/bin/bwa

RUN wget https://github.com/fulcrumgenomics/fgbio/releases/download/${FGBIO_VERSION}/fgbio-${FGBIO_VERSION}.jar -O /usr/local/bin/fgbio.jar && \
    wget https://github.com/broadinstitute/picard/releases/download/${PICARD_VERSION}/picard.jar -O /usr/local/bin/picard.jar
