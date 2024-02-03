# Project-2 Deployment of Super Mario on Kubernetes using Terraform

# Completion steps →

Step 1 → Login and basics setup

Step 2 → Setup Docker ,Terraform ,aws cli , and Kubectl

Step 3 → IAM Role for EC2

Step 4 →Attach IAM role with your EC2

Step 5 → Building Infrastructure Using terraform

Step 6 → Creation of deployment and service for EKS

Step 7 → Destroy all the Insrastructure

## Step 1 → Login and basics setup
1. Lauch an ec2 instance with ubuntu machine and t2.micro instance type

## Step 2 → Setup Docker ,Terraform ,aws cli , and Kubectl

# Switch to root user →
sudo su 
apt update

# Setup Docker →
apt install docker.io -y
usermod -aG docker $USER # Replace with your username e.g ‘ubuntu’
newgrp docker

# Setup Terraform → 
Check for offical page for installation

# Setup AWS cli → 
curl "https://awscli.amazonaws.com/awscli-exe-linux-x86_64.zip" -o "awscliv2.zip"
unzip awscliv2.zip
sudo ./aws/install
      or
sudo apt install awscli -y

# Setup kubectl → 
curl -o kubectl https://amazon-eks.s3.us-west-2.amazonaws.com/1.19.6/2021-01-05/bin/linux/amd64/kubectl
chmod +x ./kubectl
sudo mv ./kubectl /usr/local/bin 
kubectl version --short --client
         or
sudo apt install curl -y
curl -LO https://dl.k8s.io/release/$(curl -L -s https://dl.k8s.io/release/stable.txt)/bin/linux/amd64/kubectl
sudo install -o root -g root -m 0755 kubectl /usr/local/bin/kubectl

## Step 3 → IAM Role for EC2
Give Admin Access to the role 

## Step 4 →Attach IAM role with your EC2
1. go to EC2 section
2. click on actions → security → modify IAM role option
3. choose the role from dropdown and click on update IAM role

## Step 5 → Building Infrastructure Using terraform
mkdir super_mario
cd super_mario

# Git clone - [Github Project link](https://github.com/shreegs123/Project-2.git)
cd Deployment-of-super-Mario-on-Kubernetes-using-terraform/
cd EKS-TF
edit the backend.tf file by → vim backend.tf
# Note →make sure to provide your bucket and region name in this file otherwise it doesn’t work and IAM role is also associated with your ec2 which helps ec2 to use other services such S3 bucket

NOW RUN →

1.terraform init
2.terraform validate
3.terraform plan
4. terraform apply

![App Screenshot](https://github.com/shreegs123/Project-1/blob/main/output.png?raw=true)




