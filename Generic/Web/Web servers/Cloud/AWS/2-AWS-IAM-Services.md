## IAM
Identity and Access Management, (Global service)
Use it to create the user's and assign them to groups. 
> Root account created by default, should n't be used of shared, you should use users and groups. 

- Users are people within your organization, and can be grouped
- Groups only contain users, not other groups
- users don't have to belong to a group, and user can belong to multiple groups. 
- Permissions: users or groups can be assigned JSON documents called policies.
	- These policies define the permissions of the users
	- In AWS you apply the least privilege principle: don't give more permissions than a user needs. 
### IAM Policies Structure
```json
{
	"Version": "2012-10-17",
	"Id": "S3-Account-Permissions", 
	"Statement": [
		"Sid": "1",
		"Effect": "Allow",
		"Principal": {
			"AWS": ["arn:aws:iam:12346787012:root"] 
		}, 
		"Action": [
			"s3:GetObject", 
			"s3:PutObject" 
		], 
		"Resource": ["arn:aws:s3:::mybucket/*"] 
	] 
} 
```
- Consists of
	- Version: policy language version, always include "2012-10-17"
	- Id: an identifier for the policy (Optional)
	- Satarement: one or more individual statements (required)
- Statements consists of
	- Sid: an identifier for the statement (Optional) 
	- Effect: whether the statement allows or denies access (Allow, Deny)
	- Principal: account /user/ role/ to which this policy applied to 
	- Action: list of actions this policy allows or denies
	- Resource: list of resources to which the actions applied to 
	- Condition: conditions for when this policy is in effect (optional)
### IAM Password Policy
You can setup a password policy
Or use **MFA** (Multi Factor Authentication)
- MFA = Password you know +  security device you own
	- MFA Devices:
		- Virtual MFA devices: Google Authenticator, Authy
		- Hardware: 
			- Universal 2nd Factor (U2F) security key (Yubikey)
			- Hardware key Fob MFA Device (Gemalto)
			- Hardware Key Fob MFA device for AWS GovCloud (SurePssID)

## IAM Roles for Services
When the AWS services need to perform actions on your behalf, to do so, we will assign permissions to AWS services with IAM Roles.
- EC2 instance Roles
- Lambda Function Roles
- Roles for CloudFormation
To make them:
IAM -> Access management -> Roles

## IAM Security Tools
- IAM Credentials Report (account-level)
	- a report that lists all your account's users and the status of their various credentials
- IAM Access Advisor (user-level)
	- Access advisor shows the service permissions granted to a user and when those service were last accessed.
	- You can use this information to revise your policies.


## Share Responsibility Model for IAM.
What AWS is responsible for and what you are responsible for:

AWS is responsible for what they do
- Infrastructure (global network security)
- Configuration and vulnerability analysis
- Compliance validation

You is responsible for how you use AWS
- Users, Groups, Roles, Policies management and monitoring
- Enable MFA on all accounts
- Rotate all your keys often
- Use IAM tools to apply appropriate permissions
- Analyze access patterns & review permissions.

IAM Section - Summary
> Users: mapped to a physical user, has a password for AWS Console
> Groups: contains users only
> Policies: JSON document that outlines permissions for users or groups
> Roles: for EC2 instances or AWS services
> Security: MFA + Password Policy
> AWS CLI: manager your AWS services using the command line
> AWS SDK: manage your AWS services using a programming language
> Access Keys: access AWS using the CLI or SDK
> Audit: IAM credential Reports & IAM Access advisor