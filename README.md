# 105SRE_Cloud_Computing_AWS #

## Added Readme ##
### SRE ###
#### Journey ####

- This is a bullet point

- use nano to use CLI text editor
---

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

