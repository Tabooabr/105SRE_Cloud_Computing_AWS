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
Also add 8080 to the address

