# install-&-configure-docker-on-wsl2

![image](https://user-images.githubusercontent.com/55047333/234491283-42b051e1-a497-4a09-9651-9f85705015f2.png)

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

# Added the below code to run docker in daemon mode as WSL2 doesn't support daemon by default

### cd /home/user_name 
### ls -al 
### vi .profile

if grep -q "microsoft" /proc/version > /dev/null 2>&1; then

    if service docker status 2>&1 | grep -q "is not running"; then
    
        wsl.exe --distribution "${WSL_DISTRO_NAME}" --user root \
        
            --exec /usr/sbin/service docker start > /dev/null 2>&1
            
    fi
    
fi

## esc then :wq to save and exit 

# 📢 You have successfully, Install and Configure Docker on your WSL2

# Resource to follow along:

1. https://docs.docker.com/engine/install/ubuntu/
2. https://docs.docker.com/engine/install/linux-postinstall/#manage-docker-as-a-non-root-user
3. https://docs.docker.com/compose/install/linux/
4. https://github.com/nickjj/dotfiles/commit/badd3265e5c8f6eca90d3b57df29292545332500
