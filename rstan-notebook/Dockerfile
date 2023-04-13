FROM jupyter/r-notebook:r-4.2.3
# Replace `latest` with an image tag from to ensure reproducible builds:
# https://hub.docker.com/r/jupyter/minimal-notebook/tags/
# Inspect the Dockerfile at:
# https://github.com/jupyter/docker-stacks/tree/HEAD/minimal-notebook/Dockerfile

# install additional package...
RUN mamba install --yes \
    'r-bh' \
    'r-rstan' \
    'r-bayesplot' \
    'r-loo' \
    'r-rstanarm' && \
    mamba clean --all -f -y && \
    fix-permissions "${CONDA_DIR}" && \
    fix-permissions "/home/${NB_USER}"

# set the default command of the image,
# if the parent image will not launch a jupyterhub singleuser server.
# The JupyterHub "Docker stacks" do not need to be overridden.
# Set either here or in `singleuser.cmd` in your values.yaml
# CMD ["jupyterhub-singleuser"]

