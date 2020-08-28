FROM transgenmdx/base:v0.4

WORKDIR /

# Install Miniconda
RUN wget https://repo.anaconda.com/archive/Anaconda3-4.4.0-Linux-x86_64.sh -O ~/anaconda.sh && \
    /bin/bash ~/anaconda.sh -b -p /opt/conda && \
    rm ~/anaconda.sh && \
    echo "export PATH="/opt/conda/bin:$PATH"" >> ~/.bashrc && \
    /bin/bash -c "source ~/.bashrc"

ENV PATH /anaconda3/bin:$PATH

# Create CNV conda env
COPY environment.yml .

RUN . ~/.bashrc && \
    conda create --name test_env
