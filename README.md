![Alt test](Docker.jpg)

---
# Static Web App Deployment on AWS

This repository contains the reference diagram and deployment scripts for hosting a static web application using AWS services, Docker, and GitHub. The architecture leverages Amazon ECS, Amazon ECR, and other AWS components to ensure high availability, scalability, and security.

## Project Overview

The project involves deploying a static web application using the following AWS resources and services:

1. **Virtual Private Cloud (VPC)**: Configured with public and private subnets spanning two availability zones.
2. **Internet Gateway**: Provides connectivity between VPC instances and the internet.
3. **Security Groups**: Implemented as network firewalls to secure resources.
4. **Availability Zones**: Two availability zones used to enhance reliability and fault tolerance.
5. **Public Subnets**: Used for infrastructure components like NAT Gateway and Application Load Balancer.
6. **Docker**: Application containerized with Docker, with images stored in Amazon ECR and Docker Hub.
7. **Amazon ECS**: Deployed the application container using AWS Fargate, with ECS task definitions and services configured.
8. **Application Load Balancer**: Distributes web traffic across an Auto Scaling Group of EC2 instances.
9. **DNS and SSL**: Configured DNS records and requested an SSL certificate using AWS Certificate Manager to secure application communications.

## Architecture Diagram

The reference diagram for the deployment architecture can be found in the repository. It illustrates the setup of the VPC, subnets, security groups, ECS cluster, load balancer, and other components.

## Deployment Instructions

Follow the steps below to deploy the static web app using the provided scripts and configurations:

### 1. Configure VPC

- Create a VPC with public and private subnets across two availability zones.
- Deploy an Internet Gateway for internet access.

### 2. Set Up Security Groups

- Create and configure security groups for network access control.

### 3. Deploy Infrastructure Components

- **Public Subnets**: Deploy NAT Gateway and Application Load Balancer in public subnets.
- **Private Subnets**: Ensure other infrastructure components are deployed in private subnets.

### 4. Dockerize the Application

- Create a `Dockerfile` for the application.
- Build the Docker image and push it to Amazon ECR and Docker Hub.

### 5. Set Up Amazon ECS

- Create an ECS cluster using AWS Fargate.
- Define ECS task definitions and create ECS services to run the application containers.

### 6. Configure Load Balancing

- Set up an Application Load Balancer and target group to distribute traffic to the ECS service.
- Configure an Auto Scaling Group for EC2 instances across multiple availability zones.

### 7. Configure DNS and SSL

- Set up DNS records for your domain.
- Request an SSL certificate using AWS Certificate Manager and secure communications.

## Scripts and Configuration

The repository includes deployment scripts for:

- VPC and networking setup
- Docker image creation and deployment
- ECS cluster and service configuration
- Load balancer setup
- DNS and SSL configuration

## How to Use

1. Clone this repository to your local machine.
2. Follow the AWS documentation to create the required resources (VPC, subnets, Internet Gateway, etc.) as outlined in the architecture overview.
3. Use the provided scripts to set up the WordPress application on EC2 instances within the VPC.
4. Configure the Auto Scaling Group, Load Balancer, and other services as per the architecture.
5. Access the WordPress website through the Load Balancer's DNS name.


## Contributing

Feel free to contribute to this project by submitting issues or pull requests. Your feedback and improvements are welcome!

## License

This project is licensed under the [MIT License](LICENSE).

---

