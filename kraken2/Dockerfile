FROM ubuntu:16.04

LABEL Lewis Gallagher <lewis.gallagher@icr.ac.uk>

ENV KRAKEN_VERSION 2.1.2
ENV BRACKEN_VERSION 2.6.2

WORKDIR /

RUN apt-get update && apt-get -y install \
    bioperl \
    g++ \
    git \
    gzip \
    make \
    ncbi-blast+ \
    perl \
    python3 \
    wget

RUN wget https://github.com/DerrickWood/kraken2/archive/refs/tags/v${KRAKEN_VERSION}.tar.gz \
    -O kraken2_v${KRAKEN_VERSION}.tar.gz && tar -xf kraken2_v${KRAKEN_VERSION}.tar.gz

RUN wget https://github.com/jenniferlu717/Bracken/archive/refs/tags/v${BRACKEN_VERSION}.tar.gz \
    -O bracken2_v${BRACKEN_VERSION}.tar.gz && tar -xf bracken2_v${BRACKEN_VERSION}.tar.gz

RUN git clone https://github.com/jenniferlu717/KrakenTools.git

RUN ln -s /KrakenTools/*.py /usr/bin/

RUN cd kraken2-${KRAKEN_VERSION} && ./install_kraken2.sh /usr/bin/.

RUN sed -i "s#ftp://#https://#g" /usr/bin/rsync_from_ncbi.pl

WORKDIR /

RUN cd Bracken-${BRACKEN_VERSION}/ && bash install_bracken.sh /usr/bin/.

ENV PATH "$PATH:/kraken-${KRAKEN_VERSION}/scripts/"
ENV PATH "$PATH:/Bracken-${BRACKEN_VERSION}"
