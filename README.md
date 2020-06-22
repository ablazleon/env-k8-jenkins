# Production Environment

In this project I have built a CI/CD pipeline for a microservices application for different deployment strategies. This is my proposal of capstone project of the Udacity Cloud DevOps Nanodegree Program.

## 1. Installation
## 2. Usage
## 3. Contributing
## 4. How it was developed
### a. Requirement steps
### b. Roadmap
### c. Rubric

---------------

### b. Roadmap

1. Choose a github repo.

- [x] Choose an app to lint. It is choosen a [flask api boilerplate for image recognition](https://github.com/ablazleon/gorrilla).
- [x] With a dockerfile

2. Jenkins 
- [X] Tried on an EC" and discovered the benefits of Jenkins X. Setup the repo for continuous integration.
- [ ] Test pipeline: photo of a failing linting.

3. EKS. 
- [ ] Create a cluster: photo that it works manually
- [ ] Instances name rolling deployment
- [ ] The deployment works.

## Motivation

I've done software projects in hackathons or just project during college. I've realized that implementing automating pipelines for continuous integration and continuous deplyoment guarantees a quality of the software product that cannot be provided by manually assessing this quality. So, the aim of this project is fitting [the rubric of the capstone project](https://review.udacity.com/#!/rubrics/2577/view), with the final objective of creates a code that allows to easily automates this integration and deployment of a software repo in github. In general, a software is been identified to propose a certain ***value***. Then automating piepline should be provided (see image). Looking at the big picture, only three pieces are implemented in this repo:

![software product pipeline big picture](https://github.com/chanakaudaya/solutions-architecture-patterns/blob/master/vendor-neutral/images/Enterprise-CICD-Pattern.png)

Big picture from https://github.com/chanakaudaya/solutions-architecture-patterns.

1- A ***jenkinsfile***. THere are many tools for implementing pipelines (as Jenkins, Travis CI, Circle CI, Gitlab. . .) In this repo it is proposed a jenkinsfile running in an ec2 instance. After setting an ec2 with jenkins, it is deployed Jenkins X. It is realized it offers certain better cabailities as gitops and this bukernetes orientation using helm charts. So, it is configure some Jenkins X environments, following their decoumentation architecture

![Jenkins X](https://jenkins-x.io/images/jx-arch.png)

In this sample it is proposed a pipeline aproximate to this one:

Install -> lint -> test -> Rolling deployments (on certain environments)

2- A ***description file*** for k8: as the software product is structured in microservices, docker is used to conteinarized the different services, and so the development, testing and production environment can be proposed on a kubernetes cluster.

3- ***AWS***: to adapat the demand, certain cloud services are used.



-------------------

## 1. Installation
## 2. Usage
## 3. Contributing
## 4. How it was developed

### a. Requirement steps

#### Step 1: Propose and Scope the Project
Plan what your pipeline will look like.

***Install -> lint -> test -> Rolling deployments (on certain environments)***

Decide which options you will include in your Continuous Integration phase.
Use Jenkins.

Pick a deployment type - either rolling deployment or blue/green deployment.

For the Docker application you can either use an application which you come up with, or use an open-source application pulled from the Internet, or if you have no idea, you can use an Nginx “Hello World, my name is (student name)” application.

#### Step 2: Use Jenkins, and implement blue/green or rolling deployment.

Create your Jenkins master box with either Jenkins and install the plugins you will need.

*** Blue ocean is installed ***

Set up your environment to which you will deploy code.


#### Step 3: Pick AWS Kubernetes as a Service, or build your own Kubernetes cluster.
Use Ansible or CloudFormation to build your “infrastructure”; i.e., the Kubernetes Cluster.

***First, it is tried with [this cluster](!https://docs.aws.amazon.com/eks/latest/userguide/getting-started-eksctl.html). Note that, to manage eks form cloud9 [these steps](!https://eksworkshop.com/prerequisites/k8stools/) should be followed. Basically adding the administrationaccess role instead of teh eks related to the ec2***

It should create the EC2 instances (if you are building your own), set the correct networking settings, and deploy software to these instances.

As a final step, the Kubernetes cluster will need to be initialized. The Kubernetes cluster initialization can either be done by hand, or with Ansible/Cloudformation at the student’s discretion.

*** So it is isntalled jenkins X and it is then created a cluster on eks
*** THen is setup a CI pipeline wiht a python buildpack for the repo and test it** 


#### Step 4: Build your pipeline

Construct your pipeline in your GitHub repository.

Set up all the steps that your pipeline will include.

Configure a deployment pipeline.

Include your Dockerfile/source code in the Git repository.

Include with your Linting step both a failed Linting screenshot and a successful 

Linting screenshot to show the Linter working properly.

#### Step 5: Test your pipeline

Perform builds on your pipeline.

Verify that your pipeline works as you designed it.

*** Then using helm chart is deployed the service **

Take a screenshot of the Jenkins pipeline showing deployment and a screenshot of your AWS EC2 page showing the newly created (for blue/green) or modified (for rolling) instances. Make sure you name your instances differently between blue and green deployments.

### c. Rubric

#### Set up pipeline

- [x] ***Create Github repository with project code:*** All project code is stored in a GitHub repository and a link to the repository has been provided for reviewers.
- [ ] ***Use image repository to store Docker images***The project uses a centralized image repository to manage images built in the project. After a clean build, images are pushed to the repository.

#### Build Docker Container


- [ ] ***Execute linting step in code pipeline:*** Code is checked against a linter as part of a Continuous Integration step (demonstrated w/ two screenshots).
- [ ] ***Build a Docker container in a pipeline*** The project takes a Dockerfile and creates a Docker container in the pipeline.

#### Successful Deployment


- [ ] ***The Docker container is deployed to a Kubernetes cluster:*** The cluster is deployed with CloudFormation or Ansible. This should be in the source code of the student’s submission.
- [ ] ***Use Blue/Green Deployment or a Rolling Deployment successfully*** The project performs the correct steps to do a blue/green or a rolling deployment into the environment selected. Student demonstrates the successful completion of chosen deployment methodology with screenshots.

#### Bonus

- [ ] Perform additional CI steps in the pipeline outside of just linting: ***as i have integrated jenkins X is easier to include additional CI steps than with the initial Jenkins that I setup, beacuse of the jenkins X buils packs***
