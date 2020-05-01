# Ubuntu Jupyter Notebook setup

https://medium.com/coinmonks/a-step-by-step-guide-to-set-up-an-aws-ec2-for-deep-learning-8f1b96bf7984

## Take Jupyter Notebook configurations and password generation from here

https://chrisalbon.com/aws/basics/run_project_jupyter_on_amazon_ec2/

* Key pair name: master-thesis-2019

## SSH

chmod 600 master-thesis-2019.pem

ssh -i ~/EduWorkspace/master-thesis-2019/environment/master-thesis-2019.pem ubuntu@ec2-13-48-126-113.eu-north-1.compute.amazonaws.com

## Install pyenv on Ubuntu

Instructions: https://github.com/pyenv/pyenv

git clone https://github.com/pyenv/pyenv.git ~/.pyenv

echo 'export PYENV_ROOT="$HOME/.pyenv"' >> ~/.bashrc
echo 'export PATH="$PYENV_ROOT/bin:$PATH"' >> ~/.bashrc

echo -e 'if command -v pyenv 1>/dev/null 2>&1; then\n  eval "$(pyenv init -)"\nfi' >> ~/.bashrc

source ~/.bashrc

sudo apt-get update; sudo apt-get install --no-install-recommends make build-essential libssl-dev zlib1g-dev libbz2-dev libreadline-dev libsqlite3-dev wget curl llvm libncurses5-dev xz-utils tk-dev libxml2-dev libxmlsec1-dev libffi-dev liblzma-dev

pyenv install --list

pyenv install 3.7.2

git clone https://github.com/pyenv/pyenv-virtualenv.git ~/.pyenv/plugins/pyenv-virtualenv

echo 'eval "$(pyenv virtualenv-init -)"' >> ~/.bashrc

source ~/.bashrc

pyenv virtualenv -p python3.7 3.7.2 openpose-extract

https://13.48.126.113:8888/

## Get SSL certificate of a service

openssl s_client -connect {HOSTNAME}:{PORT} -showcerts
