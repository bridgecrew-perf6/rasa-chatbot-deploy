# Rasa 3.0 Deployment
Deploying Rasa Bot over Google Cloud Platform using Docker.

## Prerequisites:
- Docker
- Docker Compose


## Instructions:

### For deploying locally:

- clone this repository
- run the below command within the project directory:
>  docker-compose up --build

- Check whether the services are up and running using below command:
> docker ps -a

- test out the bot in the browser
> http://localhost



### For deploying over GCP Compute Engine:
- Create the VM instance of Ubuntu over Compute Engine
- once the instance is created login to the VM using SSH
- Run the below commands and clone our Docker app:

 - > sudo apt-get update
 
#### Install Docker

- > curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add 
- > sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable"
- > sudo apt-get update
- >  apt-cache policy docker-ce
- > sudo apt-get install -y docker-ce
- > sudo systemctl status docker
     
#### Install [Docker-Compose](https://docs.docker.com/compose/install/)

- >  sudo curl -L "https://github.com/docker/compose/releases/download/1.29.2/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose

- > sudo chmod +x /usr/local/bin/docker-compose
- > docker-compose --version

#### Clone the Docker App

- > git clone git@github.com:shankar-bavan/rasa-chatbot-deploy.git
- > cd rasa-chatbot

#### Build the Docker app and run the services:

- > sudo docker-compose up -d --build

- Check whether the services are up and running using below command:
- > docker ps -a

- Once you see all the services up and running, open the ip address of the machine in the browser and test the bot


