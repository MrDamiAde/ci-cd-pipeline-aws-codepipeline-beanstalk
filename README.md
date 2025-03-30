# CI/CD Pipeline Deployment with AWS Elastic Beanstalk

## Overview

In this project, I set up a CI/CD pipeline for a Node.js application using AWS services like Elastic Beanstalk, CodePipeline, and CodeBuild. The goal was to simulate the automation of deploying new versions of an application from a GitHub repository to Elastic Beanstalk with zero downtime.

## What I Did

### 1. **Set Up Elastic Beanstalk Application**
1. I started by creating a Node.js web server environment on Beanstalk
.![Screenshot 2025-03-29 060949](https://github.com/user-attachments/assets/1dfba21e-ba3d-4dc1-95d3-6ca9adbc133b)
2. I then configured service access to Elastic Beanstalk
![Screenshot 2025-03-29 061215](https://github.com/user-attachments/assets/333064ee-daec-4e38-94b7-60c5fd2e3b4b)
3. I selected the default VPC and selected two subnets
![Screenshot 2025-03-29 061316](https://github.com/user-attachments/assets/0f2e1600-9bf1-439d-9a26-805bfd36979f)


4. After a few minutes, my environment is live with a default screen:

![Screenshot 2025-03-29 061951](https://github.com/user-attachments/assets/5f21b643-0711-4e9e-9c00-6a68e8ec6f8f)

### 2. **Created a GitHub Repository**
1. Next, I created a GitHub repository ```devops-lab``` where the source code will be hosted
   ![Screenshot 2025-03-29 062258](https://github.com/user-attachments/assets/dd40b3dd-a897-440c-90d3-aa6cd0ea1f6a)

2. I also created a connection to that repository under Developer Tools called ```my-connection```
   ![Screenshot 2025-03-29 061846](https://github.com/user-attachments/assets/18273d82-1899-49ba-b76c-5fc77668a5c8)

### 3. **Set Up CodePipeline**
1. I created a pipeline using AWS CodePipeline, which automatically deploys changes to the Elastic Beanstalk application.
2. Under settings in Developer Tools, I created a connection to my GitHub
   ![Screenshot 2025-03-29 061846](https://github.com/user-attachments/assets/d783f857-febd-4767-86fb-0f6abdb99216)
  
### 4. **Finish CodePipeline Set Up**
1. After having the required files, I created a basic pipeline
 ![Screenshot 2025-03-29 062707](https://github.com/user-attachments/assets/58e2516d-864a-427c-9fed-198736eac909)
  
2. Named it devops-lab and allowed it to create a new service role
   ![Screenshot 2025-03-29 071013](https://github.com/user-attachments/assets/efb846e5-b105-4d98-bf70-9bf4fc9aeebb)
   
4. Selected Github as source provider, selected the connection I created earlier, and chose ```devops-lab``` as the repository 
![Screenshot 2025-03-29 071301](https://github.com/user-attachments/assets/abb1f4c7-780f-4a78-b0f8-09c2973e0511)

5. I then finally configured the deploy provider as Elastic Beanstalk, chose London as region, and application name
   ![Screenshot 2025-03-29 071351](https://github.com/user-attachments/assets/3e14c34c-898b-4899-8425-91466b5879b0)

6. My pipeline is now created and ready for use. However, because there's no code to deploy, the pipleline errored:
   ![Screenshot 2025-03-29 071445](https://github.com/user-attachments/assets/02c6dccf-ac60-498b-b9a9-e7ab87b9a6e1)

### 5. **Use CloudShell to Manage Files**
1. I used CloudShell to create a new directory called devops-lab, then git cloned my ```devops-lab``` directory into it
2. I then uploaded the nodejs-blue folder into the directory
   
![Screenshot 2025-03-29 072154](https://github.com/user-attachments/assets/35a26fc3-2a23-4e47-b186-3c99072c683e)

The difference with this index.html file is that it specifies the background colour to be blue and not green

![Screenshot 2025-03-30 144741](https://github.com/user-attachments/assets/dac6b96b-742e-42c8-b7aa-1e25a3bfff16)

4. I then pushed this change into my devops-lab directory

### 6. **Tested the Entire Pipeline**
Finally, I pushed changes to the GitHub repository, triggering the pipeline to ensure everything was automated properly. 
![Screenshot 2025-03-29 080114](https://github.com/user-attachments/assets/fc418892-6e88-415d-a426-21b2fadb30a0)
![Screenshot 2025-03-29 080135](https://github.com/user-attachments/assets/3f092345-d2f0-4b46-9eb2-09ebf0930ada)

## Project Completed 🎉


- I now have a fully automated CI/CD pipeline that deploys the app from GitHub to Elastic Beanstalk.
- With AWS CodePipeline and CloudShell, I can push changes to GitHub and have them automatically deployed to my app without manual intervention.
- This setup is scalable, and I can easily integrate future updates or add new features to the pipeline.

## Reference

https://www.youtube.com/watch?v=E-YanBx38Cs&t=585s

