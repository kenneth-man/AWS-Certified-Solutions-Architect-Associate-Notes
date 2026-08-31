## EC2 Overview
![](./imgs/1.png)

![](./imgs/2.png)

![](./imgs/3.png)

![](./imgs/4.png)

- ### EC2 Instances are always deployed within a VPC

- ### Elastic Network Interfaces (ENI) are attached to EC2 Instances
	- ### They represent a virutal network card and hold IP Addresses

![](./imgs/5.png)

## Public, Private and Elastic IP Addresses
![](./imgs/6.png)

## Network Interfaces (ENI, ENA, EFA)
- ### Elastic Network Interface
- ### Elastic Network Adapter
- ### Elastic Fabric Adapter
![](./imgs/7.png)

## Elastic Block Store (EBS)
- ### EBS Volumes are attached to EC2 Instances forpersistent storage
- ### Different EBS Volume types for different requirements
![](./imgs/8.png)

## Instance Store
- ### Attached to the host server and not attached to EC2 Instances like EBS Volumes are
- ### Better performance than EBS Volumes, but not persistent storage (Ephemeral)
	- ### If EC2 Instance stops, data is lost
![](./imgs/9.png)