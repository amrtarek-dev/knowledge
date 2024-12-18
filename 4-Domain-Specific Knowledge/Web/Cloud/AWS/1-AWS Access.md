## Access AWS
There are 3 types of access to Amazon web services:
- AWS Management Console (Web access) (Password + MFA)
- AWS Command Line Interface (CLI) (Access Keys)
- AWS Software Developer Kit (SDK) (Access Keys)

## Create Access Keys
IAM -> Access management -> Users
Security credentials -> Access keys -> Create access key

## Use Access keys by CLI
```markdown
aws configure

aws iam list-users
```