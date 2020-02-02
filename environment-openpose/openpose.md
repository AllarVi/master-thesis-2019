# OpenPose

## Ubuntu start development with Python

1. Log in to EC2 instance

:/usr/local/python/openpose$ sudo ln -s pyopenpose.cpython-36m-x86_64-linux-gnu.so pyopenpose.so

import sys
sys.path.append('/usr/local/python/openpose')
import pyopenpose as op

wget --no-check-certificate 'https://docs.google.com/uc?export=download&id=1t3YaMyz-wId9Knkz2BaOb1bSRS-TjYR_' -O sam-mikulak-tumbling.mp4

## [Installation on Mac](https://github.com/CMU-Perceptual-Computing-Lab/openpose/blob/master/doc/installation.md#installation)

make -j`sysctl -n hw.logicalcpu`

## Reinstallation on Mac

### [Update project and remove old installation](https://github.com/CMU-Perceptual-Computing-Lab/openpose/blob/master/doc/installation.md#reinstallation)

1) git pull origin master
2) cd build/
3) make uninstall
4) rm -r build/
5) In CMake GUI, click on File -> Delete Cache

## Installing Python version

cd build/python
sudo make install

vim ~/.zshrc
export PYTHONPATH=/path/to/openpose/build/python
