FROM ubuntu:18.04

MAINTAINER lewis.gallagher@icr.ac.uk

ARG STAR_VERSION=6.1.2

ENV PACKAGES wget

RUN apt-get update && \
    apt-get install -y --no-install-recommends ${PACKAGES} 

RUN wget --no-check-certificate -O cellranger-6.1.2.tar.gz "https://cf.10xgenomics.com/releases/cell-exp/cellranger-6.1.2.tar.gz?Expires=1644361685&Policy=eyJTdGF0ZW1lbnQiOlt7IlJlc291cmNlIjoiaHR0cHM6Ly9jZi4xMHhnZW5vbWljcy5jb20vcmVsZWFzZXMvY2VsbC1leHAvY2VsbHJhbmdlci02LjEuMi50YXIuZ3oiLCJDb25kaXRpb24iOnsiRGF0ZUxlc3NUaGFuIjp7IkFXUzpFcG9jaFRpbWUiOjE2NDQzNjE2ODV9fX1dfQ__&Signature=dtrjD3aq-dfdc~UyvlJ9ex25WccULMdz3h0rpg1Dv8JgxBQXMawHNOj-vblBxajQtmtYJTdGvmuLZIe~7wKC6EBEuAfSKdgPHHHCxBGvX~QwVwN9OTbHxa8scvnUYLNiY~6kYVywaRKfpDC-9gXTiuso5sg8CpyYpLnuZ9ugcLhpGg1gzGGQfNwogIaO-WZld47LKKyfRR2tFNGh2~Ui8aH6xk4IiIoIEUu~FM4Yn~yJhWvjYcB7XlY6ptRCw5NiEudwlc~OlHPmEkxjVc4fufOaEiKtROMifekPdrtJgWfaPF4J8TD4ZCaICIzQ0IwAjIV0WohmChQJ5jJ213ljEg__&Key-Pair-Id=APKAI7S6A5RYOXBWRPDA"

RUN tar -xzvf cellranger-6.1.2.tar.gz

ENV PATH /cellranger-6.1.2:$PATH
