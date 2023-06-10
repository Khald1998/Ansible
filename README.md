# Automated Nginx Deployment on AWS using Terraform and Ansible

## Background
This project deploys Nginx, an open-source software for web serving, reverse proxying, caching, load balancing, media streaming, and more, on an AWS EC2 instance. It uses Terraform, a popular Infrastructure as Code (IaC) tool, to create and manage AWS resources. It also uses Ansible, a powerful automation tool for configuration management and application deployment, to install and start the Nginx service on the newly created EC2 instance.

## Prerequisites
Before you can run the scripts, you'll need:

1. An AWS account and your AWS credentials configured locally. You can set them up using the AWS CLI with the aws configure command. You will need to input your AWS Access Key ID, AWS Secret Access Key, Default region name, and Default output format.

2. Terraform installed on your machine. You can follow the installation guide on the official Terraform website.

3. Ansible installed on your machine. Installation guide can be found on the official Ansible website.

4. SSH key pair to access the EC2 instance. You should have the private key (.pem file) available on your local machine.

5. An available VPC and Subnet on AWS to host the EC2 instance.

## Steps to Run

1. Clone this repository to your local machine.

2. Update the Terraform variables in main.tf as per your setup:
   - vpc_id and subnet_id for the EC2 instance.
   - ssh_user usually "ubuntu" or "ec2-user" depending on the AMI.
   - key_name name of the key pair in AWS.
   - private_key_path the path of your private key (.pem file).

3. Initialize Terraform using the following command in the terminal:
```
terraform init
```

4. Run the following command to check the changes that will be done by Terraform:
```
terraform plan
```

5. Apply the changes:
```
terraform apply
```

When prompted, type yes and hit enter to proceed with the creation of the resources.

6. The script should end with the public IP address of the newly created EC2 instance where Nginx is installed and running. You can access it in your web browser using the http protocol (for example, http://[ec2-instance-ip]).

Please note that the security settings as per this configuration allow all inbound connections over SSH (port 22) and HTTP (port 80). Ensure to adjust these settings as per your requirement.


# Terraform Ansible Integration | Terraform Ansible AWS Example?

[Step by Step Tutorial](https://youtu.be/QxgJlJgGA0E)
