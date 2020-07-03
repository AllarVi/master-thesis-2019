# Amazon Instance Setup

http://aws.amazon.com

## Instance settings

* Choose AMI -> Ubuntu Server 18.04 LTS (HVM), SSD Volume Type
* GPU instances -> g4dn.xlarge
* Storage -> 16GB
* two "Custom TCP Rules" with port ranges (set source to "Anywhere")
    - 20-21
    - 1024-1048

## SSH into instance

```
chmod 600 master-thesis-environment.pem

ssh -i master-thesis-environment.pem ubuntu@13.48.203.146
```

## Install CUDA

```
sudo apt-get update
sudo apt-get install dkms

cd /home/ubuntu

wget http://developer.download.nvidia.com/compute/cuda/10.2/Prod/local_installers/cuda_10.2.89_440.33.01_linux.run

sudo sh cuda_10.2.89_440.33.01_linux.run

# install everything except samples

touch ~/.bash_profile

nano ~/.bash_profile

export PATH="/usr/local/cuda-10.2/bin:$PATH"
export LD_LIBRARY_PATH="/usr/local/cuda-10.2/lib64:$LD_LIBRARY_PATH"

source ~/.bash_profile
```

## FTP 

https://medium.com/tensult/configure-ftp-on-aws-ec2-85b5b56b9c94

```
sudo apt install vsftpd

sudo vim /etc/vsftpd.conf

# Add to end:
pasv_enable=YES
pasv_min_port=1024
pasv_max_port=1048

# Public IP of your instance
pasv_address=13.48.203.146

sudo systemctl restart vsftpd

sudo adduser awsftpuser

```














