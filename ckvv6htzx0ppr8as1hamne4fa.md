## Create and Work With an EC2 Instance lab

Creating and working with Elastic Compute Cloud (EC2) instances is a very common occurrence with AWS. This is a basic A Cloud Guru lab walkthrough that involves creating a VPC, Security Group, key pair, and then connecting to the instance via SSH. 

![Screen Shot 2021-10-26 at 6.28.04 PM.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1636647028591/XHR1L4kGk.png)
Diagram from A Cloud Guru

Begin by navigating to the VPC menu to configure the Virtual Private Cloud where your EC2 instance will reside. 

AWS gives the option to use a VPC Wizard or create the VPC manually. We will use the manual approach here. Note: AWS by default will provide you a VPC which will work fine for this project, or select Create VPC, assign the CIDR block range, and select Create VPC again. 

Next, navigate to EC2 in the Services menu - Instances - Launch instance. If you are eligible for the AWS free tier, free options should be the default as you go through this process. You can keep the default selections including the default security group. Review your settings at the end and Launch. "Create a key pair" or use an existing one depending on your environment. Make sure you have access to the key file (.pem) and Launch Instances. 


![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1636647349869/kIs-vOE92.png)

