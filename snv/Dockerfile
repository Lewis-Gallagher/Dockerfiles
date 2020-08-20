FROM transgenmdx/base:v0.3

LABEL image="snv_docker"

WORKDIR /

ENV GATK_VERSION 4.0.5.1
ENV VARDICT_VERSION 1.5.8

RUN wget --quiet https://github.com/AstraZeneca-NGS/VarDictJava/releases/download/v${VARDICT_VERSION}/VarDict-${VARDICT_VERSION}.zip -O VarDict.zip && \
    unzip VarDict.zip && \
    rm VarDict.zip

RUN wget --quiet https://github.com/broadinstitute/gatk/releases/download/${GATK_VERSION}/gatk-${GATK_VERSION}.zip && \
    unzip gatk-${GATK_VERSION}.zip && \
    rm gatk-${GATK_VERSION}.zip && \
    ln -s gatk-${GATK_VERSION}/gatk /usr/local/bin/gatk

ENV PATH "$PATH:/VarDict-1.5.8/bin/"
ENV JAVA_HOME "/usr/lib/jvm/java-1.8.0-openjdk-1.8.0.262.b10-0.el7_8.x86_64/"
