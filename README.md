
### STEPS TO PERFORM THE PROJECT


### 1  clone the Repository

### 2  conda create -n medicalbot python=3.10 -y

### 3 conda activate medicalbot

### 4 pip install -r requirements.txt


### for deployment on AWS here are following steps:

```
1)Login to AWS CONSOLE.
2)create IAM user for deployment

#with specific accesss
1. EC2 access: it is virtual machine
2. ECR: Elastic container registery to save your docker image in AWS

#Description: About the deployment

1.Build docker image of the source code
2.push your docker image to ECR
3.Launch your EC2
4.Pull your image from ECR to EC2
5.Launch your docker image in EC2

#Policy:

1.AmazonEC2ContainerRegistryFullAccess
2.AmazonEC2FullAccess

Create ECR repo to store/save docker image
-Save the URI: 266735820309.dkr.ecr.ap-south-1.amazonaws.com/medicalchatbot

### 4.Create EC2 machine (ubuntu)

5. Open EC2 and install docker in EC2 machine:

sudo apt-get update -y

sudo apt-get upgrade

#required

curl -fsSL https://get.docker.com -o get-docker.sh

sudo sh get-docker.sh

sudo usermod -aG docker ubuntu

newgrp docker

#6.Configure EC2 as self-hosted runner:

setting>actions>runner>new self hosted>choose os>then run command one by one

#7. setup github secrets:

-AWS_ACCESS_KEY_ID
-AWS_SECRET_ACCESS_KEY
-AWS_DEFAULT_REGION
-ECR_REPO
-PINECONE_API_KEY
-OPENAI_API_KEY


```