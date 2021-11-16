## Aurora Serverless with Lambda Functions

I decided to go through the A Cloud Guru lab "Integrating Aurora Serverless with Lambda Functions Using Python and PyMySQL" as I'm currently working on the #CloudResumeChallenge. Part of that challenge involves using DynamoDB rather than Aurora as in this lab, but I'm hoping most of the steps are similar. Aurora is serverless SQL, DynamoDB is NoSQL.

Serverless tech is very cool partly because it provides on-demand, scalable compute and storage power without having to provision and keep other types of compute power active when not needed. Not sure if it's still true, but A Cloud Guru said they only paid $400 (maybe $900?) for their monthly AWS bill which would have been around $100K (!) with traditional virtual servers. Amazing!

When the DB has no active connections, the customer only pays for storage, meaning no unnecessary charges when idle (capacity settings are customizable during set-up to scale them way down or completely off).

In the first step we use the lambda create-function CLI command to create our Lambda function. Here you set the config for the function using the ARN of the LambdaIAMExecutionRole. If successful you'll see something like this:


![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1637035884324/AmrPXE1tn.png)

Next we create a Lambda layer containing the PyMySQL Python library. PyMySQL is a library that allows us to access the DB using Python, but it's not available by default. The Lambda layer is a method to pass dependencies and code to the Lambda function. These can be reused and shared with others.

Create a zip file with the following commands: 

aws lambda publish-layer-version (then layer name, zip file name and location)

make note of the LayerVersionArn then 

aws lambda update-function-configuration (function name and ARN from last step) 


Next, we create the Aurora database using the management console with the "Serverless" option. You will set the username and password (we'll later add these to our Lambda function).

We need to then update the Lambda function to attach it to the same VPC, subnets, and SG as the database. In Edit VPC, set the VPC, Subnets, and Security groups to match the DB, or the function can't access the DB.


![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1637035913481/GJZl7hBhh.png)

Finally, we need to update the Lambda function and plug in the values/credentials of the DB cluster. The code as pictured below was provided in the lab. You will use the user credentials from the DB set-up and enter the DB endpoint as the host.


![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1637035938754/Z-jbs6w0p.png)

In the lab example, they configured the test event with just empty curly brackets. The idea is just to confirm connection from the function and DB. A successful test should yield results like this: 


![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1637035958279/iSubANgC4.png)
