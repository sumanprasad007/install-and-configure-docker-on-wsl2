# install-&-configure-docker-on-wsl2

![image](https://user-images.githubusercontent.com/55047333/234490990-b29e90bb-4246-4144-b939-2bd92f3dac29.png)

# Insatlling docker on Ubuntu OS:

curl -fsSL https://get.docker.com -o get-docker.sh
sudo sh get-docker.sh

## Starting the docker engine 

sudo service docker start

## Adding the docker to the group
sudo groupadd docker

## Adding our user to the docker group
sudo usermod -aG docker $USER
newgrp docker

## Updating the system 
sudo apt-get update 

# Install Docker compose
sudo apt-get install docker-compose-plugin

docker compose version


# Resource to follow along:

1. https://docs.docker.com/engine/install/ubuntu/
2. https://docs.docker.com/engine/install/linux-postinstall/#manage-docker-as-a-non-root-user
3. https://docs.docker.com/compose/install/linux/
4. https://github.com/nickjj/dotfiles/commit/badd3265e5c8f6eca90d3b57df29292545332500
