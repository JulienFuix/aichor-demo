FROM nvidia/cuda:11.8.0-cudnn8-runtime-ubuntu22.04

COPY --from=nvidia/cuda:11.8.0-cudnn8-devel-ubuntu22.04 /usr/local/cuda/bin/ptxas /usr/local/cuda/b# Optimisation APT : On combine et on nettoie les listes dans la même couche

ENV DEBIAN_FRONTEND noninteractive
ENV PYTHONUNBUFFERED "yes"

RUN apt-get update && apt-get install -y --no-install-recommends \
 python3 \
 python3-pip \
 s3cmd \
 && rm -rf /var/lib/apt/lists/*

WORKDIR /app

RUN pip install --no-cache-dir --upgrade pip

ADD requirements.txt .
RUN pip install --no-cache-dir -r requirements.txt
ADD ./src ./src