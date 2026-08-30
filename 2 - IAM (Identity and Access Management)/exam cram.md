<details class='bullet-section'>
  	<summary>
		<span class='bullet-title'>
			IAM
		</span>
	</summary>
	<span class='bullet-text'>
		- A global service used to control access to AWS resources
	</span>
	<span class='bullet-text'>
		- By default, new <strong>Users</strong> have no access to AWS resources and can only login and change their password
	</span>
</details>

<details class='bullet-section'>
  	<summary>
		<span class='bullet-title'>
			IAM can be used to Manage... (8)
		</span>
	</summary>
	<span class='bullet-text'>
		- Users
	</span>
	<span class='bullet-text'>
		- Groups
	</span>
	<span class='bullet-text'>
		- Access Policies
	</span>
	<span class='bullet-text'>
		- Roles
	</span>
	<span class='bullet-text'>
		- User credentials
	</span>
	<span class='bullet-text'>
		- User password policies
	</span>
	<span class='bullet-text'>
		- Multi-factor Authentication (MFA)
	</span>
	<span class='bullet-text'>
		- API Keys
	</span>
</details>

<details class='bullet-section'>
  	<summary>
		<span class='bullet-title'>
			IAM is <strong>Eventually Consistent</strong>
		</span>
	</summary>
	<span class='bullet-text'>
		- Updates to IAM may not take effect immediately, so wait a bit before reading from IAM api
	</span>
</details>

<details class='bullet-section'>
  	<summary>
		<span class='bullet-title'>
			IAM <strong>Authentication Methods</strong> (3)
		</span>
	</summary>
	<span class='bullet-text'>
		- Username and password (and MFA) for <strong>AWS Management Console</strong>
	</span>
	<span class='bullet-text'>
		- Access Key ID and Secret Access Key for <strong>Programmatic Access (CLI, API)</strong>
	</span>
	<span class='bullet-text'>
		- Server Certificates with <strong>SSL, TLS Certificates</strong>
	</span>
</details>

<details class='bullet-section'>
  	<summary>
		<span class='bullet-title'>
			IAM <strong>User</strong>
		</span>
	</summary>
	<span class='bullet-text'>
		- Entity that represents a person or service
	</span>
	<span class='bullet-text'>
		- <strong>Service accounts</strong> are IAM users used to represent applications
	</span>
	<span class='bullet-text'>
		- Root user email address is used to create the AWS Account and password
	</span>
	<span class='bullet-text'>
		- Max 5000 users per AWS Account
	</span>
</details>

<details class='bullet-section'>
  	<summary>
		<span class='bullet-title'>
			IAM <strong>Group</strong>
		</span>
	</summary>
	<span class='bullet-text'>
		- Collections of <strong>Users</strong> and have policies attached to them
	</span>
	<span class='bullet-text'>
		- Not an identity and can't be a <strong>Principal</strong> in an IAM Policy
	</span>
	<span class='bullet-text'>
		- Can't nest groups within groups
	</span>
</details>

<details class='bullet-section'>
  	<summary>
		<span class='bullet-title'>
			IAM <strong>Roles</strong>
		</span>
	</summary>
	<span class='bullet-text'>
		- <strong>Users</strong> or <strong>Services</strong> can assume a role to gain temporary security credentials given by <strong>AWS Security Token Service (STS)</strong>
	</span>
</details>

<details class='bullet-section'>
  	<summary>
		<span class='bullet-title'>
			IAM <strong>Policies</strong>
		</span>
	</summary>
	<span class='bullet-text'>
		- Document to define permissions and can be applied to <strong>Users</strong>, <strong>Groups</strong> and <strong>Roles</strong>
	</span>
	<span class='bullet-text'>
		- Written in JSON
	</span>
	<span class='bullet-text'>
		- Most restrictive policy applied
	</span>
</details>

<details class='bullet-section'>
  	<summary>
		<span class='bullet-title'>
			IAM <strong>Policy</strong> Types (5)
		</span>
	</summary>
	<span class='bullet-text'>
		- <strong>Identity Based Policies</strong> = Attached to <strong>Users</strong>, <strong>Groups</strong> and <strong>Roles</strong>
	</span>
	<span class='bullet-text'>
		- <strong>Resource Based Policies</strong> = Attached to a resource. Defines permissions for a principal accessing the resource
	</span>
	<span class='bullet-text'>
		- <strong>Permissions Boundaries</strong> = Specify the maximum permissions an <strong>Identity Based Policy</strong> can grant an entity
	</span>
	<span class='bullet-text'>
		- <strong>Organizations Service Control Policies (SCP)</strong> = Specify the maximum permissions for an organization or organizational unit (OU)
	</span>
	<span class='bullet-text'>
		- <strong>Session Policies</strong> = Used with <strong>AssumeRole</strong> API actions
	</span>
</details>

<details class='bullet-section'>
  	<summary>
		<span class='bullet-title'>
			IAM <strong>Principal</strong>
		</span>
	</summary>
	<span class='bullet-text'>
		- An entity such as a <strong>User</strong> or <strong>Service</strong> that can authenticate and make requests to access AWS Resources
	</span>
</details>

<details class='bullet-section'>
  	<summary>
		<span class='bullet-title'>
			IAM <strong>Best Practices</strong>
		</span>
	</summary>
	<span class='bullet-text'>
		- Grant least privilege
	</span>
	<span class='bullet-text'>
		- Use <strong>Groups</strong> to assign permissions to <strong>Users</strong>
	</span>
	<span class='bullet-text'>
		- User a strong password policy for <strong>Users</strong>
	</span>
	<span class='bullet-text'>
		- Enable MFA
	</span>
	<span class='bullet-text'>
		- Use roles to delegate permissions
	</span>
	<span class='bullet-text'>
		- Rotate credentials regularly
	</span>
</details>

<details class='bullet-section'>
  	<summary>
		<span class='bullet-title'>
			Delegate Permissions
		</span>
	</summary>
	<span class='bullet-text'>
		- Letting a <strong>User</strong> or <strong>Service</strong> act on behalf of another <strong>User</strong> without needing their account credentials
	</span>
</details>