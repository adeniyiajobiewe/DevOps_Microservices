[![CircleCI](https://dl.circleci.com/status-badge/img/gh/adeniyiajobiewe/DevOps_Microservices/tree/main.svg?style=svg)](https://dl.circleci.com/status-badge/redirect/gh/adeniyiajobiewe/DevOps_Microservices/tree/main)

## Project Overview

This project uses a pretrained sklearn model, trained to predict housing prices in Boston, to serve out predictions about house prices through API calls. The overall idea is to operationalize this machine learning microservice API using container technology and Kubernetes for the orchestratrion of containers.
You can read more about the data, which was initially taken from Kaggle, on [the data source site](https://www.kaggle.com/c/boston-housing). 

## Dependencies and Requirements

* Python https://www.python.org/downloads/

* Docker Desktop Install Docker here: https://docs.docker.com/install/ based on your operating system.

* Kubernetes You would need to install any one tool for creating a Kubernetes cluster - KubeOne / Minikube / kubectl on top of Docker Desktop:

* https://kubernetes.io/docs/tasks/tools/install-kubectl/ directly on top of Docker desktop - For Windows/macOS
* https://kubernetes.io/docs/tasks/tools/install-minikube/ - For Linux/macOS
* Hadolint Install hadolint following the instructions, https://github.com/hadolint/hadolint


### Description of files and folders in the repository

* .circleci: Folder containing the config.yml file for running CircleCI builds
* model_data : this folder contains the pretrained sklearn model and housing csv files
* output_txt_files: folder contains sample output logs from running ./run_docker.sh and ./run_kubernetes.sh
* app.py: Python file that contains the flask app
* Dockerfile: File used to build a docker image
* Makefile: Contains instructiond for setting up environments and performing lint tests
* run_docker.sh: Contains bash scripts that uses the YAML Dockerfile to build the docker image
* upload_docker.sh: Bash script to upload the built Docker image to Dockerhub
* run_kubernetes.sh: Bash script to run the application in a Kubernetes cluster
* make_prediction.sh: Bash script with commands to use the pretrained model to make predictions against the Docker container and k8s cluster
* READDME.md: a readme file
You can find a detailed [project rubric, here](https://review.udacity.com/#!/rubrics/2576/view).

**The final implementation of the project will showcase your abilities to operationalize production microservices.**

---

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
* Run `make install` to install the necessary dependencies

### Running `app.py`

1. Standalone:  `python app.py`
2. Run in Docker:  `./run_docker.sh`
3. Run in Kubernetes:  `./run_kubernetes.sh`

### Kubernetes Steps

* Setup and Configure Docker locally
* Setup and Configure Kubernetes locally
* Create Flask app in Container
* Run via kubectl
