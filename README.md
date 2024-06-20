# Class agenda & tools
	Day 1 tools: google sheet & browser / lab setup = homework / Day 2 tools: AWS lab setup
	This is a 2 day class with 2 hours each day
	Do NOT do lab setup in class - I will cover setup and the details are below
## Days this was a 2 day 2*2 course in the past
	You only need a browser and the google sheet to do all the activities of first part of class
	You must do the part 1 activities for the lab and part 2 to make sense.( you can watch but how much fun is that?

# Building the lab 20240619
* 	You can run the class without the lab up to a point
*	We can build the lab after beginning of class

# AWS Lab Environment Deployment Guide
	You will not need to install any software locally to run this lab.
	You will need an AWS account and a creditcard on file with Amazon.
	This will cost less than two dollars per hour while it is running
	VERSION: 20240430.01
## 9 minute video walk-thru of lab setup & tear down https://vimeo.com/941430484

### AWS account
	To build your AWS account consider using a non-work / disposable email adddress.
	You cannot use a one-time use email address.
	https://portal.aws.amazon.com/billing/signup#/start/email
### Choose a region
*	In order track costs easily deploy in an empty region (where no other machines are deployed).
#### Run this test to determine your closest region:
*	https://cloudpingtest.com/aws
*	>200 ms is going to slow your lab down.
### Create SSH keypair in EC2
Follow the steps [here](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/create-key-pairs.html#having-ec2-create-your-key-pair) 
This is used to create an SSH key pair for connecting to the attacker machine in emergencies.
Name your key 'lab' and append today's date, Example 'lab20240430'
Windows users = .ppk
The key will automatically download
## Deployment Guide:
1. Login to the AWS Console
2. Search for CloudFormation in service
3. Click Create Stack > With New Resources (standard)
4. Give the stack same name as your SSH key, Example 'lab20240430' 
5. For template source, https://20240311-drb-ctf.s3.amazonaws.com/CAP-flag-v5.yml
   _This may be turned off until class time_
6. Fill in the parameters
- PublicIpAddress: Your public IPv4 address.
  This can be acquired by searching https://whatismyipaddress.com/
- SSHKeyPair: key pair you created above will be listed in the drop down
7. Click (Next)
8. Scroll to bottom: you must CHECK I acknowledge that AWS CloudFormation might create IAM resources.
9. Click (Create stack)
### Next Step -wait
It will take several minutes for the resources to be created
- You only need the public IP address of the Guacamole (this is a browser that only lets you connect to your KALI instance)
### Connecting to Guacamole
10. Search for E2 console at top of browser
11. Identify the guacamole public IP address
- Name of instance will say "This-Pub-IP-ADDRESS-GUAC"
12. Type IP into your browser
13. Login kali with password kali
- the first time this console loads it might take 5 minutes for the interface to display
### Smile yout lab is ready

## Cleaning Up
When you are done using the solution, you will want to tear down the resources you built in order to prevent unwanted costs in your AWS account.

### You will CONTINUALLY incur charges from AWS if you DO NOT clean up
Stopping instance will REDUCE charges and allow you to do the lab on your own.

### CloudFormation clean up
1. Go to AWS CloudFormation console, https://console.aws.amazon.com/cloudformation/home
2. Select the stack you built previously and click Delete. 
- This will delete all resources for the solution
- At this point, your account is clear of all resources created by this solution.

# FILES
## They are not perfect, if you have constructive ideas on improvement email me.
## You do not need these files to attend class.
## I do make changes and trim down these files at class time due to the compressed schedule 

