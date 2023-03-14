[![CircleCI](https://dl.circleci.com/status-badge/img/gh/Manuel1407/Operationalizing-Microservices-Using-Docker-and-Kubernetes/tree/Main.svg?style=svg)](https://dl.circleci.com/status-badge/redirect/gh/Manuel1407/Operationalizing-Microservices-Using-Docker-and-Kubernetes/tree/Main)


# Operationalized-Machine-Learning-Microservice-API
## Project Overview

In this project, you will apply the skills you have acquired in this course to operationalize a Machine Learning Microservice API. 

You are given a pre-trained, `sklearn` model that has been trained to predict housing prices in Boston according to several features, such as average rooms in a home and data about highway access, teacher-to-pupil ratios, and so on. You can read more about the data, which was initially taken from Kaggle, on [the data source site](https://www.kaggle.com/c/boston-housing). This project tests your ability to operationalize a Python flask app—in a provided file, `app.py`—that serves out predictions (inference) about housing prices through API calls. This project could be extended to any pre-trained machine learning model, such as those for image recognition and data labeling.


## Setup the Environment

* Create a virtualenv with Python 3.7 and activate it. Refer to this link for help on specifying the Python version in the virtualenv. 
```bash
python3 -m pip install --user virtualenv
# You should have Python 3.7 available in your host. 
# Check the Python path using `which python3`
# Use a command similar to this one:
python3 -m virtualenv --python=<path-to-Python3.7> .devops
source .devops/bin/activate
```

The project contains a make file file `Makefile` which helps to install dependencies and test the project.
* Run `make install` to install the necessary dependencies

* Run `make test` to run tests

* Run `make lint` to lint application and docker file

### Running applicaiton

### 1. Standalone: 
 `python app.py`


### 2. Run in Docker: 
- Install docker by downloading and installing here [here](https://www.docker.com/)
- create a docker hub [here](https://hub.docker.com/)
- login in to docker hub using `docker login`
- run `./run_docker.sh` to create an image (you can replace the docker hub id `ngaie` to yours)
- push your image to docker hub by running the command `./upload_docker.sh`
- application will start following the execution of this script on port 8000.
- run ./make_prediction.sh to get result of prediction


### 3. Run in Kubernetes:
- start docker desktop
- Setup and Configure Kubernetes locally
    * install kubectl from [here](https://kubernetes.io/docs/tasks/tools/install-kubectl-linux/)
    * install minikube from [here](https://minikube.sigs.k8s.io/docs/start/)
- start minikube with `minikube start`    
- run `./run_kubernetes.sh` 
- run `./make_predictions.sh` on another terminal window

### Kubernetes Steps

* Setup and Configure Kubernetes locally
* Create Flask app in Container
* Run via kubectl


### Help
dos2unix run_docker.sh