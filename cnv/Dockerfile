FROM transgenmdx/base:v0.3

WORKDIR /

# Specify R version
#ENV R_VERSION 3.3.2

# Install Miniconda
RUN wget https://repo.anaconda.com/miniconda/Miniconda3-py37_4.8.3-Linux-x86_64.sh -O ~/miniconda.sh && \
    /bin/bash ~/miniconda.sh -b -p /opt/conda && \
    rm ~/miniconda.sh && \
    ln -s /opt/conda/etc/profile.d/conda.sh /etc/profile.d/conda.sh && \
    echo ". /opt/conda/etc/profile.d/conda.sh" >> ~/.bashrc && \
    echo "PATH=~/anaconda3/bin:$PATH" >> ~/.bashrc


# Create CNV conda env
COPY environment.yml .

RUN conda init bash && \
    . ~/.bashrc && \
    conda env create -f environment.yml