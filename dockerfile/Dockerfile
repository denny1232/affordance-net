FROM nvidia/cuda:10.0-cudnn7-devel-ubuntu16.04

ENV ADMIN_USER="denny"
ARG DEBIAN_FRONTEND=noninteractive

RUN apt-get update && apt-get install -y --no-install-recommends \
        build-essential \
        cmake \
        git \
        wget \
        unzip \
        python2.7 python-pip \
        libatlas-base-dev \
        cuda-cublas-dev-10-0 \
        libboost-all-dev \
        libgflags-dev \
        libgoogle-glog-dev \
        libhdf5-serial-dev \
        libleveldb-dev \
        liblmdb-dev \
        libopencv-dev \
        libprotobuf-dev \
        libsnappy-dev \
        libhdf5-dev \
        libopencv-dev \
        protobuf-compiler \
        python-dev \
        python-numpy \
        python-setuptools \
        python-scipy && \
    rm -rf /var/lib/apt/lists/*

ENV CPATH="/usr/include/hdf5/serial/"

RUN cd && git clone https://github.com/denny1232/affordance-net.git && \
    cd affordance-net/caffe-affordance-net && \
    cp Makefile.config.example Makefile.config && \
    make -j8 && make pycaffe
    


ENV AffordanceNet_ROOT="/root/affordance-net"

# make cython
RUN cd $Affordance_ROOT/lib && \
    pip install --upgrade pip && \
    pip install cython \
                scikit-image \
                protobuf \
                easydict \
                opencv-python && \
    make 


ENV PYTHONPATH="$AffordanceNet_ROOT/caffe-affordance-net/python:$PYTHONPATH"

RUN cd $AffordanceNet_ROOT
