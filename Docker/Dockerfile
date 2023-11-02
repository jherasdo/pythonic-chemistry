FROM condaforge/mambaforge

# Python version
ARG PYTHON_VERSION="3.10.12"

# Change python version
RUN mamba install --quiet --yes python=$PYTHON_VERSION ipykernel

# Adding conda channels
RUN mamba config --add channels conda-forge

# Installing dependecies
RUN mamba install --quiet --yes \
    'pip' \
    'ipython' \
    'numpy' \
    'pandas' \
    'matplotlib' \
    'seaborn' \
    'ase' \
    'pymatgen' \ 
    'xtb' \
    'xtb-python' \
    'rdkit' \
    'jupyter-jsmol' \
    'autode' \
    'scikit-learn' && \
    mamba clean --all -f -y


