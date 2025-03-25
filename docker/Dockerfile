# For more information, please refer to https://aka.ms/vscode-docker-python
FROM python:3-slim-bullseye

RUN apt-get update && \
    apt-get upgrade --yes

RUN useradd --system --user-group \
    --home-dir /home/app \
    --shell /bin/bash \
    app \
    ;

USER app
WORKDIR /home/app

ENV VIRTUALENV=/home/realpython/venv
RUN python3 -m venv $VIRTUALENV
ENV PATH="$VIRTUALENV/bin:$PATH" easier container logging

ENV PYTHONUNBUFFERED=1

RUN python -m pip install --upgrade pip 

WORKDIR /opt/app

COPY . .