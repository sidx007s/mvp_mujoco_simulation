FROM python:3.12-slim

SHELL ["/bin/bash", "-c", "-o", "pipefail"]

RUN apt-get update && apt-get upgrade
RUN apt-get install -y x11-apps x11-utils libx11-dev \
                        git
RUN mkdir -p /sim_ws

COPY ./requirements.txt /sim_ws/requirements.txt
COPY ./src /sim_ws/src
COPY ./config /sim_ws/config

WORKDIR /sim_ws

RUN pip install -r requirements.txt
ENTRYPOINT ["python3", "src/mujoco_simulation.py"]

