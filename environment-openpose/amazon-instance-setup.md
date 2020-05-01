# Amazon Instance Setup

## Instance settings

Ubuntu Server 18.04 LTS (HVM), SSD Volume Type

GPU instances g4dn.xlarge

storage 16GB

two Custom TCP Rules with port ranges 20-21 and 1024-1048

## SSH into instance

chmod 600 openpose-extract.pem

ssh -i openpose-extract.pem ubuntu@ec2-13-53-199-232.eu-north-1.compute.amazonaws.com

## Install CUDA

sudo apt-get update
sudo apt-get install dkms

cd home/ubuntu

wget http://developer.download.nvidia.com/compute/cuda/10.2/Prod/local_installers/cuda_10.2.89_440.33.01_linux.run

sudo sh cuda_10.2.89_440.33.01_linux.run

Install everything except samples

Please make sure that
 -   PATH includes /usr/local/cuda-10.2/bin
 -   LD_LIBRARY_PATH includes /usr/local/cuda-10.2/lib64, or, add /usr/local/cuda-10.2/lib64 to /etc/ld.so.conf and run ldconfig as root

export PATH="/usr/local/cuda-10.2/bin:$PATH"
export LD_LIBRARY_PATH="/usr/local/cuda-10.2/lib64:$LD_LIBRARY_PATH"

## FTP 

https://medium.com/tensult/configure-ftp-on-aws-ec2-85b5b56b9c94

sudo apt install vsftpd

sudo vim /etc/vsftpd.conf

Add to end:
pasv_enable=YES
pasv_min_port=1024
pasv_max_port=1048
pasv_address=<Public IP of your instance>

sudo systemctl restart vsftpd

adduser awsftpuser















