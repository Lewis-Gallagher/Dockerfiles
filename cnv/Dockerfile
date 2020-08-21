FROM transgenmdx/base:v0.3

WORKDIR /

ENV R_VERSION 3.3.2

RUN curl -O https://cdn.rstudio.com/r/centos-7/pkgs/R-${R_VERSION}-1-1.x86_64.rpm

RUN yum -y -q update && \
    yum -y install \
        epel-release

RUN yum install -y R-${R_VERSION}-1-1.x86_64.rpm

RUN R -e "install.packages('HMMcopy',dependencies=TRUE, repos='http://cran.rstudio.com/')"