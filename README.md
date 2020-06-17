# Production Environment

In this project I have built a CI/CD pipeline for a microservices application for different deployment strategies. This is the capstone project of the Udacity Cloud DevOps Nanodegree Program.

I've done software projects in hackathons or just project during college. I've realized that implementing CI/CD pipelines guarantees a quality of the software product that cannot be provided by manually assessing this quality. So, the aim of this project is fitting [the rubric of the capstone project](https://review.udacity.com/#!/rubrics/2577/view) , with the final objective of automating the provision of a CI/CD environment towards a software repo, in a way imitating the service of gitlab autodevops. 

In this project, it has been chosen AWS as the cloud provider, jenkins as the CI/CD automation tool and [this react.js dashboard](https://github.com/ablazleon/ElectoDB-18-frontend) as a demo. 

## 1. Installation
## 2. Usage
## 3. Contributing
## 4. How it was developed

-------------------

## 1. Installation
## 2. Usage
## 3. Contributing
## 4. How it was developed

### Step 1: Propose and Scope the Project
Plan what your pipeline will look like.

***install -> lint***

Decide which options you will include in your Continuous Integration phase.
Use Jenkins.

Pick a deployment type - either rolling deployment or blue/green deployment.

For the Docker application you can either use an application which you come up with, or use an open-source application pulled from the Internet, or if you have no idea, you can use an Nginx “Hello World, my name is (student name)” application.

### Step 2: Use Jenkins, and implement blue/green or rolling deployment.

Create your Jenkins master box with either Jenkins and install the plugins you will need.

Set up your environment to which you will deploy code.

### Step 3: Pick AWS Kubernetes as a Service, or build your own Kubernetes cluster.
Use Ansible or CloudFormation to build your “infrastructure”; i.e., the Kubernetes Cluster.

***First, [it is created a sample cluster](!https://logz.io/blog/amazon-eks-cluster/)***

***Note that, to manage eks form cloud9 [these steps](!https://eksworkshop.com/prerequisites/k8stools/) should be followed***

It should create the EC2 instances (if you are building your own), set the correct networking settings, and deploy software to these instances.

As a final step, the Kubernetes cluster will need to be initialized. The Kubernetes cluster initialization can either be done by hand, or with Ansible/Cloudformation at the student’s discretion.

### Step 4: Build your pipeline

Construct your pipeline in your GitHub repository.

Set up all the steps that your pipeline will include.

Configure a deployment pipeline.

Include your Dockerfile/source code in the Git repository.

Include with your Linting step both a failed Linting screenshot and a successful 

Linting screenshot to show the Linter working properly.

### Step 5: Test your pipeline

Perform builds on your pipeline.

Verify that your pipeline works as you designed it.

Take a screenshot of the Jenkins pipeline showing deployment and a screenshot of your AWS EC2 page showing the newly created (for blue/green) or modified (for rolling) instances. Make sure you name your instances differently between blue and green deployments.

