# AWS VPC Creation Guide for Ubuntu Instance

This guide provides step-by-step instructions to create a Virtual Private Cloud (VPC) in Amazon Web Services (AWS) for hosting an Ubuntu instance.

## Prerequisites

- An AWS account
- Basic familiarity with AWS services

## Steps

### 1. Sign in to the AWS Management Console

Navigate to the AWS Management Console and sign in with your credentials.

### 2. Open the VPC Dashboard

In the AWS Management Console, navigate to the VPC Dashboard by selecting "Services" and then clicking on "VPC" under the "Networking & Content Delivery" section.

### 3. Create a VPC

- Click on the "Create VPC" button.
- Enter a name for your VPC in the "Name tag" field.
- Specify the CIDR block for your VPC. This defines the range of IP addresses for your VPC.
- Click on "Create" to create your VPC.

### 4. Create Subnets

- In the VPC Dashboard, navigate to "Subnets" in the left sidebar.
- Click on the "Create subnet" button.
- Enter a name for your subnet and select the VPC you created earlier.
- Specify the CIDR block for your subnet.
- Choose the availability zone for your subnet.
- Click on "Create" to create the subnet.

### 5. Create an Internet Gateway (IGW)

- In the VPC Dashboard, navigate to "Internet Gateways" in the left sidebar.
- Click on the "Create internet gateway" button.
- Enter a name for your internet gateway.
- Click on "Create" to create the internet gateway.
- Select the internet gateway you created and attach it to your VPC.

### 6. Update Route Tables

- In the VPC Dashboard, navigate to "Route Tables" in the left sidebar.
- Select the route table associated with your VPC.
- Click on the "Routes" tab and then click on "Edit routes".
- Add a route with destination `0.0.0.0/0` and target as the internet gateway you created.
- Click on "Save routes" to update the route table.

### 7. Launch an Ubuntu Instance

- In the EC2 Dashboard, click on "Launch Instance".
- Select an Ubuntu AMI (Amazon Machine Image) for your instance.
- Choose the instance type, configure instance details, add storage, configure security groups, and review your instance details.
- Click on "Launch" and select an existing key pair or create a new one to connect to your instance.

### 8. Connect to Your Ubuntu Instance

Once your instance is running, you can connect to it using SSH. Use the public IP address or public DNS name of your instance along with the private key associated with your key pair to establish the SSH connection.

```bash
ssh -i /path/to/your/private-key.pem ubuntu@your-instance-public-ip

