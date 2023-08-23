---
title : "Create an EC2 Instance"
date : "`r Sys.Date()`"
weight : 1
chapter : false
pre : " <b> 2.1 </b> "
---

#### Introduction

Before enabling CloudTrail, we'll set up an Amazon Elastic Compute Cloud (Amazon EC2) instance to function as a web server. This will allow us to simulate the actions of a user shutting down a web server.

#### Step-by-Step Guide to Create an EC2 Instance

1. **Access EC2 Management Console**: Navigate to the [EC2 service administration interface](https://console.aws.amazon.com/ec2/).

2. **Launch Instance**: Click on **Launch Instance** to initiate the creation process.
   
   ![Launch Instance](/images/2-preparation/2.1-ec2-instance/01-launch-instance.png)

3. **Name the Instance**: Provide a name for your instance by setting the "Name" tag. For example: `workshop2-instances`
   
   ![Name the Instance](/images/2-preparation/2.1-ec2-instance/02-name-instance.png)

4. **Choose an Amazon Machine Image (AMI)**: Select the desired AMI. For example: `Amazon Linux 2 AMI`.
   
   ![Choose AMI](/images/2-preparation/2.1-ec2-instance/03-choose-ami.png)

5. **Select an Instance Type**: Choose the `t2.micro` instance type and proceed.
   
   ![Select Instance Type](/images/2-preparation/2.1-ec2-instance/04-select-instance.png)

6. **Configure Key Pair**: Choose `Proceed without a key pair`
   
   ![Configure Key Pair](/images/2-preparation/2.1-ec2-instance/05-configure-keypair.png)

7. **Launch the Instance**: Click **Launch Instance**.
   
   ![Launch the EC2](/images/2-preparation/2.1-ec2-instance/06-launch-ec2.png)

8. **Create Ec2 instance successfully**
   
   ![Created the EC2](/images/2-preparation/2.1-ec2-instance/07-ec2-created.png)

{{%notice note%}}
**Important**: Once the EC2 instance is launched, make sure to note down the EC2 instance ID for future use.
Example of Ec2 instnce ID: `i-08622517ee43ef4ed`
{{%/notice%}}

#### Upcoming Steps

With the EC2 instance up and running, we're now set to simulate user interactions and monitor them using AWS CloudTrail.
