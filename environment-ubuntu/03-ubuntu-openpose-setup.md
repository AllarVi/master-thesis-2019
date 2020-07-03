# Install Openpose on Ubuntu

## 1) Get CUDA version

nvcc --version

/usr/local/cuda/bin/nvcc --version

## 2) Install and use Python virtualenv

## 3) Install OpenPose

cd ~/

git clone https://github.com/CMU-Perceptual-Computing-Lab/openpose

wget -c "https://github.com/Kitware/CMake/releases/download/v3.13.4/cmake-3.13.4.tar.gz"
tar xf cmake-3.13.4.tar.gz
cd cmake-3.13.4 && ./configure && make && sudo make install

# Basic

sudo apt-get --assume-yes update
sudo apt-get --assume-yes install build-essential

# OpenCV

sudo apt-get --assume-yes install libopencv-dev

# General dependencies

sudo apt-get --assume-yes install libatlas-base-dev libprotobuf-dev libleveldb-dev libsnappy-dev libhdf5-serial-dev protobuf-compiler

sudo apt-get --assume-yes install --no-install-recommends libboost-all-dev

# Remaining dependencies, 14.04

sudo apt-get --assume-yes install libgflags-dev libgoogle-glog-dev liblmdb-dev

# Python3 libs

sudo apt-get --assume-yes install python3-setuptools python3-dev build-essential
sudo apt-get --assume-yes install python3-pip
sudo -H pip3 install --upgrade numpy protobuf opencv-python

# OpenCL Generic

sudo apt-get --assume-yes install opencl-headers ocl-icd-opencl-dev
sudo apt-get --assume-yes install libviennacl-dev   

# Openpose Models
cd openpose/models && ./getModels.sh

CUDNN_URL="https://developer.nvidia.com/compute/machine-learning/cudnn/secure/7.6.5.32/Production/10.2_20191118/cudnn-10.2-linux-x64-v7.6.5.32.tgz"

CUDNN_URL="http://developer.download.nvidia.com/compute/redist/cudnn/v5.1/cudnn-8.0-linux-x64-v5.1.tgz"

wget -c ${CUDNN_URL}

sudo tar -xzf cudnn-10.2-linux-x64-v7.6.5.32.tgz -C /usr/local

sudo tar -xzf cudnn-8.0-linux-x64-v5.1.tgz -C /usr/local

rm cudnn-10.2-linux-x64-v7.6.5.32.tgz && sudo ldconfig

rm cudnn-8.0-linux-x64-v5.1.tgz && sudo ldconfig

# Build Openpose (in ../openpose/build/)

mkdir build
cd build
 
cmake .. 

vim CMakeCache.txt
turn BUILD_PYTHON to ON

make -j`nproc`

## Install OpenPose Python version

cd build/python
make install

pip install opencv-python-headless

vim ~/.bashrc
export PYTHONPATH=/home/ubuntu/openpose/build/python
source ~/.bashrc

