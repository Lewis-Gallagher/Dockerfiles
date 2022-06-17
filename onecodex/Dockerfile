FROM ubuntu:18.04

RUN apt-get update && apt-get -y install \
    python3.7 \
    python3-pip

RUN pip3 install --no-input --upgrade pip && \
    python3.7 -m pip install onecodex==0.10.0

ENV LC_ALL=C.UTF-8
ENV LANG=C.UTF-8
