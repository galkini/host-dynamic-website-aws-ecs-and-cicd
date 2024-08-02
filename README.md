![Alt text](/Dynamic_website_on_ECS_CI_CD_implementation.png)

I hosted a a dynamis Website on AWS with docker containers, ECS and ECR for a DevOps project. Have created CICD Pipeline with GitHub Actions to implement workflow from the moment that developer pushes and update to the GitHub repository, till the moment the updated AWS infrastructure, and Web application are up and running.

1.	Have created GitHub repository, with AWS infrastructure terraform files, and .gitignore file adjusted to the CICD workflow process. Cloned and synced with my PC
2.	Updated terraform.tfvars, and backend.tf files, and performed dry run of building and destroying the AWS infrastructure
3.	Created GitHub access token for the repository just created
4.	Created GitHub Repository Secrets to store env variables values that we will use during building the image, and during runtime
5.	Created a GitHub Actions workflow file in project repository
6.	Created a GitHub Actions job to configure AWS credentials
7.	Created a GitHub Actions job to deploy AWS Infrastructure
8.	Created a GitHub Actions job to create an Amazon ECR Repository
9.	Created EC2 instance, installed on it Docker and Git, and created AMI from it. The self-hosted runner that we will use later on, will start from this image
10.	Created a GitHub Actions job to start a self-hosted runner
11.	Created a Dockerfile to build an application image
12.	Created a GitHub Actions job, on a self-hosted runner, to build and push a Docker image to ECR
13.	Created a GitHub Actions job to export env variables to S3 bucket
14.	Created a GitHub Actions job, on a self-hosted runner, to migrate the application database to RDS. Used Flyway engine for migration
15.	Created a GitHub Actions job to stop EC2 instance that served as our self-hosted runner
16.	Created a GitHub Actions job to create new ECS Task definition revision
17.	Created a GitHub Actions job to restart the ECS Fargat service, in order to update the ECS task revision to work with. To the latest ECS task revision
18.	Destroyed everything
