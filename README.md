# 105SRE_Cloud_Computing_AWS #

## Added Readme ##

### SRE ###
#### Journey ####

- [105SRE_Cloud_Computing_AWS](#105sre_cloud_computing_aws)
  - [Added Readme](#added-readme)
    - [SRE](#sre)
      - [Journey](#journey)
    - [Intro to AWS And Cloud Computing:](#intro-to-aws-and-cloud-computing)
  - [Why are some businessess going cloud ?](#why-are-some-businessess-going-cloud-)
    - [Benefits of cloud computing:](#benefits-of-cloud-computing)
    - [Characteristics](#characteristics)
    - [Diversion of traffic](#diversion-of-traffic)
  - [Q Regarding Today](#q-regarding-today)
  - [AWS Diagram:](#aws-diagram)
    - [How to connect to remote VM:](#how-to-connect-to-remote-vm)
  - [(some steps may need clarification)](#some-steps-may-need-clarification)
    - [Inside the VM](#inside-the-vm)
    - [File Permisions:](#file-permisions)
    - [Bash Scripting - Automate process with the script](#bash-scripting---automate-process-with-the-script)
  - [tomcat script:](#tomcat-script)
  - [Questions and R+D](#questions-and-rd)
    - [- What is a VPC](#--what-is-a-vpc)
    - [- What is an Internet Gateway](#--what-is-an-internet-gateway)
    - [- What is Route Tables](#--what-is-route-tables)
    - [- What is a subnet](#--what-is-a-subnet)
    - [- What is NACLS](#--what-is-nacls)
    - [- What is a Security Group](#--what-is-a-security-group)
    - [- How did you secure your app on the public cloud](#--how-did-you-secure-your-app-on-the-public-cloud)
    - [- What are the outbound rules for security group by default and why?](#--what-are-the-outbound-rules-for-security-group-by-default-and-why)
    - [- What is the command to kill a process in Linux?](#--what-is-the-command-to-kill-a-process-in-linux)
    - [Monolith - N-tier - 2-tier & Microservices Architecture](#monolith---n-tier---2-tier--microservices-architecture)
      - [Monolith](#monolith)
      - [N-tier](#n-tier)
      - [2-tier](#2-tier)
      - [Microservices Architecture](#microservices-architecture)
      - [Scaling up and scaling out?](#scaling-up-and-scaling-out)
      - [AWS CLI](#aws-cli)
- [Following this tutorial to setup northwind in a db](#following-this-tutorial-to-setup-northwind-in-a-db)
  - [This Diagram summarizes the end result:](#this-diagram-summarizes-the-end-result)
    - [Deploying the api:](#deploying-the-api)
  - [To test connection](#to-test-connection)
  - [Port Forwarding](#port-forwarding)
  - [Now that it is working:](#now-that-it-is-working)
- [Docker](#docker)
  - [installing Docker](#installing-docker)
  - [- Log-in to docker hub](#--log-in-to-docker-hub)
  - [Docker Commands:](#docker-commands)
  - [DockerHub](#dockerhub)
    - [Docker file to automate the process of building customised image - Building a Microservice with docker](#docker-file-to-automate-the-process-of-building-customised-image---building-a-microservice-with-docker)
  - [Create a Dockerfile for an ASP.NET Core application](#create-a-dockerfile-for-an-aspnet-core-application)
    - [Docker Compose:](#docker-compose)
- [Kubernetes](#kubernetes)
  - [Kubernetes Diagram:](#kubernetes-diagram)
    - [Kubernetes Service:](#kubernetes-service)
    - [K8 Objects:](#k8-objects)
    - [K8 Setup](#k8-setup)
  - [Kubernetes commands](#kubernetes-commands)
  - [API Using K8:](#api-using-k8)
  - [Services and Deploy files:](#services-and-deploy-files)
  - [Deploy an api in a cluster:](#deploy-an-api-in-a-cluster)
  - [The other side of the business and challenges that we have encountered:](#the-other-side-of-the-business-and-challenges-that-we-have-encountered)

### Intro to AWS And Cloud Computing: ##

- Amazon Web Services (AWS)

- why do we need cloud?
    Pay as you go: when not using it we dont pay for it. 
pay for what we use on the cloud. (cost effective).

- Go global in minutes, if you were to do it locally would take a lot of money to deploy.
therer are a lot of costs involded, whereas if you use a cloud service provider they are
in charge of all of that.
    
On the cloud no need to worry about the security of the data center.

- (on print is a local way to do the data centering)

- **Hybrid:** how is it implemented? Where a business wants to keep some services on print
and some services on cloud.

  - Banks:
    - to open a bank account you need to provide a lot of confidential details.
    some of the info they might wanna have it available to the public, but they would keep
    the confidential details on the on **prem** site, (PINS Passwords etc.) and leave the 
    rest of the public information available to the public.
- On prem : (Local)
- Cloud based (using AWS or other services).

## Why are some businessess going cloud ? ##

in 2008 Netflix went down for 3 days, the on prem site caught fire, and lost everything
they then made the decison to migrate to cloud based, using AWS and AGILE.

By 2018 2019 they had 103M active users, (a sub is 9.99), 

According to one of the officials, they said it took them 6 years to migrate everything
from on prem to completely cloud based.

### Benefits of cloud computing: ###

Pillars of cloud computing:
(investigate examples on this, how is it:)
- Ease of use
- flexibility
- robustness
- cost

### Characteristics ###

- ACES Region london, has at least 2 data centers, (availability zones) 
- why do we need multiple availability zones? 

- CDN (content delivery network) They work by getting a request and storing data on the cache. 
it get stored at the nearest available zone from the user.

- and it will display the data (like cookies), and that helps with the speed.

according to the size of the zone, they will have different AWS services. 
(for example a Sainsburys if its the biggest one, they might have more services,
such as Clothing, where not all sainsburys may have that available due to their size).

Why? (to facilitate user journey 24/7 Experiences). 

**GOVcloud:** They wont rent that, because it belongs to only the Government of the world.

How Does AWS Global provide more than 1 availability Zone?

### Diversion of traffic ###

You may divert the traffic to another availabilty zone to where the traffic may be redirected to 
(maybe due to a failure of one of the zones),
you can use autoscaling to dynamically allocate that traffic to a good available region. This allows
the service to be Highly available & Scalable.

Link here: https://aws.amazon.com/about-aws/global-infrastructure/

We need to ensure that the app is available 24/7. 

--- 

## Q Regarding Today ##

1. What is the role of SRE?
  - An SRE is responsible for making sure that a given service is up and running
  - And making sure that the user Experience is satisfactory through and through 

2. Benefits of Cloud Computing
    - Ease of use
    - Flexibility
    - Robustness
    - Cost Effective

3. AWS?

    - Amazon Web Services
    - On demand cloud computing platforms.

4. AWS Global Infrastructure?

    ![Map](map.png)
    - They have 84 availability zones with 26  Total regions

5. Regions VS Availability zones?

- Each region is a separate Geographic area.
- Availability zones may be located within a Region.
  - (data centers) 

6. What are the four pillars of cloud computing?

    - Ease of use
    - Flexibility
    - Robustness
    - Cost Effective

7. What is CDN ?

- CDN: Content Delivery Network
- Stores cache information closer to the user in a given
- availability one, so it speeds up the User experience.

8. On Prem vs Hybrid - On Prem Vs Public Cloud

- On prem means that business may use local data centres to store information, 
  - an example would be a bank storing private information sucha as passwords and other details.
    - this means that the business will be responsible for the safekeeping of that prem data center.
    - costly
    - Many bank entities prefer using a hybrid approach, meaning that they store private info on prem,
    - but will keep public information on the cloud service to reduce costs.
 - Prem vs public cloud:
     - Prem vs public cloud, like descreibed before, it implies the costs of having a service on a local 
     - prem (data center), this is very costly and the company has to risk the information being lost (netflix fire)
     - If cloud is used the provider is responsible for the safekeeping
     - of that data center, and it follows a pay as you go model.
--- 

## AWS Diagram:


![image](https://user-images.githubusercontent.com/34945430/159507487-54f1dedb-e809-4686-a3a8-709afb316145.png)


### How to connect to remote VM: ###

1. put the SSH key into your .ssh folder (C/users/username/.ssh)
2. In AWS Select EC2
3. Create a new instance (in this case ubuntu v 18.04)
4. add a name
5. add security groups:
    - make sure to restrict access in SSH selecting proper port
    - allow access to vm through HTTP
    - and set ssh as private
6. Launch and connect following the instructions from
AWS

7. **Remember to stop the instance when not using the vm through the AWS website** 
(some steps may need clarification)
---
Cheatsheet: https://www.guru99.com/linux-commands-cheat-sheet.html

### Inside the VM ##

1. Run: `sudo apt-get update -y`
2. run: `sudo apt-get upgrade -y`
3. run: `sudo apt-get install nginx -y`
4. Check that it was installed sucessfully through checking the public IP

How to check status of nginx or anything:

*Note: "sudo" gives you admin priviledges when running a command*

- How to check a given service:

`systemctl status name_service`

- How to start a service:

`sudo systemctl start name_service`

- How to stop a process:

`sudo systemctl stop name_service`

- How to enable service:
 `sudo systemctl enable service_name`

- How to install a package:

    `sudo apt-get install package_name -y`
    
    `sudo apt install package_name -y` *(also works for newer V)*

- How to remove a package:`sudo apt remove package_name -y` 
- How to check all processes: `top`
- Who am I `uname` or `uname -a` 
- Where am I `pwd` 
- Create a directory: `mkdir dir_name`
- How to check dir `ls` or `ls -a`
- How to create a file `touch name_file` or `nano file_name` 
- How to check content of the file without going inside of the file: `cat file_name`

- how to copy a file `copy file.txt form current location to sre folder`

- move a file: `mv /current_location_of_the_file_you_want_to_copy/target_file   /Destination_where_you_want_to_move_that_file_to/`
    or `sudo mv filename ~/filenamenew`
- how to move back `cd -` or `cd ..`
- how to delete folder `sudo rm -rf folder_name` *(Dangerous, doesn't ask if sure to remove)*

### File Permisions: ###

- How to check a file permision `ll`
- Change file permission `chmod required_permision file_name`
- Write `w` read `r` exec `x`
- https://chmod-calculator.com


### Bash Scripting - Automate process with the script ###

- code block
```bash
#!/bin/bash

# run update

sudo apt-get update -y

# run upgrades

sudo apt-get upgrade -y

# install nginx

sudo apt get install nginx -y

# Ensure it's running - start nginx

sudo systemctl start nginx

# Enable ngin


```

- Change the file to exe file `sudo chmod +x provision.sh`
- How to run an exe file `./provision.sh`

---

## tomcat script: ##

```bash 
#!/bin/bash
  # install nginx
  sudo apt install tomcat9 -y
  # ensure it's running - start nginx
  sudo systemctl start tomcat9
  # enable nginx
  sudo systemctl enable tomcat9
  # allow traffic to port 8080
  sudo ufw allow from any to any port 8080 proto tcp
```
Also add 8080 to the Security groups
then add :8080 to the http
Also this was useful:
https://devops4solutions.com/installation-of-tomcat-on-aws-ec2-linux-integration-with-jenkins/

--- 

## Questions and R+D ##

![image](https://user-images.githubusercontent.com/34945430/159764195-148f2220-8687-4749-85bd-1ef5ea415331.png)

### - What is a VPC ###
-   Virtual Private Cloud
-   A virtual Network dedicated to your account on the service
-   Private instance that is secure and Isolated within a Public Cloud
-   Stores Data
-   Run Code
-   Host Websites
### - What is an Internet Gateway ###
- A horizontally Scaled, Redudntant and highly available VPC component
- Allows Communications between VPC and Interent
- Enables the resources like EC2 Instances to connect to the internet if they have a public IPV4 or 6 Address
- Provide a target in your VPC Route Tables for traffic routing
- Perform Network Address Translation for instances for traffic routing
### - What is Route Tables ###
- A set of rules called routes that determine where network traffic from your subnet or Gateway is directed
- local route for communication within the VPC
### - What is a subnet ###
- a range of IP adresses in your VPC
- Dividing the network into two or more networks
- Public and Private Subnet exist
### - What is NACLS ###
- Network Access Control List
- Optional Security layer
- Acts as a Firewall for controlling traffic in and out of one or more subnets
### - What is a Security Group ###
- A virtual firewall that controls traffic
- Decides what traffic leaves and reaches the resources it is associated with
- EG Ec2 instance where our security group we added 8080 to allow Tomcat to access
### - How did you secure your app on the public cloud ###
- By using security groups and allowing only Heavily used and necessary ports   
- Tomcat: 8080
- We restrict traffic allowing to enter or exit different adresses within our app
### - What are the outbound rules for security group by default and why? ###
- Default is all inbout traffic from resources that are assigned to the same security group
- Allows all outbound IPV4 traffic
- Allows IPV6 traffic if vpc has an associated ipv6 Block
### - What is the command to kill a process in Linux? ###
```bash
Kill processID
SigKill ProcessID / Kill-9 ProcessID
```
Illustration:

![image](https://user-images.githubusercontent.com/34945430/159765083-275793cc-3a9a-44e9-9416-f08f0688a16d.png)

---

### Monolith - N-tier - 2-tier & Microservices Architecture ###

#### Monolith ####
- One big service
- Simple but has limitations and complexity
- Heavy apps can slow down the startup tim
- Each update results into redeploying the full stack app
- Challenging to scale up
- Perfect for small services that don't require scaling
- Schools and smaller business that know they wont scale

#### N-tier ####
- An N-tier architecture divides an application into logical layers and physical tiers.
- Layers are a way to separate responsibilities and manage dependencies.
- Each layer has a specific responsibility.
- A higher layer can use services in a lower layer, but not the other way around.
![image](https://user-images.githubusercontent.com/34945430/159960917-bf7c2a36-2c69-41f7-9fd6-71dda4759fae.png)

#### 2-tier ####
- A two-tier architecture is a software architecture in which a presentation layer or interface runs on a client, and a data layer or data structure gets stored on a server.
- Separating these two components into different locations represents a two-tier architecture, as opposed to a single-tier architecture.
#### Microservices Architecture ####
![image](https://user-images.githubusercontent.com/34945430/159960853-039d5e1a-ea70-4962-a500-e47d6187d9e4.png)

for example: Netflix and banks, whos business needs depend on having an available app 24/7. or that know their service will scale up inmensely.

#### Scaling up and scaling out? ####

caling up is increasing the size of the database (pisical)
where scaling out is used to allow more traffic.

---

https://medium.com/@ahshahkhan/devops-culture-and-cicd-3761cfc62450

What is Docker? 

- Its a virtualization platform to containerise your app, it enables to build a container image and use it across the development process.
- Allows you to split non dependent steps and run them in parallel.
- run apps in containers instead of VMs is becoming popular.

CI CD?
- Continous integration and continous delivery and deployment. (Pipeline)
-its the backbone  of the devops Practices and Automation.

CI: 
- Developers merge/commit code to master branch multiple times a day, fully automated build and test process which gives feedback within few minutes.

CD:
-is an extension of continuous integration to make sure that you can release new changes to your customers quickly in a sustainable way. This means that on top of having automated your testing, you also have automated your release process and you can deploy your application at any point of time by clicking on a button.

CI CD:

![image](https://user-images.githubusercontent.com/34945430/159910966-8a296c1f-8947-4048-b9ac-0e73870daa85.png)

Best tools to build CICD pipeline?
Jenkins Circleci, teamcitym, bamboo, gitlab

Jenkins:
![image](https://user-images.githubusercontent.com/34945430/159911158-b1e755e2-944e-4a3d-8720-1357beae32f2.png)

---
Business and production
SDLC – software development life cycle
It’s the process of end to end product development.
Products need to follow a certain life cycle.
The Stages are:
•    Planning
Just an idea, only in someone’s head
•    Designing
Writing out how the product will look and what it needs.
•    Development
Develop an environment that works for all of us. i.e the linux instance we created
Implementing the design.
•    Testing
Nothing goes to production without testing.
The test must pass in order to go to the next stage.
Beta versions can happen after testing to get feedback from the user.
•    Staging
It’s the holding area before the code gets deployed. The program is packaged and ready, just on hold till the release date. After staging the code is deployed.



Github
-    One person reviewing is always the best.
-    Someone who is more knowledgeable should merge.
-    Git enter will tell you all the commands that can be performed on git
-    If you delete the .git file you need to reconnect to the github remote before pushing the code back to github.

---

<h3> S3 </h3>

- What is it:

- Amazon S3 or Amazon Simple Storage Service is a service offered by Amazon Web Services that provides object storage through a web service interface. Amazon S3 uses the same scalable storage infrastructure that Amazon.com uses to run its global e-commerce network.
- Simple storage service
- used in data backup, Disaster recovery plan (DR)
- S3 Classes

#### AWS CLI ####

1. `aws configure`
2. (input id keys region format)
3. `aws s3 ls` (using aws go to s3 and do this command
4. `aws s3 mb s3://105-sre-aaron` (how to make a folder)

**How to upload to S3:**

5. (make any file)
6. `aws s3 cp test.txt s3://105-sre-aaron` (aws service name-of-file path)

**Download data from s3:**

`aws s3 cp s3://105-sre-aaron/test.txt ~/`

**Delete bucket and text file**
`aws s3 rb s3://105-sre-aaron`
(rememebr to delete whats inside with `rm`)

--- 

# Following this tutorial to setup northwind in a db #

## This Diagram summarizes the end result: ##

![image](https://user-images.githubusercontent.com/34945430/160295820-98b969ef-8159-4208-8114-725241d29592.png)


Start installing MSSQL server following this tutorial:

https://www.youtube.com/watch?v=bzOljuaYeUk

Changes from the video: 
1. use the EC2 Public ip when connecting through Microsoft Server SQL tools.
command to acces the SQL server: `sqlcmd -S localhost -U SA -P 'password'`

After installing MSSQL Server and being able to access it, 

2. it is required to change the connection strings inside the app:

(change localhost, add ID, and password to the connection strings)
Inside the Json Config:

![string connection](https://user-images.githubusercontent.com/34945430/160294224-14dad5e2-e9f9-4813-ac9d-7e1dac54da02.png)

Inside Program:

![image](https://user-images.githubusercontent.com/34945430/160294244-d54666c3-9334-44e2-a4b2-ba1e0ec70374.png)

Inside the product context:

![image](https://user-images.githubusercontent.com/34945430/160294271-dc4e978b-7400-4e78-9986-42c95673c974.png)

3. Package the Api to Ubuntu (in VS tterminal) with this command: `dotnet publish -c release -r ubuntu.18.04-x64`
3.1  zip it, paste it into the .ssh folder.

### Deploying the api: ##

1. Launch a new instance for the API (Has to be in the local machine) and then send it to the instance with this:

`scp -i "105.pem" Apizip.zip ubuntu@ec2-x-xxx-xxx-xxx.eu-west-1.compute.amazonaws.com:~/api.zip`

2. SSH into the remote machine 
3. Install unzip `sudo apt install zip`
4. Unzip the api file: `sudo unzip api.zip`
5. Cd Into the ubuntu files, then find the api file and change its permissions to be executable
`sudo chmod 777 ProductsApi` (tabbing helps)
6. Run the new executable with `./ProductsApi`

next testing local connection:

## To test connection ##

 `curl localhost:5000/api/Employees/1`
 You should retrieve information if you change the information correctly:

EG:

![image](https://user-images.githubusercontent.com/34945430/160295408-2bf24334-2b19-407e-b35f-781ad91c3725.png)

If you can retrieve information then continue with port forwarding:

## Port Forwarding ##

1. Install Nginx

Original link: https://docs.microsoft.com/en-us/aspnet/core/host-and-deploy/linux-nginx?view=aspnetcore-6.0

Use `apt-get` to install Nginx. The installer creates a systemd init script that runs Nginx as daemon on system startup. Follow the installation instructions for Ubuntu at Nginx: Official Debian/Ubuntu packages.

 Note

If optional Nginx modules are required, building Nginx from source might be required.

Since Nginx was installed for the first time, explicitly start it by running:

```Bash


sudo service nginx start
```
Verify a browser displays the default landing page for Nginx. The landing page is reachable at http://<server_IP_address>/index.nginx-debian.html.

2. Configure Nginx
To configure Nginx as a reverse proxy to forward HTTP requests to your ASP.NET Core app, modify `/etc/nginx/sites-available/default.` Open it in a text editor, and replace the contents with the following snippet:


```bash
server {
    listen        80;
    server_name   example.com *.example.com;
    location / {
        proxy_pass         http://127.0.0.1:5000;
        proxy_http_version 1.1;
        proxy_set_header   Upgrade $http_upgrade;
        proxy_set_header   Connection keep-alive;
        proxy_set_header   Host $host;
        proxy_cache_bypass $http_upgrade;
        proxy_set_header   X-Forwarded-For $proxy_add_x_forwarded_for;
        proxy_set_header   X-Forwarded-Proto $scheme;
    }
}
```

![image](https://user-images.githubusercontent.com/34945430/160295051-ec4dc5dd-98ac-4eec-8a30-8ff452cca0d1.png)

(if it doesn't work) Then follow this:

https://github.com/mahedee/Articles/blob/master/dot-net-core/HowToHostASP.NETCoreWebAPIwithMSSQLServerOnLinuxWithNginxFromScratch.md

Step 7 & 9.

Then test the connection through the website and it should all run:

## Now that it is working: ##

SSH into the app and run the ./ProductsApi 
Test any ends:
![image](https://user-images.githubusercontent.com/34945430/160295269-615c080a-4e8a-4e53-bfae-31d87b0469e0.png)

---

![image](https://user-images.githubusercontent.com/34945430/160573860-26ab0db3-4749-4d9e-b9f3-882b064eb49c.png)


# Docker #

Docker is a set of platform as a service products that use OS-level virtualization to deliver software in packages called containers. 

It works by running commands and trying to find local containers in our machine, if it doesn't appear, it will go to the registry (docker hub) to find the container.

Docker was live in 2013, and by 2017 20% of tech companies have containers deployed, and in 2020 50% of organizations have adopted Docker and deployed docker containers.


![image](https://user-images.githubusercontent.com/34945430/160572309-77559e28-6512-4a65-b6a3-5bedb403e0ed.png)


Virtualisation Vs Docker: 

![image](https://user-images.githubusercontent.com/34945430/160571936-48be9dd8-99b7-4519-b404-8c599a37881e.png)




- Why docker? 

- docker is very user friendly, starts faster and the size required is small compared to having a VM.
if you make a VM it will take away 50% of the power of your machine, where as docker would take the resources on demand only.

![image](https://user-images.githubusercontent.com/34945430/160584975-55b37858-db63-4988-bbe8-2ab843084c56.png)


![image](https://user-images.githubusercontent.com/34945430/160372106-253a79c1-3fc6-4813-b46e-1068c1c6641e.png)


- What are volumes? 

Docker volumes are directories and files that exist on the host file system outside of the Docker container. These volumes are used to persist data and share data between Docker containers. Docker supports the mounting of one or more data volumes from the host OS to the Docker container.


## installing Docker ##

Guide: https://docs.docker.com/desktop/windows/install/

Prerequisites:

- Enable CPU virtualisation in your bios
- In windows features turn on Hyper-Visor

Installation instructions:

- Download and install docker hub
- Should get messege asking you to install WLS2 (windows linux subsystem)
- Log-in to docker hub
---
## Docker Commands: ##
Docker commands:

`Docker images:` Will present the images available

`Docker ps`: To check the containers running

`Docker ps -a`: To check every container running including hidden files

`Docker pull`: to pull the image from docker hub

`Docker run` : to run the image live directly from dockerhub

`docker exec -it [container id] bash`: to access the running container

`docker stop`: stops a running container

`docker kill`: kills container by stopping execution. stop gives time to shut down gracefully

`docker commit [container id][username/imagename]`: creates new image of an edited container on local system

`docker rm [container id]`:removes container

`docker history [image name]`: to view history

`docker image rm [image name]`: deletes image

 - Making docker docs available on our localhost 

```bash

docker run -d -p 4000:4000 docs/docker.github.io 

# Logging into a running container

docker exec -it <container-id/name> sh

# Port mapping in our containers with localhost

docker run -d -p localhost-port:container-port

# Copying files to container

docker cp <file to copy> <container_id>:<path/to/file>
#(Easier if you git bash from the path of the file you want to copy)

# Running a container with ghost

docker run -d -p 2368:2368 ghost

# Running nginx on port 80

docker run -d -p 80:80 nginx

# Replacing nginx default page

docker cp index.html <imageID>:/usr/share/nginx/html
```

Docker Cheatsheet: https://dockerlabs.collabnix.com/docker/cheatsheet/

## DockerHub ##

- Make a commit: `docker commit container_id <Docker_id>/<repo_name>:<tag>`

- Push commit to repo: `docker push <Docker_id>/<repo_name>:<tag>` (Name of image must match name of repo or it wont work).

- Pull the repo: `docker run -d -p 80:80 <Docker_id>/<repo_name>:<latest>`

### Docker file to automate the process of building customised image - Building a Microservice with docker

- Crio - Rocket - Docker
- Automate image building of our customised nginx image
- create a `Dockerfile` in the same loacation where our index.html is
- Decide which base image to use for your image

```bash


# Select Base image

FROM nginx

# Label it - add optional details

LABEL MAINTAINER=AARON

# copy the data  from localhost to Container
# copy index.html to ?usr?share?nginx/html/

COPY index.html /usr/share/nginx/html/

# expose the required port - port 80

EXPOSE 80

# launch the app 

CMD ["nginx", "-g", "daemon off;"]
# CMD will run the command in this case to launch the image when we create a container

```
---

## Create a Dockerfile for an ASP.NET Core application

Create a Dockerfile in your project folder.
Add the text below to your Dockerfile for either Linux or Windows Containers. The tags below are multi-arch meaning they pull either Windows or Linux containers depending on what mode is set in Docker Desktop for Windows. Read more on switching containers.
The Dockerfile assumes that your application is called aspnetapp. Change the Dockerfile to use the DLL file of your project.
```bash
# syntax=docker/dockerfile:1
FROM mcr.microsoft.com/dotnet/sdk:6.0 AS build-env
WORKDIR /app

# Copy csproj and restore as distinct layers
COPY *.csproj ./
RUN dotnet restore

# Copy everything else and build
COPY ../engine/examples ./
RUN dotnet publish -c Release -o out

# Build runtime image
FROM mcr.microsoft.com/dotnet/aspnet:6.0
WORKDIR /app
COPY --from=build-env /app/out .
ENTRYPOINT ["dotnet", "aspnetapp.dll"]
To make your build context as small as possible add a .dockerignore file to your project folder and copy the following into it.
```
```bash 
bin/
obj/
```

### Docker Compose: ###
```docker
Docker Compose (YAML)
version: '3'
services:
  db:
    image: the1taboo/mssql-northwind
    environment:
      ACCEPT_EULA: "Y"
      SA_PASSWORD: "1password4all!"
      MSSQL_PID: Express
    ports:
      - "1433:1433"
  products-api:
    build: .
    ports:
      - "80:80"
    depends_on:
      - db
```
Before running this make sure Port 80 and Port 1433 are open
Refactor the code to so connection string contains server = db, 1433 (matches the name in docker-compose.yaml)
Creates the MSSQL database with Northwind using shakilrahman/mssql-northwind
Creates the API using the Dockerfile
Run: docker-compose up
Two Containers should be created and the API should run on Port 80 (localhost)
Tutorial: https://www.youtube.com/watch?v=4V7CwC_4oss

---
# Kubernetes #

![image](https://user-images.githubusercontent.com/34945430/160809058-31bb38eb-2331-4f94-b14f-10f8c1d6bf11.png)


What is it and why is it used?

- What is Kubernetes and why it is used?
Kubernetes is a portable, extensible, open-source platform for managing containerized workloads and services, that facilitates both declarative configuration and automation. It has a large, rapidly growing ecosystem. Kubernetes services, support, and tools are widely available.
- Kubernetes, also known as K8s, is an open-source system for automating deployment, scaling, and management of containerized applications.

- It groups containers that make up an application into logical units for easy management and discovery.

- Kubernetes builds upon 15 years of experience of running production workloads at Google, combined with best-of-breed ideas and practices from the community.

- Developed and run by Google for over 15 years
- Now owned by the Linux foundation and is open-source
- Used to Orchestrate the containers and Organise how they connect
Advantages:
 - Self Healing: When a pod crashes another is spun up automatically
 - Load Balancing: When a pod crashes the load balancer redirects the traffic to another pod
 - Auto Scaling: Allows you to create more pods when required
 - Automated rollouts and rollback: When an image is not working it can rollback to a working version
 - Each pod (smallest item in K8) has its own IP address
- If a pod crashes then the controller-manager will delete the pod and then creates a replica
Load balancer will redirect the traffic to another pod (Scheduler)

## Kubernetes Diagram: ##
Diagram

![image](https://user-images.githubusercontent.com/34945430/160861679-2c35585b-89df-4881-978e-f39ba84a4ea3.png)

Best Practice
Start with a small team, test, learn and move on
Use Docker to contrainerise your apps for fast and constant delivery
Orchestration with K8 to make your life easier

![image](https://user-images.githubusercontent.com/34945430/160811596-0a27cb44-c418-4bcf-88b1-4c1269fe2cc7.png)


See further info here: https://kubernetes.io/docs/concepts/architecture/ 

- Cluster Architecture
- Nodes
- Control Plane-Node Communication
- Controllers
- Cloud Controller Manager
- Container Runtime Interface (CRI)
- Garbage Collection

### Kubernetes Service: ###

![image](https://user-images.githubusercontent.com/34945430/160810999-fc9a4ddd-9c40-470b-9edf-3e754dddc181.png)

- What is a service in K8? 
    - A Kubernetes service is a logical abstraction for a deployed group of pods in a cluster (which all perform the same function). Since pods are ephemeral, a service enables a group of pods, which provide specific functions (web services, image processing, etc.) to be assigned a name and unique IP address (clusterIP).

### K8 Objects: ###

- Kubernetes objects are entities that are used to represent the state of the cluster. An object is a “record of intent” – once created, the cluster does its best to ensure it exists as defined. This is known as the cluster's “desired state.”



### K8 Setup ###

Follow this guide for setting up with Docker: 

https://docs.docker.com/desktop/kubernetes/

(Check here: https://kubernetes.io/docs/tasks/tools/)

## Kubernetes commands ##

```bash

#  services: deployment, service, pods, replicasets, crobjob, autoscalinggroup, horizontal pod scaling group (HPA)

# Kubect get service_name - deployment - pod - rs

# kubectl get deploy nginx_deploy (nginx_svc)

# kubectl get pods 

# kubect describe pod pod_name

```



Find more information at: https://kubernetes.io/docs/reference/kubectl/overview/

```bash
Basic Commands (Beginner):
  create        Create a resource from a file or from stdin
  expose        Take a replication controller, service, deployment or pod and expose it as a new Kubernetes service
  run           Run a particular image on the cluster
  set           Set specific features on objects

Basic Commands (Intermediate):
  explain       Get documentation for a resource
  get           Display one or many resources
  edit          Edit a resource on the server
  delete        Delete resources by file names, stdin, resources and names, or by resources and label selector

Deploy Commands:
  rollout       Manage the rollout of a resource
  scale         Set a new size for a deployment, replica set, or replication controller
  autoscale     Auto-scale a deployment, replica set, stateful set, or replication controller

Cluster Management Commands:
  certificate   Modify certificate resources.
  cluster-info  Display cluster information
  top           Display resource (CPU/memory) usage
  cordon        Mark node as unschedulable
  uncordon      Mark node as schedulable
  drain         Drain node in preparation for maintenance
  taint         Update the taints on one or more nodes

Troubleshooting and Debugging Commands:
  describe      Show details of a specific resource or group of resources
  logs          Print the logs for a container in a pod
  attach        Attach to a running container
  exec          Execute a command in a container
  port-forward  Forward one or more local ports to a pod
  proxy         Run a proxy to the Kubernetes API server
  cp            Copy files and directories to and from containers
  auth          Inspect authorization
  debug         Create debugging sessions for troubleshooting workloads and nodes

Advanced Commands:
  diff          Diff the live version against a would-be applied version
  apply         Apply a configuration to a resource by file name or stdin
  patch         Update fields of a resource
  replace       Replace a resource by file name or stdin
  wait          Experimental: Wait for a specific condition on one or many resources
  kustomize     Build a kustomization target from a directory or URL.

Settings Commands:
  label         Update the labels on a resource
  annotate      Update the annotations on a resource
  completion    Output shell completion code for the specified shell (bash or zsh)

Other Commands:
  api-resources Print the supported API resources on the server
  api-versions  Print the supported API versions on the server, in the form of "group/version"
  config        Modify kubeconfig files
  plugin        Provides utilities for interacting with plugins
  version       Print the client and server version information

Usage:
  kubectl [flags] [options]
```
## API Using K8: ##

![structure](https://user-images.githubusercontent.com/34945430/160864871-59ada508-4b79-406b-8faf-ba225811dea3.png)

## Services and Deploy files: ##

Service:
```yml
---
# Select the type of API version and type of service/object
apiVersion: v1
kind: Service
# Metadata for name
metadata: 
  name: api-svc
  namespace: default #
# Specification to include ports Selector to connect to the deployment
spec: 
  ports:
  - nodePort: 30443 # Range is 30000 - 32768 will have ufw these ports or make SG
    port: 82 #port for localhost
    protocol: TCP
    targetPort: 80

# Let's define the selector and label to connect to nginx deployment
  selector:
    app: api

  #Creating LoadBalancer type of deployment
  type: LoadBalancer
```
Deployment yml:

```yml
# K8 works with API versions to declare the resources
# We have to declase to apiVersion and the kind of service/component
# services: deployment, service, pods, replicasets, crobjob, autoscalinggroup, horizontal pod scaling group (HPA)
# kubectl get service_name - deployment - pod - rs
# kubectl get deploy nginx_deploy (nginx_svc)
# kubectl get pods
# kubectl describe pod pod_name

# YML is case sensitive - indentation of YML is important
# use spaces not a tab
apiVersion: apps/v1 # which api to use for deployment
kind: Deployment # what kind of service/object you want to create

# what would you like to call it - name the service/object
metadata: 
  name: nginx-deployment


spec: 
  selector:
    matchLabels:
      app: nginx # look for this label to match with k8 service

  # Let's create a replica set of this with 3 instances/pods
  replicas: 3

  # Template to use it's label for K8 service to launch in the browser
  template: 
    metadata:
      labels: 
        app: nginx # This label connects to the service or any other K8 components
    
    #Let's define the container spec:
    spec:
      containers:
      - name: nginx
        image: the1taboo/105_sre_aaron_nginx
        ports:
        - containerPort: 80

# create a kubernetes nginx-service.yml to create a k8 service
```


## Deploy an api in a cluster: ##

1. Install docker.io 
```bash
sudo apt-get remove docker docker-engine docker.io containerd runc
sudo apt install docker.io -y
```
2. Install KubeCTL:

```bash
curl -LO https://storage.googleapis.com/kubernetes-release/release/`curl -s https://storage.googleapis.com/kubernetes-release/release/stable.txt`/bin/linux/amd64/kubectl

#then 

chmod +x ./kubectl

#then

sudo mv ./kubectl /usr/local/bin/kubectl

```
3. install minikube:

```bash

curl -Lo minikube https://storage.googleapis.com/minikube/releases/latest/minikube-linux-amd64 

#then 

chmod +x minikube 

#then

 sudo mv minikube /usr/local/bin/
```
4. SCP your YML Services and deploy files into the Ec2 Instance

```bash
 scp -i ~/.ssh/105.pem api-test-deploy.yml ubuntu@ec2-54-xx-xxx-xxx.eu-west-1.compute.amazonaws.com`
```

5. Check Minikube Version

```bash 
minikube version
```

6. Install conntrack 

```bash 
$ sudo apt install conntrack
```

7. Running Minikube on EC2 Ubuntu
Become a root user.

```bash
sudo -i
```

8. Run the containers:

```bash
`kubectl create -f api-test-deploy.yml`

# Then (it is very important to run the deploy before service)

`kubectl create -f api-test-service.yml`
```

9. Get the public ip, and select the node port:

## The other side of the business and challenges that we have encountered: ##

- Notes
- Using Microsoft Technologies they had issues developing their tech in docker.
- size of containers is big and deployment slow, suggested to use multi stage-deployment.
- AKS manage service on Azure
- Lightweight, so much better than VMs
- The less technicall people are not that involved in the technical side
- Contanerization and Orchestration (autoscaling, self healing, replica sets, pods) (It's hard to explain apparently)

invest in the technologies that the business is using, develop yourself and add value to the business, for example by doing certifications, 
real life examples and professionals.

Upskill in one area and reskill later on.

In 5 years time if playing the cards right, you could earn 50k.
Working alone will not make you stand out, but you need to seek to develop yourself 

C#, ASP.NET, Docker and Kube -- Microsoft 

Be positive.