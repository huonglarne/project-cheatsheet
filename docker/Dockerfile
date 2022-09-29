FROM python:3.8.12-slim AS base_image
ENV PIP_NO_CACHE_DIR=off \
    PIP_DISABLE_PIP_VERSION_CHECK=on \
    PIP_DEFAULT_TIMEOUT=100

ARG USERNAME=lc_dev
ARG USER_UID=1006
ARG USER_GID=1007
ARG WORK_DIR=/home/$USERNAME

ENV DEBIAN_FRONTEND noninteractive
RUN apt-get update && \
    apt-get -y install gcc && \
    apt-get -y install openssh-client && \
    rm -rf /var/lib/apt/lists/*

# Create the user
RUN groupadd --gid $USER_GID $USERNAME \
    && useradd --create-home --shell /bin/bash --uid $USER_UID --gid $USER_GID -m $USERNAME

USER $USERNAME
WORKDIR $WORK_DIR

# venv + poetry
ENV VENV_PATH=$WORK_DIR/venv
ENV PATH="$VENV_PATH/bin:$PATH"
RUN python -m venv $VENV_PATH
RUN python -m pip install --upgrade pip setuptools wheel poetry==1.1.15

copy just the reqs (rarely change)
COPY --chown=$USERNAME pyproject.toml poetry.lock .env ./

# install deps
SHELL ["/bin/bash", "-c"]
RUN source .env \
    && poetry config virtualenvs.create false \
    && poetry install --no-interaction --no-ansi -vvv

CMD ["/bin/bash"]
