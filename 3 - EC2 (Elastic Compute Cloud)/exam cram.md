<details class='bullet-section'>
  	<summary>
		<span class='bullet-title'>
			EC2 Instance
		</span>
	</summary>
	<span class='bullet-text definition'>
		- A virtual server deployed using AWS Infrastructure
	</span>
	<span class='bullet-text'>
		- Securely connect to instances via <strong>Key Pairs</strong>
	</span>
	<span class='bullet-text'>
		- Instance Storage is either <strong>EBS</strong> (persistent) or <strong>Instance Store</strong> (non-persistent)
	</span>
	<span class='bullet-text'>
		- <strong>AMI</strong> provides the information to launch an instance
	</span>
	<span class='bullet-text'>
		- <strong>User Data</strong> is a script that runs when an instance launches for the first time
	</span>
</details>

<details class='bullet-section'>
  	<summary>
		<span class='bullet-title'>
			EC2 Instance <strong>Pricing</strong> (6)
		</span>
	</summary>
	<img src='imgs/63.png'/>
</details>

<details class='bullet-section'>
  	<summary>
		<span class='bullet-title'>
			<strong>Dedicated Instances</strong> vs <strong>Dedicated Hosts</strong>
		</span>
	</summary>
	<img src='imgs/64.png'/>
</details>

<details class='bullet-section'>
  	<summary>
		<span class='bullet-title'>
			Benefits of EC2 (6)
		</span>
	</summary>
	<span class='bullet-text'>
		- <strong>Elasticity</strong> = Scale up or down instances quickly depending on your requirements
	</span>
	<span class='bullet-text'>
		- <strong>Control</strong> = Control instances with full root/admin access
	</span>
	<span class='bullet-text'>
		- <strong>Flexibility</strong> = Choose instance types, OS, software installed
	</span>
	<span class='bullet-text'>
		- <strong>Reliability</strong> = High availability, deployable in multiple AZ and Regions
	</span>
	<span class='bullet-text'>
		- <strong>Security</strong> = Deployable in VPC
	</span>
	<span class='bullet-text'>
		- <strong>Cost Effective</strong> = Pay for what you use
	</span>
</details>

<details class='bullet-section'>
  	<summary>
		<span class='bullet-title'>
			<strong>Public</strong>, <strong>Private</strong> and <strong>Elastic</strong> IP Addresses
		</span>
	</summary>
	<img src='imgs/56.png'/>
</details>

<details class='bullet-section'>
  	<summary>
		<span class='bullet-title'>
			<strong>Placement Groups</strong> (3)
		</span>
	</summary>
	<img src='imgs/57.png'/>
</details>

<details class='bullet-section'>
  	<summary>
		<span class='bullet-title'>
			<strong>NAT Gateway</strong>
		</span>
	</summary>
	<span class='bullet-text definition'>
		- Receive traffic from private subnet instance and forwards it to public internet via elastic ip address
	</span>
	<span class='bullet-text'>
		- AWS Managed
	</span>
	<span class='bullet-text'>
		- Must be deployed in a public subnet
	</span>
</details>

<details class='bullet-section'>
  	<summary>
		<span class='bullet-title'>
			EC2 Instance Lifecycle (6)
		</span>
	</summary>
	<img src='imgs/58.png'/>
	<br/>
	<img src='imgs/59.png'/>
	<br/>
	<img src='imgs/60.png'/>
	<br/>
	<img src='imgs/61.png'/>
</details>

<details class='bullet-section'>
  	<summary>
		<span class='bullet-title'>
			<strong>Nitro System</strong>
		</span>
	</summary>
	<span class='bullet-text definition'>
		- Foundation of the latest generation of EC2 Instance. Better performance and security... close to bare metal performance
	</span>
	<span class='bullet-text'>
		- Breaks logical functions into specialized  hardware with a <strong>Nitro Hypervisor</strong>
	</span>
	<img src='imgs/62.png'/>
</details>

## Architecture Patterns