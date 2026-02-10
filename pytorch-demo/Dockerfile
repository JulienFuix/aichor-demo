FROM pytorch/pytorch:2.10.0-cuda13.0-cudnn9-runtime

RUN mkdir -p /opt/app/src
WORKDIR /opt/app

COPY requirements.txt .
RUN pip install -r requirements.txt

COPY src/main.py src/