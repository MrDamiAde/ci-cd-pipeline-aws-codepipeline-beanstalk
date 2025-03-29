# CI/CD Pipeline Deployment with AWS Elastic Beanstalk

## Overview

In this project, I set up a CI/CD pipeline for a Node.js application using AWS services like Elastic Beanstalk, CodePipeline, and CodeBuild. The goal was to simulate the automation of deploying new versions of an application from a GitHub repository to Elastic Beanstalk with zero downtime.

## What I Did

### 1. **Set Up Elastic Beanstalk Application**
1. I started by creating a Node.js web server environment on Beanstalk
.![Screenshot 2025-03-29 060949](https://github.com/user-attachments/assets/1dfba21e-ba3d-4dc1-95d3-6ca9adbc133b)
2. I then configured service access to Elastic Beanstalk
![Screenshot 2025-03-29 061215](https://github.com/user-attachments/assets/333064ee-daec-4e38-94b7-60c5fd2e3b4b)
3. I selected the default VPC and checked the required regions
![Screenshot 2025-03-29 061316](https://github.com/user-attachments/assets/0f2e1600-9bf1-439d-9a26-805bfd36979f)
4. And then selected basic monitoring 
![Screenshot 2025-03-29 061450](https://github.com/user-attachments/assets/1c29c76b-0d6e-4472-af02-ca85c550f336)

My environment is now created and ready for use.

### 2. **Created a GitHub Repository**
1. Next, I created a GitHub repository ```devops-lab``` which will be where the source code will be hosted.

### 3. **Set Up CodePipeline**
1.I created a pipeline using AWS CodePipeline, which automatically deploys changes to the Elastic Beanstalk application. This pipeline was connected to the GitHub repository and triggered whenever a new commit was pushed.

### 4. **Configured CodeBuild**
To build and test the app, I used AWS CodeBuild. I set up a buildspec.yml file in the root of the project, which defines the build commands and test processes. This ensures that the code is correctly packaged and ready to be deployed to Elastic Beanstalk.

### 5. **Set Up the IAM Role**
I also created an IAM role with the necessary permissions for Elastic Beanstalk, CodePipeline, and CodeBuild. This role needed the ability to interact with AWS services and deploy the application automatically.

### 6. **Configured Elastic Beanstalk to Use the Latest Version**
Each time a new commit was pushed to GitHub, the CI/CD pipeline would automatically create a new version of the app and deploy it to Elastic Beanstalk. I set up the pipeline to ensure that the latest version is always deployed, keeping the app up-to-date.

### 7. **Tested the Entire Pipeline**
Finally, I pushed changes to the GitHub repository, triggering the pipeline to ensure everything was automated properly. From the commit to the final deployment, I ensured that each step worked as expected.

## Project Completed 🎉

- I now have a fully automated CI/CD pipeline that deploys the app from GitHub to Elastic Beanstalk.
- With AWS CodePipeline and CodeBuild, I can push changes to GitHub and have them automatically deployed to my app without manual intervention.
- This setup is scalable, and I can easily integrate future updates or add new features to the pipeline.

