- ### How does IAM work?
	- ### `Authentication`
		- ### Are you who you say you are?
	- ### `Authorization`
		- ### What actions do you have permission to perform?
![](../imgs/1.png)

(in more detail for a `User`)

![](../imgs/10.png)

- ### Users, User Groups, Roles, Policies
![](../imgs/2.png)

- ### For every resource in AWS, it has an `Amazon Resource Name (ARN)`
	- ### A unique identifier
	- ### E.g. Highlighted in red below is the user account number, the whole thing is the `ARN`
![](../imgs/3.png)

- ### Authentication methods
	- ### AWS Management Console
	- ### API/CLI
![](../imgs/4.png)

- ### Root user vs IAM user
	- ### IAM users have 0 permissions by default and can only update their password
![](../imgs/5.png)

- ### Multi Factor Authentication (MFA)
![](../imgs/6.png)

- ### Permissions Boundaries
	- ### Has precedence over other permission policies
![](../imgs/7.png)

![](../imgs/8.png)

![](../imgs/9.png)

- ### Types of policies
	- ### Indentity, Resource, Permission boundaries, SCP, Session
![](../imgs/11.png)

![](../imgs/12.png)
