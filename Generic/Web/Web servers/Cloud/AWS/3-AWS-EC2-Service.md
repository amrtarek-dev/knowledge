EC2 is Elastic Compute Cloud = Infrastructure as a Service
it is a sort of VPS (with selected OS) on the cloud (instance of cloud server.)
It is consists in the capability of:
- Renting virtual machines (EC2)
- Storing data on virtual drives (EBS)
- Distributing load across machines (ELB)
- Scaling the services using an auto-scaling group (ASG)


## EC2 Sizing & configuration options
- Operating System (OS): Linux, Windows or Mac OS
	- Amazon Linux
	- Ubuntu
	- Suse Linux ....
- Instance type
	- Compute power & cores (CPU)
	- Random-access memory (RAM)
- Storage space:
	- Network-attached (EBS & EFS)
	- Hardware (EC2 instance Store)
- Key pair (login): to use ssh (.pem for MAC, Linux, Win)
- Network card: speed of the card, Public IP address
- Firewall rules: security group
	- Enable Allow HTTP Traffic from the internet to access port 80
- Bootstrap script (configure at first launch): EC2 User Data.

## EC2 User Data
- it is possible to bootstrap our instance using an EC2 User data script.
- bootstrapping means launching commands when a machine starts
- That script is only run once at the instance first start
- EC2 user data is used to automate boot tasks such as:
	- Installing updates
	- Installing software
	- Downloading common files from the internet
	- Anything you can think of.
Ex:
```shell
#!/bin/bash
# Use this for your user data (script from top to bottom)
# Install httpd (Linux 2 version)
yum update -y
yum install -y httpd
systemctl start httpd
systemctl enable httpd
echo "<h1>Hello World from $(hostname -f)</h1>" > /var/www/html/index.html
```

> If you stoped an instance and restart it again the public ip will be changed.


## EC2 Instance Types
There are 8 types of instances:
- General Purpose
- Compute Optimized
- Memory Optimized
- Storage Optimized
- Accelerated Computing
- Instance Features
- Measuring Instance Performance

Instance naming convention:
ex: m5.2xlarge
m: instance class (type)
5: Generation (Improved over time means increment)
2xlarge: the size in the instance class (memory, cpu)

**General Purpose**: Great for diversity of workloads (web server, code repositories)
- balance between:
	- Compute
	- Memory
	- Networking
**Compute Optimized:** (C names) high performance processor
- Batch processing workloads
- Media transcoding
- High performance web servers
- High performance computing (HPC)
- Scientific modeling & machine learning
- Dedicated gaming servers.

**Memory Optimized:** for large data sets in memory (RAM) (R names)
- High performance, relational/non-relational databases.
- Distributed web scale cache stores
- In-memory databases optimized for BI(business intelligence)
- Applications performing real-time processing of big unstructured data.

**Storage Optimized:** for storage-intensive tasks that require high, sequential read and write access to large data sets on local storage. (I, D, H names)
- High frequency online transaction processing (OLTP) systems
- Relational & NoSQL databases
- Cache for in-memory databases (for example, Redis)
- Data warehousing applications
- Distributed file systems

https://www.ec2instances.info

## Security Groups
They are the fundamental of network security in AWS.
- as a firewall they control how traffic is allowed into or out of our EC2 Instances (Inbound/Outbound traffic)
- They only contain allow rules
	- the rules reference by IP or by security group
- They acting as a firewall on EC2 instances to regulate:
	- Access to ports
	- Authorised IP ranges -IPv4, IPv6
	- Control of inbound (to the instance) and outbound (from the instance) network.
type, protocol, port range, source, description
- They can be attached to multiple instance
- Locked down to a region / VPC combination
- It is good to maintain one separate security group for SSH.
- By Default all inbound is blocked, all outbound is authorised.

You can authorise and block the communication between security groups to avoid using the IP for the instances, so if the security group is authorised all instance that is already attached to this security group will be authorised.

Classic ports:
21 = FTP
22 = SSH, SFTP
80 = HTTP
443 = HTTPS
3389 = RDP (Remote Desktop protocol)

## SSH to EC2
3 ways to connect to EC2 by SSH
1. SSH command line (Terminal)
2. Putty
3. EC2 Instance Connect

Steps:
- Allow inbound ssh connection from the security group (0.0.0.0/port 22)
- Have the PEM file ready (download it from the EC2 instance) (chmod 400) or PPK for putty

``` sh
ssh ec2-user@3.250.26.200 -i amazon.pem
```
> EC2 Instance connect is a web ssh terminal from your browser.

You can control the AWS from the the EC2 and you have to attach a security role to it from IAM service.

## Purchasing Options
- On-Demain Instances - short workload, predictable pricing, pay by second
	- Time oriented
- Reseved (1 & 3 years) (Plan oriented (you know the plan))
	- Reserved instance (long term workloads)
	- Convertible Reserved Instances (long term workloads with flexible instances)
- Savings Plans (1 & 3 years) - Commitment on amount of usage (long workload) (Budget (money oriented))
- Spot Instances - cheap, can lose instance (short workloads) (Task Oriented)
- Dedicated Hosts - a physical server (control instance placement) (Hardware Oriented)
- Dedicated Instances - no other customers will share your hardware (Software Oriented)
- Capacity Reservations - reserve capacity for any duration (Load oriented)

## Public IP charges
- IPv4 Charges
Every public IPv4 is 0.005$ per hour ~ 3.6$ per month (EC2 is the only one which has a free tier (750H/ month)
- IPv6 Free
Not all Internet service providers are supporting IPv6 yet.

> You can check the billing in the `Billing and cost management` service to check them.

you can monitor IP address on your account by Amazon VPC IP Address Manager (IPAM)

## Shared Responsibility Model
who is responsible fro what (AWS<->User)

|                   AWS                    |                          User                          |
| :--------------------------------------: | :----------------------------------------------------: |
| Infrastructure (global network security) |                 security Groups rules                  |
|       Isolation on Physical hosts        |          Operating-System patches and updates          |
|       Isolation on physical hosts        |  Software and utilities installed on the EC2 instance  |
|        Replacing faulty hardware         | IAM Roles assigned to EC2 & IAM user access management |
|          Compliance validation           |             Data security on your instance             |


