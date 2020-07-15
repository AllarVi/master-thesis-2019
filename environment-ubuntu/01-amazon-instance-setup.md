# Amazon Instance Setup

http://aws.amazon.com

## Instance specifications

* Ubuntu Server 18.04 LTS (HVM), SSD Volume Type
* g4dn.xlarge (- ECUs, 4 vCPUs, 2.5 GHz, Intel Xeon P-8259L, 16 GiB memory, EBS only)
* 64GB general purpose SSD
* $0.558 per On Demand Linux g4dn.xlarge Instance Hour
* "Custom TCP Rules" with port ranges (set source to "Anywhere")
    - 20-21
    - 1024-1048
    - 8888

## SSH into instance

```
chmod 600 master-thesis-environment.pem

# Amazon
ssh -i master-thesis-environment.pem ubuntu@13.48.123.194

# Google Cloud 
ssh -i ~/.ssh/master-thesis-environment ubuntu@34.105.147.25
```

## Install CUDA

```

# https://www.tensorflow.org/install/gpu#linux_setup

sudo apt-get update

# Add NVIDIA package repositories

wget https://developer.download.nvidia.com/compute/cuda/repos/ubuntu1804/x86_64/cuda-repo-ubuntu1804_10.1.243-1_amd64.deb

sudo apt-key adv --fetch-keys https://developer.download.nvidia.com/compute/cuda/repos/ubuntu1804/x86_64/7fa2af80.pub

sudo dpkg -i cuda-repo-ubuntu1804_10.1.243-1_amd64.deb

sudo apt-get update

wget http://developer.download.nvidia.com/compute/machine-learning/repos/ubuntu1804/x86_64/nvidia-machine-learning-repo-ubuntu1804_1.0.0-1_amd64.deb

sudo apt install ./nvidia-machine-learning-repo-ubuntu1804_1.0.0-1_amd64.deb

sudo apt-get update

# Install NVIDIA driver

sudo apt-get install --no-install-recommends nvidia-driver-450

# Reboot. Check that GPUs are visible using the command: nvidia-smi

# Install development and runtime libraries (~4GB)
sudo apt-get install -y --no-install-recommends \
    cuda-10-1 \
    libcudnn7=7.6.4.38-1+cuda10.1  \
    libcudnn7-dev=7.6.4.38-1+cuda10.1

# Install TensorRT. Requires that libcudnn7 is installed above.
sudo apt-get install -y --no-install-recommends libnvinfer6=6.0.1-1+cuda10.1 \
    libnvinfer-dev=6.0.1-1+cuda10.1 \
    libnvinfer-plugin6=6.0.1-1+cuda10.1

touch ~/.profile && \
echo 'export PATH="/usr/local/cuda-10.1/bin:$PATH"' >> ~/.profile && \
echo 'export LD_LIBRARY_PATH="/usr/local/cuda-10.1/lib64:$LD_LIBRARY_PATH"' >> ~/.profile && \
echo 'export LD_LIBRARY_PATH="/usr/local/cuda/extras/CUPTI/lib64:$LD_LIBRARY_PATH"' >> ~/.profile && \
source ~/.profile

```

## FTP 

https://medium.com/tensult/configure-ftp-on-aws-ec2-85b5b56b9c94

```

sudo apt install -y vsftpd

sudo vim /etc/vsftpd.conf

# Add to end:
write_enable=YES
pasv_enable=YES
pasv_min_port=1024
pasv_max_port=1048
port_enable=YES
# Public IP of amazon instance
pasv_address=34.105.147.25
pasv_addr_resolve=YES

sudo systemctl restart vsftpd

sudo service vsftpd status

# use user ubuntu and key with FileZilla default port

```

## Clone notebooks repo

git clone https://github.com/AllarVi/pose-estimation-jupyter.git

## Install Python

git clone https://github.com/pyenv/pyenv.git ~/.pyenv && \
echo 'export PYENV_ROOT="$HOME/.pyenv"' >> ~/.profile && \
echo 'export PATH="$PYENV_ROOT/bin:$PATH"' >> ~/.profile && \
source ~/.profile

sudo apt-get install -y build-essential libssl-dev zlib1g-dev libbz2-dev \
libreadline-dev libsqlite3-dev wget curl llvm libncurses5-dev libncursesw5-dev \
xz-utils tk-dev libffi-dev liblzma-dev python-openssl git

pyenv install 3.7.2

pyenv global 3.7.2

## Graphviz for plots

sudo apt install -y graphviz

## Install Python virtualenv

git clone https://github.com/pyenv/pyenv-virtualenv.git $(pyenv root)/plugins/pyenv-virtualenv

echo 'eval "$(pyenv init -)"' >> ~/.bashrc && \
echo 'eval "$(pyenv virtualenv-init -)"' >> ~/.bashrc && \
source ~/.bashrc

## Create virtualenv

pyenv virtualenv -p python3.7 3.7.2 master-thesis-environment
pyenv activate master-thesis-environment

pip install jupyter ipython

ipython kernel install --user --name=master-thesis-environment

cd ~/pose-estimation-jupyter

pip install -r requirements.txt

pip install tensorflow-gpu

// password is 'admin'
ipython
from IPython.lib import passwd
passwd()
Enter password: [Create password and press enter] Verify password: [Press enter]
'sha1:dc542de4fb23:8e8785edb5e8fec931e6b81e872d8dcc0b8acf85'
exit

jupyter notebook --generate-config

mkdir certs && \
cd certs && \
openssl req -x509 -nodes -days 365 -newkey rsa:1024 -keyout mycert.pem -out mycert.pem

cd ~/.jupyter/

vi jupyter_notebook_config.py

```
# Insert at the beginning of document 
# Change password

c = get_config()

# Kernel config
c.IPKernelApp.pylab = 'inline'  # if you want plotting support always in your notebook

# Notebook config
c.NotebookApp.certfile = u'/home/ubuntu/certs/mycert.pem' #location of your certificate file
c.NotebookApp.ip = '0.0.0.0'
c.NotebookApp.open_browser = False  #so that the ipython notebook does not opens up a browser by default
c.NotebookApp.password = u'sha1:dc542de4fb23:8e8785edb5e8fec931e6b81e872d8dcc0b8acf85'  #the encrypted password we generated above
# Set the port to 8888, the port we set up in the AWS EC2 set-up
c.NotebookApp.port = 8888

```

sudo chown $USER:$USER /home/ubuntu/certs/mycert.pem

jupyter notebook

// In Safari
https://34.105.147.25:8888/


```

import tensorflow as tf

tf.config.list_physical_devices('GPU')

```













