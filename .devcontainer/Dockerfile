# See here for image contents: https://github.com/microsoft/vscode-dev-containers/tree/v0.245.2/containers/python-3/.devcontainer/base.Dockerfile

# [Choice] Python version (use -bullseye variants on local arm64/Apple Silicon): 3, 3.10, 3.9, 3.8, 3.7, 3.6, 3-bullseye, 3.10-bullseye, 3.9-bullseye, 3.8-bullseye, 3.7-bullseye, 3.6-bullseye, 3-buster, 3.10-buster, 3.9-buster, 3.8-buster, 3.7-buster, 3.6-buster
ARG VARIANT="3.10.7-bullseye"
FROM mcr.microsoft.com/vscode/devcontainers/python:0-${VARIANT}

# ENV PYTHONBUFFERED=1 \
#     PYTHONDONTWRITEBYTECODE=1

# RUN apt-get update
# RUN apt-get install -y build-essential \
#     libssl-dev \ 
#     libffi-dev
# RUN apt-get install -y ca-certificates
# COPY /cert/Norwegian_Research_Centre_Root_CA.cer /usr/local/share/ca-certificates/NORCE_ROOT_CA.crt
# RUN update-ca-certificates

# RUN pip config set global.cert /usr/local/share/ca-certificates/NORCE_ROOT_CA.crt

USER vscode

ADD ./cert ./cert

# Handle SSL-Decrypt...
# RUN apt-get update && apt-get -y update &&\
#     apt-get install -y ca-certificates && \
#     update-ca-certificates

COPY requirements.txt ./
# RUN pip install --trusted-host pypi.org --trusted-host pypi.python.org --trusted-host files.pythonhosted.org --no-cache-dir -r requirements.txt
RUN pip config set global.cert /cert/NORCE_CA.cer && \
    pip install --no-cache-dir -r requirements.txt

# ADD /cert/Norwegian_Research_Centre_Root_CA.cer /usr/local/share/ca-certificates/NORCE_ROOT_CA.crt
# RUN chmod 644 /usr/local/share/ca-certificates/NORCE_ROOT_CA.crt && update-ca-certificates


# [Choice] Node.js version: none, lts/*, 16, 14, 12, 10
ARG NODE_VERSION="none"
RUN if [ "${NODE_VERSION}" != "none" ]; then su vscode -c "umask 0002 && . /usr/local/share/nvm/nvm.sh && nvm install ${NODE_VERSION} 2>&1"; fi




# [Optional] If your pip requirements rarely change, uncomment this section to add them to the image.
# COPY requirements.txt /tmp/pip-tmp/
# RUN pip3 --disable-pip-version-check --no-cache-dir install -r /tmp/pip-tmp/requirements.txt \
#    && rm -rf /tmp/pip-tmp

# RUN pip install numpy

# [Optional] Uncomment this section to install additional OS packages.
# RUN apt-get update && export DEBIAN_FRONTEND=noninteractive \
    # && apt-get -y install --no-install-recommends <your-package-list-here>


# [Optional] Uncomment this line to install global node packages.
# RUN su vscode -c "source /usr/local/share/nvm/nvm.sh && npm install -g <your-package-here>" 2>&1