
# Ex 4 Deployment and configuration of a Private Cloud in AWS
## REG NUMBER: 212223220036
## NAME: INESH N

## Aim:
To set up of a Private Cloud in AWS.

## Setting up of a private cloud in AWS:
Setting up a private cloud within AWS, also known as a Virtual Private Cloud (VPC), involves creating a logically isolated virtual network that you can use to launch AWS resources. This provides you with full control over your virtual networking environment, including resource placement, connectivity, and security. Amazon Virtual Private Cloud (Amazon VPC) gives you full control over your virtual networking environment, including resource placement, connectivity, and security. Get started by setting up your VPC in the AWS service console. Next, add resources to it such as Amazon Elastic Compute Cloud (EC2) and Amazon Relational Database Service (RDS) instances. Finally, define how your VPCs communicate with each other across accounts, Availability Zones, or AWS Regions.

## Procedure:

### Plan Your VPC:
● Determine your needs:

### Define your use case, including application requirements, security needs, and compliance standards.

● Plan IP address ranges:

### Choose appropriate IP address ranges for your VPC and subnets to avoid conflicts.

● Select Availability Zones:

### Decide which Availability Zones (AZs) you'll use for your resources, considering redundancy and performance.

● Plan internet connectivity:

### Determine if you need public internet access and how to configure it.

● Define security:

### Plan your security groups, network ACLs, and access controls to ensure a secure environment.

### Create Your VPC:
• Sign in to AWS Management Console: Access the VPC console and navigate to the VPC dashboard.

• Choose "Create VPC": Initiate the VPC creation process.

• Configure VPC details: Enter the VPC name, CIDR block, Availability Zones, and other necessary settings.

• Create subnets: Define subnets within your VPC to isolate different parts of your network.

• Create route tables: Specify how traffic is routed within and outside the VPC.

• Create security groups: Define access control rules for your resources.

### Deploying Resources:
• Launch EC2 instances: Create and launch virtual machines within your VPC.

• Set up RDS instances: Deploy databases for your applications.

• Configure networking: Connect your resources to the appropriate subnets, security groups, and route tables.

• Deploy other AWS services: Integrate other services like S3 for storage and Lambda for serverless computing.

### Managing and Monitoring:

• Use AWS CloudWatch: Monitor your VPC and resources for performance and health.

• Configure logging and auditing: Track access and activity within your VPC for security and compliance.

• Implement security best practices: Regularly review and update your security configuration.

• Scale and adjust as needed: Adjust your VPC infrastructure to meet changing demands.

## Output:

### Snapshot 1: Create VPC image

![op1](https://github.com/user-attachments/assets/f1bbe800-eb49-4fc4-a8b4-0b2c45b87da4)


### Snapshot 2: Configuring Subnets
![op2](https://github.com/user-attachments/assets/5c4d49dd-503e-44b7-8c00-783c7d7c9b16)

### Snapshot 3: Configure Subnets
![op3](https://github.com/user-attachments/assets/2dd70a6f-21c0-4390-9569-546792f76a81)

### Snapshot 4: Setting Internet gateway
![op4](https://github.com/user-attachments/assets/9531c864-6e80-40aa-91df-104d2a5724cc)

### Snapshot 5: Creating Internet gateway
![op5](https://github.com/user-attachments/assets/88a01fd1-add8-4f6e-a018-32d0d34edfcc)

### Snapshot 6: Setting Internet gateway
![op6](https://github.com/user-attachments/assets/b857ff77-0d91-4558-8327-c53a2887dce8)

### Snapshot 7: Creating route table

![op7](https://github.com/user-attachments/assets/5d9b8973-6962-465b-94e0-4ad0bc7f5db6)


### Snapshot 8: Configuring route table
![op8](https://github.com/user-attachments/assets/b70e1607-37e5-481a-92f2-543177903903)

### Snapshot 9: Editing routes

![op9](https://github.com/user-attachments/assets/fc6a6898-19bc-443f-93d7-369c9521ab1c)


### Snapshot 10: Creating route table
![op10](https://github.com/user-attachments/assets/75e0f1e3-cf04-45b5-a554-ee807f00c668)


## Result:
Thus, a private cloud on AWS involves using VPCs has been created for a dedicated, isolated network where we can manage our resources and control access according to our requirements.
