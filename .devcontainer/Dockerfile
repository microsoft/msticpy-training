# See here for image contents: https://hub.docker.com/r/jupyter/scipy-notebook
FROM jupyter/minimal-notebook
LABEL maintainer="Msticpy Dev Team <msticpy@microsoft.com>"

USER ${NB_UID}

# Add conda to path
ENV PATH /opt/conda/envs/env/bin:$PATH

# Environment variable for Pip and conda packages to be installed
ENV INSTALL_CONDA_PACKAGES jupyter_contrib_nbextensions jupyterthemes phantomjs autopep8 plotly black rise
ENV INSTALL_PIP_PACKAGES azure-cli jupyterlab-git setuptools_git

# Install conda and pip packages
# Download maxmind database to msticpy pacakge directory
# Clone msticpy and Azure sentinel github directories
RUN conda install --quiet --yes ${INSTALL_CONDA_PACKAGES} && \
    pip install --upgrade --quiet ${INSTALL_PIP_PACKAGES} && \
    #installing Msticpy requirements and dependencies
    git clone https://github.com/microsoft/msticpy.git && \
    git clone https://github.com/microsoft/msticpy-training.git && \
    pip install --requirement /home/jovyan/msticpy/requirements-all.txt

ENV MSTICPYCONFIG /home/jovyan/msticpy-training/workshops/Oct2022/msticpyconfig.yaml

# Activate ipywidgets extension in the environment that runs the notebook server
RUN jupyter nbextension enable --py widgetsnbextension --sys-prefix && \
    jupyter nbextension enable toc2/main --sys-prefix && \
    jupyter nbextension enable execute_time/ExecuteTime --sys-prefix && \
    jupyter nbextension enable python-markdown/main --sys-prefix && \
    jupyter nbextension enable codefolding/main --sys-prefix && \
    jupyter nbextension enable autosavetime/main --sys-prefix && \
    jupyter nbextension enable tree-filter/index --sys-prefix && \
    jupyter nbextension enable hide_input_all/main --sys-prefix && \
    jupyter nbextension enable hinterland/hinterland --sys-prefix && \
    jupyter nbextension enable varInspector/main --sys-prefix && \
    jupyter nbextension enable spellchecker/main --sys-prefix && \
    jupyter nbextension enable toggle_all_line_numbers/main --sys-prefix && \
    jupyter nbextension install https://github.com/drillan/jupyter-black/archive/master.zip --sys-prefix && \
    jupyter nbextension install --py nbdime --sys-prefix && \
    jupyter nbextension enable jupyter-black-master/jupyter-black --sys-prefix && \
    jupyter nbextension enable nbdime --py --sys-prefix && \
    jupyter nbextension enable rise --py --sys-prefix && \
    jupyter nbextensions_configurator enable --sys-prefix && \
    jupyter labextension install @jupyterlab/git --no-build && \
    jupyter labextension install @jupyterlab/github --no-build && \
    jupyter labextension enable git && \
    jupyter lab build --dev-build=False

USER ${NB_UID}

WORKDIR "/home/jovyan/msticpy-training/workshops/Oct2022"