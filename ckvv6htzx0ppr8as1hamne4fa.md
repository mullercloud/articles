## Create and Work with an EC2 Instance lab

Creating and working with Elastic Compute Cloud (EC2) instances is a very common occurrence with AWS. This is a basic A Cloud Guru lab walkthrough that involves creating a VPC, Security Group, key pair, and then connecting to the instance via SSH. 

![Screen Shot 2021-10-26 at 6.28.04 PM.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1636647028591/XHR1L4kGk.png)
Diagram from A Cloud Guru

Begin by navigating to the VPC menu to configure the Virtual Private Cloud where your EC2 instance will reside. 

AWS gives the option to use a VPC Wizard or create the VPC manually. We will use the manual approach here. Note: AWS by default will provide you a VPC which will work fine for this project, or select Create VPC, assign the CIDR block range, and select Create VPC again. 

Next, navigate to EC2 in the Services menu - Instances - Launch instance. If you are eligible for the AWS free tier, free options should be the default as you go through this process. You can keep the default selections including the default security group. Review your settings at the end and Launch. "Create a key pair" or use an existing one depending on your environment. Make sure you have access to the key file (.pem) and Launch Instances. 


![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1636647349869/kIs-vOE92.png)

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1636648947742/-1TD6sHn1j.png)

Next we will SSH into the instance. From the EC2 menu, select your instance and Connect. AWS gives a few options including SSH which we'll use here. You will need to modify permissions on your .pem key file from the last section. CD into the key file folder and run chmod 400 to modify the file to owner read only permissions. You will then use "ssh -i (your .pem file name) ec2-user@ " to connect to your instance. (You can simply copy and paste these commands from the AWS instructions. 

If you see something like the image below you have successfully connected to your instance! To clean up your environment you can terminate the instance and delete the VPC if necessary. 


![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1636648966837/2fLFqYaJf.png)
