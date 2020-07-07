# Amazon Instance Setup

http://aws.amazon.com

## Instance settings

* Choose AMI -> Ubuntu Server 18.04 LTS (HVM), SSD Volume Type
* GPU instances -> g4dn.xlarge
* Storage -> 16GB
* two "Custom TCP Rules" with port ranges (set source to "Anywhere")
    - 20-21
    - 1024-1048
    - 8888

### Instance specifications

* Ubuntu Server 18.04 LTS (HVM), SSD Volume Type
* g4dn.xlarge (- ECUs, 4 vCPUs, 2.5 GHz, Intel Xeon P-8259L, 16 GiB memory, EBS only)
* 16GB general purpose SSD
* $0.558 per On Demand Linux g4dn.xlarge Instance Hour

## SSH into instance

```
chmod 600 master-thesis-environment.pem

ssh -i master-thesis-environment.pem ubuntu@13.53.133.217
```

## Install CUDA

```

sudo apt-get update && sudo apt-get -y install dkms

cd  && wget http://developer.download.nvidia.com/compute/cuda/10.2/Prod/local_installers/cuda_10.2.89_440.33.01_linux.run

# install everything except samples
sudo sh cuda_10.2.89_440.33.01_linux.run

touch ~/.bash_profile && \
echo 'export PATH="/usr/local/cuda-10.2/bin:$PATH"' >> ~/.bash_profile && \
echo 'export LD_LIBRARY_PATH="/usr/local/cuda-10.2/lib64:$LD_LIBRARY_PATH"' >> ~/.bash_profile && \
source ~/.bash_profile

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
pasv_address=13.53.133.217
pasv_addr_resolve=YES

sudo systemctl restart vsftpd

sudo service vsftpd status

# use user ubuntu and key with FileZilla default port

```

## Clone notebooks repo

git clone https://github.com/AllarVi/pose-estimation-jupyter.git

## Install Python

git clone https://github.com/pyenv/pyenv.git ~/.pyenv && \
echo 'export PYENV_ROOT="$HOME/.pyenv"' >> ~/.bash_profile && \
echo 'export PATH="$PYENV_ROOT/bin:$PATH"' >> ~/.bash_profile && \
source ~/.bash_profile

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

// password is 'admin'
ipython
from IPython.lib import passwd
passwd()
Enter password: [Create password and press enter] Verify password: [Press enter]
'sha1:d3ba85fb8b4a:1525499c248a0cf8f35053c3e7015e7fa3e0b076'
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
# Change ip

c = get_config()

# Kernel config
c.IPKernelApp.pylab = 'inline'  # if you want plotting support always in your notebook

# Notebook config
c.NotebookApp.certfile = u'/home/ubuntu/certs/mycert.pem' #location of your certificate file
c.NotebookApp.ip = '0.0.0.0'
c.NotebookApp.open_browser = False  #so that the ipython notebook does not opens up a browser by default
c.NotebookApp.password = u'sha1:d3ba85fb8b4a:1525499c248a0cf8f35053c3e7015e7fa3e0b076'  #the encrypted password we generated above
# Set the port to 8888, the port we set up in the AWS EC2 set-up
c.NotebookApp.port = 8888

```

sudo chown $USER:$USER /home/ubuntu/certs/mycert.pem

jupyter notebook

// In Safari
https://13.53.133.217:8888/



