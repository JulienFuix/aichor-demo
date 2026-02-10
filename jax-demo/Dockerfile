FROM nvidia/cuda:12.4.0-cudnn-runtime-ubuntu22.04

COPY --from=nvidia/cuda:12.4.0-cudnn-devel-ubuntu22.04 /usr/local/cuda/bin/ptxas /usr/local/cuda/bin/ptxas

RUN apt update
ENV DEBIAN_FRONTEND noninteractive
ENV PYTHONUNBUFFERED "yes"
RUN apt install -y python3 python3-pip s3cmd

WORKDIR /app

ADD requirements.txt .
RUN pip install -r requirements.txt --no-cache-dir

ADD ./src .