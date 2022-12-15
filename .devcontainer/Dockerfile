# See here for image contents: https://github.com/microsoft/vscode-dev-containers/tree/v0.245.2/containers/python-3/.devcontainer/base.Dockerfile

# [Choice] Python version (use -bullseye variants on local arm64/Apple Silicon): 3, 3.10, 3.9, 3.8, 3.7, 3.6, 3-bullseye, 3.10-bullseye, 3.9-bullseye, 3.8-bullseye, 3.7-bullseye, 3.6-bullseye, 3-buster, 3.10-buster, 3.9-buster, 3.8-buster, 3.7-buster, 3.6-buster
ARG VARIANT="3.10-bullseye"
FROM mcr.microsoft.com/vscode/devcontainers/python:0-${VARIANT}

#COPY requirements.txt /tmp/
#RUN pip install -r /tmp/requirements.txt

RUN pip install poetry

# RUN chown -R vscode:vscode /home/vscode/.config && \
#     /usr/local/py-utils/bin/poetry completions bash > /etc/bash_completion.d/poetry.bash-completion && \
#     python -m venv /workspace/.venv --prompt feria && \
#     chown -R vscode:vscode /workspace/.venv

COPY .devcontainer/config/pypoetry_config.toml /home/vscode/.config/pypoetry/config.toml

RUN chown -R vscode:vscode /home/vscode/.config && \
    poetry completions bash > /etc/bash_completion.d/poetry.bash-completion


# [Optional] Uncomment this section to install additional OS packages.
# RUN apt-get update && export DEBIAN_FRONTEND=noninteractive \
#     && apt-get -y install --no-install-recommends <your-package-list-here>

# [Optional] Uncomment this line to install global node packages.
# RUN su vscode -c "source /usr/local/share/nvm/nvm.sh && npm install -g <your-package-here>" 2>&1
