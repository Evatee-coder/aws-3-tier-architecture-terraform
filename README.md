# aws-3-tier-architecture-terraform
To Deploy A highly Secure 3-Tier Infrastructure on AWS with Terraform, GitHub Actions

Here we deploy two ec2 instances. One on a public subnet, and the other on a private subnet. EC2 instance in a public subnet has a public IP that connect to the Internet, given that we have configured an Internet gateway for VPC and created a route from the subnet to the Internet gateway.

The private EC2 instance did not have a public IP, keeping it isolated from direct access on the Internet. Even though we are not allowing it to be reachable from the Internet, we still need a way for EC2 instances to download patches. To do this, we will use the magic of the NAT gateway.

As a result, we create a NAT gateway in the public subnet and assign it a static IP(Elastic IP). Further, we configure the routes for the private subnet to talk to NAT, which enables the EC2 instance in the private subnet to download the software updates.

Tools utilized: AWS and Terraform

Terraform deployment: Manual

Terraform state: Local

AWS Services used: VPC( vpc, subnets, route tables, routes, nat gateway, internet gateway) EC2( ec2, security group, elastic ips)
