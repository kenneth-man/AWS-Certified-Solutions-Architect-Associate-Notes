## EC2 Overview
![](./imgs/1.png)

![](./imgs/2.png)

![](./imgs/3.png)

![](./imgs/4.png)

- ### EC2 Instances are always deployed within a VPC

- ### Elastic Network Interfaces (ENI) are attached to EC2 Instances
	- ### They represent a virtual network card and hold IP Addresses

![](./imgs/5.png)

## Public, Private and Elastic IP Addresses
![](./imgs/6.png)

## Network Interfaces (ENI, ENA, EFA)
- ### Elastic Network Interface
- ### Elastic Network Adapter
- ### Elastic Fabric Adapter
![](./imgs/7.png)

![](./imgs/26.png)

![](./imgs/27.png)

![](./imgs/28.png)

## Elastic Block Store (EBS)
- ### EBS Volumes are attached to EC2 Instances forpersistent storage
- ### Different EBS Volume types for different requirements
![](./imgs/8.png)

## Instance Store
- ### Attached to the host server and not attached to EC2 Instances like EBS Volumes are
- ### Better performance than EBS Volumes, but not persistent storage (Ephemeral)
	- ### If EC2 Instance stops, data is lost
![](./imgs/9.png)

## Amazon Machine Image (AMI)
- ### When creating an EC2 Instance, the AMI determines the OS, Software and EBS volumes that are configured on the instance; like a blueprint
![](./imgs/10.png)

## Key Pairs (SSH)
- ### Use key pairs to login to the instance via ssh
- ### AWS will give you the private key, and the private key will be added to the instance somewhere on your machine
- ### `chmod 400 [PRIVATE_KEY_NAME.pem]` on the private key so only you can read it
- ### Connect to the instance using it's public DNS e.g. `ssh -l [PRIVATE_KEY_NAME.pem] [INSTANCE_PUBLIC_DNS.COM]`

## EC2 Metadata
- ### Retrieving data about the EC2 Instance
![](./imgs/11.png)
![](./imgs/12.png)

- ### Instance Metadata Service (IMDS1, IMDS2)
![](./imgs/13.png)

## User Data
- ### Script ran when EC2 Instance runs for the 1st time
- ### Uses a User Data script via Management Console or CLI
(Management Console)
![](./imgs/14.png)
(CLI)
![](./imgs/15.png)

![](./imgs/16.png)

- ### You can use Instance Metadata inside User Data Scripts so you don't need to hard code sensitive information...
	- ### E.G. This User Data Script installs a web server and uses Instance Metadata to retrieve information about the instance and then output the information on a webpage

```bash
#!/bin/bash

# Update system and install httpd (Apache)
yum update -y
yum install -y httpd

# Start httpd service and enable it to start on boot
systemctl start httpd
systemctl enable httpd

# Fetch metadata using IMDSv2
TOKEN=$(curl -X PUT "http://169.254.169.254/latest/api/token" -H "X-aws-ec2-metadata-token-ttl-seconds: 21600")
INSTANCE_ID=$(curl -H "X-aws-ec2-metadata-token: $TOKEN" http://169.254.169.254/latest/meta-data/instance-id)
AMI_ID=$(curl -H "X-aws-ec2-metadata-token: $TOKEN" http://169.254.169.254/latest/meta-data/ami-id)
INSTANCE_TYPE=$(curl -H "X-aws-ec2-metadata-token: $TOKEN" http://169.254.169.254/latest/meta-data/instance-type)

# Create a web page to display the metadata
cat <<EOF > /var/www/html/index.html
<html>
	<head>
		<title>EC2 Instance Metadata</title>
	</head>
	<body>
		<h1>EC2 Instance Metadata</h1>
		<p>Instance ID: $INSTANCE_ID</p>
		<p>AMI ID: $AMI_ID</p>
		<p>Instance Type: $INSTANCE_TYPE</p>
	</body>
</html>
EOF
```

## Access keys vs Roles with EC2 Instances
- ### Access keys for long term credentials, Roles for temporary credentials
- ### Access keys stored on the Instance in plain text which is a security weakness
	- ### Roles don't require keys being stored on Instance
- ### Roles credentials expire quickly, so needs to fetch new ones from STS frequently

### Using Access Keys with EC2 Instances
![](./imgs/17.png)

### Using Roles with EC2 Instances
![](./imgs/18.png)

## EC2 Placement Groups
- ### 3 Ways to deploy EC2 Instance across availability zones...
- ### `Cluster Placement Group`
	- ### Deploying instances all in the same AZ
![](./imgs/19.png)

![](./imgs/20.png)

- ### `Partition Placement Group`
![](./imgs/21.png)

![](./imgs/22.png)

- ### `Spread Placement Group`
![](./imgs/23.png)

![](./imgs/24.png)

- ### Example Placement Group Use Cases
![](./imgs/25.png)

## Public, Private and Elastic IP Addresses
![](./imgs/29.png)

- ### Elastic IP Addresses are static and don't change

- ### Public IP Addresses are dynamic and can change when instance is rebooted
![](./imgs/30.png)

## Network Address Translation (NAT) for Public IP Addresses
- ### Handles the association from private to public (going out) and public to private (coming in) ip addresses in data packets
- ### EC2 Instances can only see the private ip address via `ifconfig`, not the public ip address, so NAT is required to associate the private and public ips
![](./imgs/31.png)

## Public subnets, Private subnets and Bastion hosts
- ### Use a Bastion host to connect to an instance in a private subnet from your machine
	- ### A 'Bastion host' is just an instance in a public subnet that can communicate with an instance in a private subnet within the same VPC because they both have a private ip address within the same `CIDR` block range in their route tables
- ### Public and private subnets have route tables
	- ### Public subnets have a route to public internet via `Internet Gateway` `IGW`
	- ### Private subnets don't have a route to public internet unless you add a `NAT Gateway` which allows one-way communication from private subnet instance to public internet, called `Outbound` internet ccess
	- ### Each instance in a public subnet will have a public ip address
![](./imgs/32.png)

- ### E.g. Connectingt to private subnet instance with public subnet instance via SSH
	- ### The private subnet instance was created with a rsa key pair
	- ### that key pair private key was copied and pasted into a new file via `nano us-east-kp.pem`
![](./imgs/33.png)

## NAT Gateways
- ### Must be deployed in a public subnet
- ### Then a route e.g. `0.0.0.0` that allows the NAT Gateway you created, must be added to the private subnet route table so that the privat subnet instance can send traffic to public internet
- ### NAT Gateways receive traffic from private subnet instance and forwards it to public internet via elastic ip address
![](./imgs/34.png)

![](./imgs/35.png)

![](./imgs/36.png)

- ### The default is a public NAT Gateway, but you can also have a private NAT Gateway
![](./imgs/37.png)

- ### Route table = A set of routes that determine where network traffic from your subnets or gateways is directed

![](./imgs/38.png)

## Ec2 Instance Lifecycle
![](./imgs/39.png)

![](./imgs/40.png)

![](./imgs/41.png)

![](./imgs/42.png)

![](./imgs/43.png)

## AWS Nitro
![](./imgs/44.png)

![](./imgs/45.png)

- ### AWS Nitro Enclaves
	- ### For the most secure computing environment
![](./imgs/46.png)

## EC2 Instance Pricing
![](./imgs/47.png)

- ### Reserved Instances
![](./imgs/48.png)

![](./imgs/49.png)

- ### Spot Instances
![](./imgs/52.png)

- ### Dedicated Instances and Hosts
![](./imgs/53.png)

- ### Savings Plans
![](./imgs/51.png)

- ### Capacity Blocks
![](./imgs/50.png)

## EC2 Istance Pricing Use Cases
![](./imgs/54.png)

![](./imgs/55.png)