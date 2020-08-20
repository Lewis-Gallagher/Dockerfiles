FROM transgenmdx/base:v0.3

LABEL image="snv_docker"

ENV GATK_VERSION 4.0.5.1
ENV VARDICT_VERSION 1.5.8

RUN yum install -y -q \
    r-base && \
    perl &&\
    tabix

WORKDIR /usr/local/bin

RUN wget -q https://github.com/AstraZeneca-NGS/VarDictJava/releases/download/v${VARDICT_VERSION}/VarDict-${VARDICT_VERSION}.zip -O VarDict.zip && \
    unzip VarDict-${VARDICT_VERSION}.zip && \
    rm VarDict-${VARDICT_VERSION}.zip && \
    cd VarDict-${VARDICT_VERSION} && \
    ./gradlew clean installApp

RUN wget -q https://github.com/broadinstitute/gatk/releases/download/${GATK_VERSION}/gatk-${GATK_VERSION}.zip && \
    unzip gatk-${GATK_VERSION}.zip && \



