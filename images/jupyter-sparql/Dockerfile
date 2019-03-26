# Copyright (c) Jupyter Development Team.
# Distributed under the terms of the Modified BSD License.
ARG BASE_CONTAINER=jupyter/base-notebook:7f1482f5a136
FROM $BASE_CONTAINER

LABEL maintainer="Damien T. <damientprof@gmail.com>"

USER root

# Install all OS dependencies for fully functional notebook server
RUN apt-get update && apt-get install -yq --no-install-recommends \
    graphviz \
    && pip install sparqlkernel \
    && rm -rf /var/lib/apt/lists/*

# Switch back to jovyan to avoid accidental container runs as root
USER $NB_UID

RUN jupyter sparqlkernel install --user
