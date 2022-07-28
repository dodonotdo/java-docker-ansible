## java-docker-ansible

I'm going to describe how to build up this statck end end flow in this example. Here, I've chosen **Ubuntu** as the operating system.

Requirements

|SERVER| IP ADDRES|
|---|---|
| ubuntu | 192.168.0.10 |

_dependencies_

all the appliction are should running as a container. so you need to install the docker daemon and docker-compose  binary in your local machine. If your not installed in your execution machine please installit first. please follow below the instaructions.

_docker installation commands_

```bash
echo -e "\e[1;31mdocker installation"
sudo apt-get update
sudo apt install curl git -y
sudo apt-get install ca-certificates curl gnupg lsb-release -y
sudo mkdir -p /etc/apt/keyrings
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg
echo \
    "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.gpg] https://download.docker.com/linux/ubuntu \
$(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list >/dev/null
sudo apt update -y
sudo apt install docker-ce docker-ce-cli containerd.io docker-compose-plugin -y
sudo systemctl start docker
sudo systemctl status docker
```

_docker compose installtion_

```bash
echo -e "\e[1;31mdocker-compose installation"
sudo curl -SL https://github.com/docker/compose/releases/download/v2.7.0/docker-compose-linux-x86_64 -o /usr/local/bin/docker-compose
sudo chmod +x /usr/local/bin/docker-compose
docker-compose  version
```

_note_

Avoid permission issue you can switch the root user.

_copy the source repository to your virtual machine_

```bash
git clone https://github.com/FourTimes/java-docker-ansible.git
cd java-docker-ansible
```
sonar installation

```bash

```
