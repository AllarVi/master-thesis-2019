# Ubuntu OpenPose Python Setup

## Ubuntu start development with Python

1. Log in to EC2 instance

:/usr/local/python/openpose$ sudo ln -s pyopenpose.cpython-36m-x86_64-linux-gnu.so pyopenpose.so

import sys
sys.path.append('/usr/local/python/openpose')
import pyopenpose as op

wget --no-check-certificate 'https://docs.google.com/uc?export=download&id=1t3YaMyz-wId9Knkz2BaOb1bSRS-TjYR_' -O sam-mikulak-tumbling.mp4
