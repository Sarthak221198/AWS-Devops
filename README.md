# AWS DevOps Project: CI/CD with CodeBuild, CodeDeploy, and CodePipeline

# 📌 Project Overview

This project demonstrates a fully automated CI/CD pipeline using AWS DevOps services, including:

- AWS CodeBuild → Builds the application
- AWS CodeDeploy → Deploys the application to EC2 or other environments
- AWS CodePipeline → Automates the workflow from source to deployment

🎯 Project Workflow

# Build Phase (AWS CodeBuild)

- The application source code is retrieved.
- CodeBuild runs unit tests and creates an artifact.
- The built package is stored in an S3 bucket.

# Code build settings

![Screenshot](images/images1.PNG)

- Since code commit is no longer available for storing repos in AWS we will be integrating github with AWS

![Screenshot](images/images2.PNG)



![Screenshot](images/images3.PNG)

- Build spec.yml file builds the project and installs the required dependency's.

![Screenshot](images/images4.PNG)

- Storing the build artifact in a S3 bucket, which can be helpfull in versioning of the code.

![Screenshot](images/images5.PNG)

- Service role in AWS CodeDeploy is an IAM role that grants AWS CodeDeploy the necessary permissions to perform deployment operations on behalf of the user. The role allows CodeDeploy to interact with AWS resources like EC2 instances, Auto Scaling groups, Lambda functions, and ECS services.

![Screenshot](images/images6.PNG)

![Screenshot](images/images7.PNG)

- After running the build and on its completion we can see the code being stored as a zip file in S3 bucket.

![Screenshot](images/images8.PNG)

![Screenshot](images/images9.PNG)


# Deployment Phase (AWS CodeDeploy)

- CodeDeploy fetches the artifact from S3.
- Deploys the application to EC2 instances, ECS, or Lambda.
- Uses deployment strategies like Blue-Green or Rolling Updates.

# Code Deploy settings

- creation of applications, deployment groups and deployments

![Screenshot](images/images10.PNG)

![Screenshot](images/images11.PNG)

![Screenshot](images/images12.PNG)

- Need to create an Ubuntu 22.04 LTS version EC2 instance with code deploy agent installed

![Screenshot](images/images13.PNG)

![Screenshot](images/images14.PNG)

- Deployment creation

![Screenshot](images/images15.PNG)

![Screenshot](images/images16.PNG)

- Deployment completion and application hosted on the public IP of the EC2 instance.

![Screenshot](images/images17.PNG)

- HTML website hosted on the EC2 instances

![Screenshot](images/Capture1.PNG)


# Pipeline Execution (AWS CodePipeline)

- Automates the entire process.
- Ensures seamless deployments.

# Code pipeline settings

![Screenshot](images/images18.PNG)

![Screenshot](images/images19.PNG)

![Screenshot](images/images20.PNG)

![Screenshot](images/images21.PNG)

![Screenshot](images/images22.PNG)

![Screenshot](images/images23.PNG)


# 🛠 Technologies Used
- ✅ AWS Services: CodePipeline, CodeBuild, CodeDeploy, S3, EC2, IAM
- ✅ Version Control: GitHub
- ✅ Build Automation: CodeBuild (buildspec.yml)
- ✅ Deployment Strategy: In Line deployment


