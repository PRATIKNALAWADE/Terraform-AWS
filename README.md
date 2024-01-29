# Terraform-AWS

Terraform script that is well-structured and comprehensive, setting up a VPC, subnets, security group, S3 bucket, EC2 instances, and an Application Load Balancer (ALB). It follows best practices for creating a basic AWS infrastructure with load balancing. Here are some points:

### VPC and Subnets:

Defines a VPC with two subnets across different availability zones.
Enables public IP mapping on launch for instances in both subnets.
Internet Gateway and Route Table:

#### Attaches an internet gateway to the VPC for external connectivity.
Creates a route table and associates it with the subnets, routing traffic through the internet gateway.
Security Group:

#### Defines a security group named "webSg" with rules for allowing HTTP (port 80) and SSH (port 22) traffic. Also, allows all outbound traffic.
Associates the security group with EC2 instances and the ALB.
S3 Bucket:

#### Creates an S3 bucket with the specified name.

### EC2 Instances:

Launches two EC2 instances in different subnets, each with a specified AMI, instance type, security group, subnet, and user data script.
Application Load Balancer (ALB):

#### Creates an ALB named "myalb" with the specified configuration.
Associates the ALB with the security group, subnets, target group, and listener.

### ALB Target Group:
Defines a target group for routing traffic to the EC2 instances.
Sets up health checks on the "/" path.

### ALB Listener:

Creates an HTTP listener on the ALB, forwarding traffic to the target group.
Output:

Outputs the DNS name of the ALB for easy access.
This script covers various AWS resources and demonstrates the creation of a basic web application infrastructure with high availability and load balancing.
