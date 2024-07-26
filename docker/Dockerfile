FROM python:3.10-slim

SHELL ["/bin/bash", "-c", "-o", "pipefail"]

RUN apt-get update && apt-get upgrade
RUN apt-get install -y x11-apps x11-utils libx11-dev \
                        git

COPY ./src /sim_ws/src
COPY ./requirements.txt /sim_ws/requirements.txt
WORKDIR /sim_ws

RUN pip install --no-cache-dir -r /sim_ws/requirements.txt
