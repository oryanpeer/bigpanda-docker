# Deploy Bigpanda containerized application,node application, only if healthcheck success
Deploy docker container with python3.4 only if the application pass healthcheck, additional file to https://github.com/bigpandaio/ops-exercise .
## Description
This project is using Docker and Docker compose, download and extract tar.gz archive, link node application to MongoDB using docker compose.

Explanation of each tool can be found on the links below:
* Docker (https://docs.docker.com/)
* Docker-Compose (https://docs.docker.com/compose/)
* Node in Docker (https://nodejs.org/en/docs/guides/nodejs-docker-webapp/)

## Requirements
* [Git](http://git-scm.com)
* [Docker](https://docs.docker.com/install/)
* [Docker-Compose](http://www.vagrantup.com) - The binary file needs to be locates at /usr/local/bin/docker-compose
* [python3.4](https://www.python.org/downloads/)
* [pip](https://pip.pypa.io/en/stable/installing/)

## Optional Requirements
* [virtualenv](https://docs.python-guide.org/dev/virtualenvs/) - After installing venv, you can create environment using, virtualenv -p /usr/bin/python3 docker

## Install clone the repository and install pip packages

```
git clone https://github.com/oryanfarjon/bigpanda-docker.git
pip install -r bigpanda-docker/requirements.txt
```
## Clone BigPanda repo and copy files between repos
```
git clone https://github.com/bigpandaio/ops-exercise.git
cp bigpanda-docker/deployment.py ops-exercise/.
cp bigpanda-docker/docker-compose.yml ops-exercise/.
cd ops-exercise
```
After installing pip requirements and copied the files above to your project root directory, Deploy the application using the command below:
```
python deployment.py
```
You can follow the script output to follow the deployment proccess

After successful deployment, the node app will be available on port 3000 on the server.
* nodeapp: http://localhost:3000
* healthcheck: http://localhost:3000/health

If everything is working properly you will be able to browse the node application URL and see Panda's images.

## Stop containers
To stop the containers and remove the application use the following commands(in your root directory where the docker-compose.yml located):
```
docker-compose stop
docker-compose rm
```
