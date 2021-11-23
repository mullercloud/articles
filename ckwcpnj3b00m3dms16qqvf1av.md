## Deploying Custom Code with a CI/CD Pipeline Using AWS CodeStar

AWS CodeStar is a set of development tools to enable rapid development and deployment of code. In this A Cloud Guru lab we use a template they provide to provision the environment, and apart from a couple of steps that involve using the console, work mostly from the CLI. This is a basic exercise and the result is to deploy a single webpage, but it was good experience in using the AWS CI/CD tools and the templates and commands that automate the services used behind the scenes. 

Some of the benefits of using infrastructure as code in this demo are visibility, as far as being able to clearly see in the template which resources will be deployed, and the provisioning process helps ensure resources are working so our environment functions as expected. 

There are additional files that AWS creates for you when a project is created through the console. Since we're mostly using the CLI in this demo, some of these files are provided by the lab for our use. 

We start by using Session Manager to access a provided EC2 instance, which was already configured with command line tools and git. A snapshot of the demo template is below, and the sections we need to update during the set-up are indicated we'll update as we add several services.

![Screen Shot 2021-11-19 at 9.35.34 PM.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1637708753221/Fu2bp54Eg.png)

Switching to the console, we create and add a CodeStar service role. This service will then be available to access through IAM roles in the console. We will use the ARN for this role to add to our template. 

![Screen Shot 2021-11-17 at 8.36.25 PM.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1637708903906/YwsQXON9q.png)

Also in the console we create an S3 bucket, VPC, and subnet details (if the defaults are available they'll work OK here). Then back to the CLI.

We need to add the bucket name, VPC and subnet IDs, and the service role ARN, and the save the updated template file.

With the above steps completed and an updated template to deploy from, we launch our CodeStar project with the command here: 

![Screen Shot 2021-11-23 at 4.57.30 PM.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1637708804306/k400QAkbZ.png)

Back to the console, and we can watch as as the services are being created within CodeStar. Once this process is finished, we can view our test website using the IP address from the EC2 instance, as shown below.

![Screen Shot 2021-11-23 at 5.03.25 PM.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1637708764653/H_5Y0qR8V.png)
