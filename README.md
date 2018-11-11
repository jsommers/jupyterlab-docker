# jupyterlab-docker

This is a docker container based on debian:latest, with miniconda3 (latest; 3.7) and jupyterlab installed.  It is based on continuumio's miniconda3 docker container, but uses the miniconda3 installed with Python 3.7, not 3.5

The Miniconda distribution is installed into the /opt/conda folder and ensures that the default user has the conda command in their path.

# usage

You can download this image with:

    docker pull jsommers/jupyterlab

And run the image with:

    docker run -i -p 8888:8888 -v `pwd`:/notebooks -t jsommers/jupyterlab /bin/bash -c "mkdir -p /notebooks && cd /notebooks && jupyter-lab --notebook-dir=/notebooks --ip=0.0.0.0 --port 8888 --no-browser --allow-root"

The command above will map the directory `/notebooks` within the docker image to your current working directory so that any notebooks can be saved in the host machine file system.  

Then, follow the prompt left by jupyter-lab: it will provide the URL to connect to via a browser on the host machine (http://localhost:8888).

