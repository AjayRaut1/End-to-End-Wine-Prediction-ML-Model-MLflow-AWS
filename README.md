# End-to-End-Wine-Prediction-ML-Model-MLflow-AWS
This repo contains End to End AWD hosted full functional Wine Prediction Machine Learning model with high accuracy

## Workflows 

0. First do Research in research/01_data_ingestion.ipynb file.
1. Update config.yaml
2. Update schema.yaml 
3. Update params.yaml
4. Update the entity -> config_entity.py file
5. Update the configuration manager in src config -> configuration.py (mlProject/Config Folder)
6. Update the components -> data_ingestion.py (mlProject/components Folder)
7. Update the pipeline -> stage_01_data_ingestion.py (mlProject/pipeline)
8. Update the main.py 
9. Update the app.py



# How to run?
### STEPS:

Clone the repository

```bash
https://github.com/AjayRaut1/End-to-End-Wine-Prediction-ML-Model-MLflow-AWS/
```
### STEP 01- Create a conda environment after opening the repository

```bash
conda create -n mlproj python=3.8 -y
```

```bash
conda activate mlproj
```


### STEP 02- install the requirements
```bash
pip install -r requirements.txt
```


```bash
# Finally run the following command
python app.py
```

Now,
```bash
open up you local host and port : 
http://127.0.0.1:8080
```



## MLflow

[Documentation](https://mlflow.org/docs/latest/index.html)


##### cmd
- mlflow ui

### Dagshub
Connect your Repo with [Dagshub](https://dagshub.com/)

Ignore below details that u will get from dagshub :
(This details will be required for executing the below bash commands) 

MLFLOW_TRACKING_URI=https://dagshub.com/coderajayraut/End-to-End-Wine-Prediction-ML-Model-MLflow-AWS.mlflow \
MLFLOW_TRACKING_USERNAME=coderajayraut \
MLFLOW_TRACKING_PASSWORD=88050e0c2c067ebbe5d0589f98ea1f9723dd9c44 \
python script.py

Run this to export as env variables into Bash:

```bash

export MLFLOW_TRACKING_URI=https://dagshub.com/coderajayraut/End-to-End-Wine-Prediction-ML-Model-MLflow-AWS.mlflow

export MLFLOW_TRACKING_USERNAME=coderajayraut

export MLFLOW_TRACKING_PASSWORD=88050e0c2c067ebbe5d0589f98ea1f9723dd9c44

```



# AWS-CICD-Deployment-with-Github-Actions

## 1. Login to AWS console.

## 2. Create IAM user for deployment

	#with specific access

	1. EC2 access : It is virtual machine

	2. ECR: Elastic Container registry to save your docker image in aws


	#Description: About the deployment

	1. Build docker image of the source code

	2. Push your docker image to ECR

	3. Launch Your EC2 

	4. Pull Your image from ECR in EC2

	5. Lauch your docker image in EC2

	#Policy:

	1. AmazonEC2ContainerRegistryFullAccess

	2. AmazonEC2FullAccess

	
## 3. Create ECR repo to store/save docker image
    - Save the URI: 041830038805.dkr.ecr.ap-south-1.amazonaws.com/mlproj-wine-prediction

	
## 4. Create EC2 machine (Ubuntu) 

## 5. Open EC2 and Install docker in EC2 Machine:
	
	
	#optional

	sudo apt-get update -y

	sudo apt-get upgrade
	
	#required

	curl -fsSL https://get.docker.com -o get-docker.sh

	sudo sh get-docker.sh

	sudo usermod -aG docker ubuntu

	newgrp docker

	docker --version (to verify docker installation)
	
# 6. Configure EC2 as self-hosted runner:
    setting>actions>runner>new self hosted runner> choose os> then run command one by one


# 7. Setup github secrets:

    AWS_ACCESS_KEY_ID = (Downloaded mlproj-user-access-keys csv file) 

    AWS_SECRET_ACCESS_KEY = (Downloaded mlproj-user-access-keys csv file)

    AWS_REGION = ap-south-1 (I am using Mumbai server)

    AWS_ECR_LOGIN_URI = 041830038805.dkr.ecr.ap-south-1.amazonaws.com (Use your's from step 3)

    ECR_REPOSITORY_NAME = mlproj-wine-prediction (refer step 3)




## About MLflow 
MLflow

 - Its Production Grade
 - Trace all of your expriements
 - Logging & tagging your model


