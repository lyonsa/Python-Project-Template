# For more information, please refer to https://aka.ms/vscode-docker-python
FROM python:3-slim-bullseye

RUN useradd --system --user-group \
    --home-dir /home/app \
    --shell /bin/bash \
    app \
    ;

USER app
WORKDIR /home/app

RUN apt-get update -- yes && \
    apt-get install --yes --no-install-recommends\
    sudo \
    ;

COPY . .

ENV VIRTUALENV=/home/app/venv
RUN python3 -m venv $VIRTUALENV
ENV PATH="$VIRTUALENV/bin:$PATH"

ENV PYTHONUNBUFFERED=1

WORKDIR /opt/app

RUN pip install --no-cache-dir \
    --report report.json \
    .
