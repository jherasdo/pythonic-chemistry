FROM deepnote/python:3.10

# Python version
ARG PYTHON_VERSION="3.10.12"

# Install base utilities
RUN apt-get update \
    && apt-get install -y build-essential \
    && apt-get install -y wget \
    && apt-get clean \
    && rm -rf /var/lib/apt/lists/*

# Installing conda
ENV CONDA_DIR /opt/conda
RUN wget https://repo.anaconda.com/miniconda/Miniconda3-latest-Linux-x86_64.sh -O ~/miniconda.sh && \
    /bin/bash ~/miniconda.sh -b -p /opt/conda

# Adding conda to Path and update
ENV PATH=$CONDA_DIR/bin:$PATH
RUN conda update conda

# Change python version
RUN conda install python=$PYTHON_VERSION

# Adding conda channels
RUN conda config --add channels conda-forge

# Installing mamba to speed up installation
RUN conda install -n base mamba --channel conda-forge
RUN conda clean --all -f -y

# Installing dependecies
RUN mamba install --quiet --yes \
    'pip' \
    'numpy' \
    'pandas' \
    'matplotlib' \
    'seaborn' \
    'ase' \
    'pymatgen' \ 
    'xtb' \
    'xtb-python' \
    'rdkit' \
    'scikit-learn' && \
    mamba clean --all -f -y

