ARG CUDA_VER=12.1.0
ARG UBUNTU_VER=22.04
# base, runtime, devel
ARG IMAGE_TYPE=base

# Use an official nvidia/cuda runtime as a parent image
FROM nvidia/cuda:${CUDA_VER}-${IMAGE_TYPE}-ubuntu${UBUNTU_VER}


RUN apt update && \
    apt install -y python3 python3-pip git

COPY requirements.txt /tmp

RUN pip3 install -r /tmp/requirements.txt && \
    pip3 cache purge && \
    rm -rf /tmp/requirements.txt