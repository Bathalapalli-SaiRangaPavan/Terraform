# Setup Terraform on Windows System 


## Terraform Environment on Windows
As part of this, we should setup 
1. Terraform
2. AWS CLI

##### Install Terraform 
1. Download terraform the latest version from [here](https://developer.hashicorp.com/terraform/downloads)
###### Operating System 
- select (Windows) 
###### Binary download for Windows
- select (386 Version: (1.4.6))  
###### Note - Versions changes
###### Once it downloaded 
- select (terraform_1.4.6_windows_386)
- give right click on folder ((terraform_1.4.6_windows_386)
- select (extract all))
- Rename (terraform_1.4.6_windows_386) to (terraform_1.4.6)
- click (terraform_1.4.6)  
###### You can see terraform.exe
###### Keep terraform.exe in secure location
- copy the (terraform_1.4.6) folder 
- click (This pc) 
- click (Local Disc (c))
- select (Program Files) & Paste (terraform_1.4.6) folder 
- click (Continue) 
- open (terraform_1.4.6)
- select path(C:\Program Files\terraform_1.4.6)

#### Setup environment variable
- click (start button)
- search (Edit the system environment variables) & click on it.
###### Under the Advanced tab
- select (Environment variables) 
###### Under the system variables 
- select (path)
- click (edit) 
- click (New)
- Add terraform location in the path variable (C:\Program Files\terraform_1.4.6)
- click (ok - ok - ok)

####  Validate terraform version

- Go to command prompt 
```
terraform -version
```
###### I could able to see Terraform v1.4.6 on windows_386 which means terraform installation is successful

## AWS CLI installation

- Download AWSCLI latest version from [here](https://docs.aws.amazon.com/cli/latest/userguide/getting-started-install.html) and install it.

or you can run the below command in powershell or the command prompt
```
msiexec.exe /i https://awscli.amazonaws.com/AWSCLIV2.msi
```
- Accept the terms & conditions 
- click (Install) 

- Go to command prompt 
```
aws
```
###### I could able to see aws help , aws <command> help 


### Create IAM User 

- Go to (AWS Management Console) 
- Search (IAM) 
###### Access Management 
- Click (Users)
- Click (Add Users) 
- User name (terraform-user)
- Click (Next) 
###### Set permissions
- Select (Attach policies directly) 
- Select (Administrator Access) 
- Click (Next) 
- Click (Create user) 
#### You can see terraform-user 
- Select (terraform-user)
- Select (Security Credentials) 
###### Access keys 
- Click (Create Access Key)
- Select (Command Line Interface) (cli)
- Select (box) -  I understand the above recommendation and want to proceed to create an access key.
- Click (Next)
- Click (Create Access Key) 
- Download (.csv file) # Never ever share with any 
- Click (Done)


######  Go to command prompt
```
aws configure 
```
- give access key 
- give secret key 
- Select region (us-east-1) <it depends on which region you want to launch>
- Default output format - its optional 
- click (Enter) 

##### To test 
```
aws s3 ls
```

