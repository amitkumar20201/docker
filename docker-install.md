
https://github.com/academiaonline/dca

***INSTALL DOCKER***
https://docs.docker.com/

follow article as per OS
* Get the name of OS 
cat /etc/os-release

Remove previous version of docker.
sudo apt-get remove docker docker-engine docker.io containerd runc

Run docker as root without sudo
https://docs.docker.com/engine/install/linux-postinstall/

***END***

**Install Commands**

sudo apt-get remove docker docker-engine docker.io containerd runc
sudo apt-get update
sudo apt-get install \
    apt-transport-https \
    ca-certificates \
    curl \
    gnupg \
    lsb-release

curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg

echo \
  "deb [arch=amd64 signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/ubuntu \
  $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null

sudo apt-get update
sudo apt-get install docker-ce docker-ce-cli containerd.io

sudo groupadd docker
sudo usermod -aG docker $USER
newgrp docker 

docker run hello-world

**Enable the docker and vaildate**

systemctl is-enabled docker
sudo systemctl enable docker
systemctl status docker
sudo systemctl start docker

**Play with Docker**

Docker Lab (Free) - https://labs.play-with-docker.com/
Kubernetes (Free) - https://learn.openshift.com/playgrounds/


