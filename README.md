
# Ex 4 Deployment and configuration of a Private Cloud in AWS
## REG NUMBER: 212223220036
## NAME: INESH N

## AIM

To deploy and configure a private cloud environment in AWS using Amazon VPC, including public and private subnets, route tables, Internet Gateway, NAT Gateway, security group, and an EC2 web server.

## ALGORITHM

1. Open the AWS Management Console and select **VPC**.
2. Create a VPC using **VPC and more**.
3. Configure public and private subnets with appropriate CIDR blocks.
4. Configure an Internet Gateway and NAT Gateway.
5. Create additional public and private subnets in a second Availability Zone.
6. Configure public and private route tables.
7. Create a security group allowing HTTP traffic.
8. Launch an EC2 instance in the public subnet.
9. Configure the EC2 instance with Amazon Linux and the required User Data script.
10. Verify the web server using its Public IPv4 DNS.

## PROCEDURE

### 1. Create VPC

Create a VPC with the following configuration:

| Setting | Value |
|---|---|
| VPC | `lab-vpc` |
| IPv4 CIDR | `10.0.0.0/16` |
| Availability Zones | 1 |
| Public Subnet | `10.0.0.0/24` |
| Private Subnet | `10.0.1.0/24` |
| NAT Gateway | In 1 AZ |
| VPC Endpoints | None |

The VPC automatically creates an Internet Gateway and route tables.

### 2. Create Additional Subnets

Create the following subnets in the second Availability Zone:

| Subnet | CIDR |
|---|---|
| `lab-subnet-public2` | `10.0.2.0/24` |
| `lab-subnet-private2` | `10.0.3.0/24` |

Associate the public subnets with the public route table and the private subnets with the private route table.

### 3. Create Security Group

Create a security group:

| Setting | Value |
|---|---|
| Name | `Web Security Group` |
| Description | `Enable HTTP access` |
| VPC | `lab-vpc` |
| Inbound Type | HTTP |
| Source | Anywhere-IPv4 |

### 4. Launch EC2 Web Server

Configure the EC2 instance:

| Setting | Value |
|---|---|
| Name | `Web Server 1` |
| AMI | Amazon Linux 2023 |
| Instance Type | `t2.micro` |
| Key Pair | `vockey` |
| VPC | `lab-vpc` |
| Subnet | `lab-subnet-public2` |
| Public IP | Enabled |
| Security Group | `Web Security Group` |

Use the following User Data:

```bash
#!/bin/bash
dnf install -y httpd wget php mariadb105-server
wget https://aws-tc-largeobjects.s3.us-west-2.amazonaws.com/CUR-TF-100-ACCLFO-2/2-lab2-vpc/s3/lab-app.zip
unzip lab-app.zip -d /var/www/html/
chkconfig httpd on
service httpd start
```
### 5. Launch the instance and wait until 2/2 status checks passed.
### 6. Copy the Public IPv4 DNS.
### 7. Open it in a browser to verify the web server.


## OUTPUT

The VPC, public and private subnets, Internet Gateway, NAT Gateway, route tables, security group, and EC2 web server are successfully created.

### Snapshot 1: Create Your VPC
<img width="1919" height="875" alt="image" src="https://github.com/user-attachments/assets/ddb287c4-653c-4eea-8cfc-bdc2a84f406f" />
<img width="1919" height="865" alt="image" src="https://github.com/user-attachments/assets/3a2e4ac6-df98-4716-8907-c0244daa8316" />

### Snapshot 2: Create Additional Subnets
<img width="1919" height="862" alt="image" src="https://github.com/user-attachments/assets/40fdda28-ffcc-4e6c-94e6-7f9e26719253" />
<img width="1919" height="872" alt="image" src="https://github.com/user-attachments/assets/402cd4b2-6629-4b6f-b012-0fb21c023b30" />
<img width="1919" height="868" alt="image" src="https://github.com/user-attachments/assets/3f29fc78-ae90-4fe5-a63e-30577e26a054" />
<img width="1919" height="879" alt="image" src="https://github.com/user-attachments/assets/a9692da4-230f-4f06-a6bc-966a912c5085" />

### Snapshot 3: Create Additional Subnets
<img width="1919" height="874" alt="image" src="https://github.com/user-attachments/assets/d105c998-d756-4133-b7f2-0c78a1c70780" />
<img width="1919" height="859" alt="image" src="https://github.com/user-attachments/assets/d3be6b66-da2f-4ef2-b84b-c200d22e132d" />
<img width="1919" height="872" alt="image" src="https://github.com/user-attachments/assets/78b4a66a-c3f5-4ac0-bbe4-8476ab154d11" />

### Snapshot 4: Launch a Web Server Instance
<img width="1917" height="878" alt="image" src="https://github.com/user-attachments/assets/1f3d4992-a1b1-4f22-a03c-f26bb1ba0dbf" />
<img width="1919" height="860" alt="image" src="https://github.com/user-attachments/assets/70ce7f1e-27b3-4169-8619-acaf0b9f4521" />
<img width="1919" height="872" alt="image" src="https://github.com/user-attachments/assets/eab7a9b1-279e-41e8-9a70-6281fc7d11fc" />
<img width="1919" height="871" alt="image" src="https://github.com/user-attachments/assets/d2842579-721b-4254-bd8b-6e4b3ba36405" />

The web application is successfully accessible through the EC2 Public IPv4 DNS.
<img width="1919" height="868" alt="image" src="https://github.com/user-attachments/assets/f9c2b507-288b-4e81-8d4b-0b6941fce146" />

## RESULT
Thus, a private cloud environment was successfully deployed and configured in AWS using Amazon VPC, with public and private subnets, routing, security controls, NAT connectivity, and an EC2-based web server.

