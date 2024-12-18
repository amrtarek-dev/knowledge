EC2 is Elastic Compute Cloud = Infrastructure as a Service
it is a sort of VPS (with selected OS) on the cloud (instance of cloud server.)
It is consists in the capability of:
- Renting virtual machines (EC2)
- Storing data on virtual drives (EBS)
- Distributing load across machines (ELB)
- Scaling the services using an auto-scaling group (ASG)


## EC2 Sizing & configuration options
- Operating System (OS): Linux, Windows or Mac OS
- Compute power & cores (CPU)
- Random-access memory (RAM)
- Storage space:
	- Network-attached (EBS & EFS)
	- Hardware (EC2 instance Store)
- Network card: speed of the card, Public IP address
- FIrewall rules: security group
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