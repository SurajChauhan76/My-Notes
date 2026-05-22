# **How to create and manage users within AWS IAM Identity Center**



##### **AWS Single Sign-On (SSO) – AWS IAM Identity Center**.



AWS IAM Identity Center is a cloud service that allows you to grant your users access to AWS resources, such as Amazon EC2 instances, across multiple AWS accounts. By default, AWS IAM Identity Center now provides a directory that you can use to create users, organize them in groups, and set permissions across those groups. You can also grant the users that you create in AWS IAM Identity Center permissions to applications such Salesforce, Box, and Office 365. AWS IAM Identity Center and its directory are available at no additional cost to you.



A directory is a key building block that allows you to manage the users to whom you want to grant access to AWS resources and applications. AWS Identity and Access Management (IAM) provides a way to create users that can be used to access AWS resources within one AWS account. However, many businesses prefer an approach that enables users to sign in once with a single credential and access multiple AWS accounts and applications. You can now create your users centrally in AWS IAM Identity Center and manage user access to all your AWS accounts and applications. Your users sign in to a user portal with a single set of credentials configured in AWS IAM Identity Center, allowing them to access all of their assigned accounts and applications in a single place.



Note: If you manage your users in a Microsoft Active Directory (Microsoft AD) directory, AWS IAM Identity Center already provides you with an option to connect to a Microsoft AD directory. By connecting your Microsoft AD directory once with AWS IAM Identity Center, you can assign permissions for AWS accounts and applications directly to your users by easily looking up users and groups from your Microsoft AD directory. Your users can then use their existing Microsoft AD credentials to sign into the AWS IAM Identity Center user portal and access their assigned accounts and applications in a single place. Customers who manage their users in an existing Lightweight Directory Access Protocol (LDAP) directory or through a cloud identity provider such as Microsoft Azure AD can continue to use IAM federation to enable their users’ access to AWS resources.



##### **How to create users and groups in AWS IAM Identity Center**

You can create users in AWS IAM Identity Center by configuring their email address and name. When you create a user, AWS IAM Identity Center sends an email to the user by default so that they can set their own password. Your user will use their email address and a password they configure in AWS IAM Identity Center to sign into the user portal and access all of their assigned accounts and applications in a single place.



You can also add the users that you create in AWS IAM Identity Center to groups you create in AWS IAM Identity Center. In addition, you can create permissions sets that define permitted actions on an AWS resource, and assign them to your users and groups. For example, you can grant the DevOps group permissions to your production AWS accounts. When you add users to the DevOps group, they get access to your production AWS accounts automatically.



In this post, I will show you how to create users and groups in AWS IAM Identity Center, how to create permission sets, how to assign your groups and users to permission sets and AWS accounts, and how your users can sign into the AWS IAM Identity Center user portal to access AWS accounts. To learn more about how to grant users that you create in AWS IAM Identity Center permissions to business applications such as Office 365 and Salesforce, see Manage IAM Identity Center to Your Applications.



**Walk-through prerequisites**

For this walk-through, I assume the following:



You’ve enabled AWS IAM Identity Center for your AWS Organization. To learn more, see Enable AWS IAM Identity Center.

You’ve added the AWS accounts to which you want to grant AWS IAM Identity Center access to your organization. To learn more, see Managing the AWS Accounts in Your Organization.

You’ve signed into the AWS Management Console with your AWS Organizations master account credentials. To learn more about AWS Organizations and master accounts, see AWS Organizations FAQs.

You’ve required permissions to use the AWS IAM Identity Center Console. To learn more, see Permissions Required to Use the AWS IAM Identity Center Console.





##### **Overview**

To illustrate how to add users in AWS IAM Identity Center and how to grant permissions to multiple AWS accounts, imagine that you’re the IT manager for a company, Example.com, that wants to make it easy for its users to access resources in multiple AWS accounts. Example.com has five AWS accounts: a master account (called MasterAcct), two developer accounts (DevAccount1 and DevAccount2), and two production accounts (ProdAccount1 and ProdAccount2). Example.com uses AWS Organizations to manage these accounts and has already enabled AWS IAM Identity Center.



Example.com has two developers, Martha and Richard, who need full access to Amazon EC2 and Amazon S3 in the developer accounts (DevAccount1 and DevAccount2) and read-only access to EC2 and S3 resources in the production accounts (ProdAccount1 and ProdAccount2).



The following diagram illustrates how you can grant Martha and Richard permissions to the developer and production accounts in four steps:



1. **Add users and groups in AWS IAM Identity Center**: Add users Martha and Richard in AWS IAM Identity Center by configuring their names and email addresses. Add a group called Developers in AWS IAM Identity Center and add Martha and Richard to the Developers group.
2. **Create permission sets**: Create two permission sets. In the first permission set, include policies that give full access to Amazon EC2 and Amazon S3. In second permission set, include policies that give read-only access to Amazon EC2 and Amazon S3.
3. **Assign groups to accounts and permission sets**: Assign the Developers group to your developer accounts and assign the permission set that gives full access to Amazon EC2 and Amazon S3. Assign the Developers group to your production accounts, too, and assign the permission set that gives read-only access to Amazon EC2 and Amazon S3. Martha and Richard now have full access to Amazon EC2 and Amazon S3 in the developer accounts and read-only access in the production accounts.
4. **Users sign into the User Portal to access accounts**: Martha and Richard receive email from AWS to set their passwords with AWS IAM Identity Center. Martha and Richard can now sign into the AWS IAM Identity Center User Portal using their email addresses and the passwords they set with AWS IAM Identity Center, allowing them to access their assigned AWS accounts.





**Step 1: Add users and groups in AWS IAM Identity Center**



To add users in AWS IAM Identity Center, navigate to the AWS IAM Identity Center Console. Then, follow the steps below to add Martha as a user, to create a group called Developers, and to add Martha to the Developers group in AWS IAM Identity Center.



In the AWS IAM Identity Center Dashboard, choose Manage your directory to navigate to the Directory tab.



By default, AWS IAM Identity Center provides you a directory that you can use to manage users and groups in AWS IAM Identity Center. To add a user in AWS IAM Identity Center, choose Add user. If you previously connected a Microsoft AD directory with AWS IAM Identity Center, you can switch to using the directory that AWS IAM Identity Center now provides by default by following the steps in Change Directory.



On the Add User page, enter an email address, first name, and last name for the user, then create a display name. In this example, you’re adding “Martha Rivera” as a user. For the password, choose Send an email to the user with password instructions. This allows users to set their own passwords.

Optionally, you can also set a mobile phone number and add additional user attributes.



Next, you’re ready to add the user to groups. First, you need to create a group. Later, in Step 3, you can grant your group permissions to an AWS account so that any users added to the group will inherit the group’s permissions automatically. In this example, you will create a group called Developers and add Martha to the group. To do so, from the Add user to groups page, choose Create group.



In the Create group window, title your group by filling out the Group name field. For this example, enter Developers. Optionally, you can also enter a description of the group in the Description field. Choose Create to create the group.



On the Add users to group page, check the box next to the group you just created, and then choose Add user. Following this process will allow you to add Martha to the Developers group.



You’ve successfully created the user Martha and added her to the Developers group. You can repeat sub-steps 2, 3, and 6 above to create more users and add them to the group. This is the process you should follow to create the user Richard and add him to the Developers group.



Next, you’ll grant the Developers group permissions to AWS resources within multiple AWS accounts. To follow along, you’ll first need to create permission sets.





**Step 2: Create permission sets**



To grant user permissions to AWS resources, you must create permission sets. A permission set is a collection of administrator-defined policies that AWS IAM Identity Center uses to determine a user’s permissions for any given AWS account. Permission sets can contain either AWS managed policies or custom policies that are stored in AWS IAM Identity Center. Policies contain statements that represent individual access controls (allow or deny) for various tasks. This determines what tasks users can or cannot perform within the AWS account. To learn more about permission sets, see Permission Sets.



For this use case, you’ll create two permissions sets: 1) EC2AndS3FullAccess, which has AmazonEC2FullAccess and AmazonS3FullAccess managed policies attached and 2) EC2AndS3ReadAccess, which has AmazonEC2ReadOnlyAccess and AmazonS3ReadOnlyAccess managed policies attached. Later, in Step 3, you can assign groups to these permissions sets and AWS accounts, so that your users have access to these resources. To learn more about creating permission sets with different levels of access, see Create Permission Set.



Follow the steps below to create permission sets:



Navigate to the AWS IAM Identity Center Console and choose AWS accounts in the left-hand navigation menu.

Switch to the Permission sets tab on the AWS Accounts page, and then choose Create permissions set.



On the Create new permissions set page, choose Create a custom permission set. To learn more about choosing between an existing job function policy and a custom permission set, see Create Permission Set.



Enter EC2AndS3FullAccess in the Name field and choose Attach AWS managed policies. Then choose AmazonEC2FullAccess and AmazonS3FullAccess. Choose Create to create the permission set.



You’ve successfully created a permission set. You can use the steps above to create another permission set, called EC2AndS3ReadAccess, by attaching the AmazonEC2ReadOnlyAccess and AmazonS3ReadOnlyAccess managed policies. Now you’re ready to assign your groups to accounts and permission sets.





**Step 3: Assign groups to accounts and permission sets**



In this step, you’ll assign your Developers group full access to Amazon EC2 and Amazon S3 in the developer accounts and read-only access to these resources in the production accounts. To do so, you’ll assign the Developers group to the EC2AndS3FullAccess permission set and to the two developer accounts (DevAccount1 and DevAccount2). Similarly, you’ll assign the Developers group to the EC2AndS3ReadAccess permission set and to the production AWS accounts (ProdAccount1 and ProdAccount2).



Follow the steps below to assign the Developers group to the EC2AndS3FullAccess permission set and developer accounts (DevAccount1 and DevAccount2). To learn more about how to manage access to your AWS accounts, see Manage IAM Identity Center to Your AWS Accounts.



Navigate to the AWS IAM Identity Center Console and choose AWS Accounts in the left-hand navigation menu.

Switch to the AWS organization tab and choose the accounts to which you want to assign your group. For this example, select accounts DevAccount1 and DevAccount2 from the list of AWS accounts. Next, choose Assign users.



On the Select users and groups page, type the name of the group you want to add into the search box and choose Search. For this example, you will be looking for the group called Developers. Check the box next to the correct group and choose Next: Permission Sets.



On the Select permissions sets page, select the permission sets that you want to assign to your group. For this use case, you’ll select the EC2AndS3FullAccess permission set. Then choose Finish.



You’ve successfully granted users in the Developers group access to accounts DevAccount1 and DevAccount2, with full access to Amazon EC2 and Amazon S3.



You can follow the same steps above to grant users in the Developers group access to accounts ProdAccount1 and ProdAccount2 with the permissions in the EC2AndS3ReadAccess permission set. This will grant the users in the Developers group read-only access to Amazon EC2 and Amazon S3 in the production accounts.





**Step 4: Users sign into User Portal to access accounts**



Your users can now sign into the AWS IAM Identity Center User Portal to manage resources in their assigned AWS accounts. The user portal provides your users with IAM Identity Center access to all their assigned accounts and business applications. From the user portal, your users can sign into multiple AWS accounts by choosing the AWS account icon in the portal and selecting the account that they want to access.



You can follow the steps below to see how Martha signs into the user portal to access her assigned AWS accounts.



When you added Martha as a user in Step 1, you selected the option Send the user an email with password setup instructions. AWS IAM Identity Center sent instructions to set a password to Martha at the email that you configured when creating the user. This is the email that Martha received:



To set her password, Martha will select Accept invitation in the email that she received from AWS IAM Identity Center. Selecting Accept invitation will take Martha to a page where she can set her password. After Martha sets her password, she can navigate to the User Portal.



In the User Portal, Martha can select the AWS Account icon to view all the AWS accounts to which she has permissions.



Martha can now see the developer and production accounts that you granted her permissions to in previous steps. For each account, she can also see the list of roles that she can assume within the account. For example, for DevAccount1 and DevAccount2, Martha can assume the EC2AndS3FullAccess role that gives her full access to manage Amazon EC2 and Amazon S3. Similarly, for ProdAccount1 and ProdAccount2, Martha can assume the EC2AndS3ReadAccess role that gives her read-only access to Amazon EC2 and Amazon S3. Martha can select accounts and choose Management Console next to the role she wants to assume, letting her sign into the AWS Management Console to manage AWS resources. To switch to a different account, Martha can navigate to the User Portal and select a different account. From the User Portal, Martha can also get temporary security credentials for short-term access to resources in an AWS account using AWS Command Line Interface (CLI). To learn more, see How to Get Credentials of an IAM Role for Use with CLI Access to an AWS Account.



Martha bookmarks the user portal URL in her browser so that she can quickly access the user portal the next time she wants to access AWS accounts.







# **AWS Cloud Technical Essentials: Creating a VPC and Launching a Web Application in an Amazon EC2 Instance**





Objectives

After completing this lab, you will be able to:



* Understand Amazon VPC configuration
* Validate Subnet and Internet Gateway infrastructure
* Confirm a Route Table has a Public Route to the Internet
* Create Security Group rules
* Launch an Amazon Elastic Compute Cloud (Amazon EC2) instance
* Configure an EC2 instance to host a web application using a user data script





Scenario

In this scenario, you review the underlying network architecture, that has been created for you, and is needed to run a web application on an Amazon EC2 instance. You then launch the EC2 instance used to host your web application and conduct a simple test to verify you can access it in a web browser.



Start lab

1. To launch the lab, at the top of the page, choose Start Lab.



 Caution: You must wait for the provisioned AWS services to be ready before you can continue.



2\. To open the lab, choose Open Console .



You are automatically signed in to the AWS Management Console in a new web browser tab.





#### **Task 1: Understand a Virtual Private Cloud’s Configuration**

In this task, you review an Amazon VPC, that has been created for you, and all the infrastructure attached to and within it. You look at configuration of it’s internet gateway, route table, and subnets.



Amazon Virtual Private Cloud (Amazon VPC) enables you to launch AWS resources into a virtual network that you’ve defined. This virtual network closely resembles a traditional network that you’d operate in your own data center, with the benefits of using the scalable infrastructure of AWS.



An Internet gateway is a horizontally scaled, redundant, and highly available VPC component that allows communication between your VPC and the internet. It supports IPv4 and IPv6 traffic. It does not cause availability risks or bandwidth constraints on your network traffic.



After creating a VPC, you add a subnet or multiple subnets. Each subnet resides entirely within one Availability Zone and cannot span multiple Availability Zones. A subnet is a range of IP addresses in your VPC. You can launch AWS resources into a specified subnet. Use a public subnet for resources that must be connected to the internet, and a private subnet for resources that won’t be connected to the Internet. You will not use private subnets in this lab.



 Note: You must use the same Region throughout the lab. If you have changed the region, please revert to the previous region in which you launched this lab; you can do so by referring the Region parameter on the left side of these instructions.



3\. At the top of the AWS Management Console, in the search bar, search for and choose VPC.



4\. To view the VPC that has been created to host your web application, select the VPC ID link of the form vpc-\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\* next to Lab VPC.



5\. Observe key configurations on this page:



* The IPv4 CIDR block is 10.10.0.0/16. The subnet mask, /16 indicates that 2^16 possible addresses are available in this network, from 10.10.0.0 to 10.10.255.255.
* No IPv6 CIDR block
* DNS resolution enabled DNS hostnames enabled, allowing instances within the VPC to receive DNS hostnames that correspond to their public IP addresses.



6\. To view subnet details, choose lab-2-public-subnet-1 within the Resource map.



The available subnet occupies IPv4 CIDR range 10.10.1.0/24 within the VPC.



7\. To view the details of how traffic is routed from the subnet, choose lab-2-rtb-public within the Resource map.



The route table enables connections locally within the subnet, to an Internet Gateway, and to an S3 Endpoint. This enables internet connection and Gateway endpoint connection to AWS S3.



 You reviewed the web app VPC.



#### **Task 2: Create a VPC Security Group**

In this task, you review the VPC security group pre-created to launch your web application instance. A security group controls the traffic that is allowed to reach and leave the resources that it is associated with. For example, after you associate a security group with an EC2 instance, it controls the inbound and outbound traffic for the instance, similar to a firewall.



8\. In the left navigation pane, locate the Security section, and choose Security groups.



9\. To view the Security Group that has been created to control inbound and outbound access to your web server EC2 instance, select the Security group ID link of the form sg-\*\*\*\*\*\*\*\*\*\*\*\*\* next to WebAppSG.



See the security group, belongs to the VPC you just reviewed, has two inbound rules, and has 3 outbound rules.



10\. Examine the two Inbound rules currently displayed:



* TCP port 80 inbound access from all addresses is allowed to enable HTTP requests to your web application instance
* TCP port 443 inbound access from all addresses is allowed to enable HTTPS requests to your web application instance



11\. Choose the Outbound rules tab and examine the three Outbound rules displayed:

* All outbound traffic is allowed to the security group within your account for VPC Endpoints, enabling connections to other AWS services



* UDP port 53 outbound access from all addresses is allowed to enable DNS resolution



* Outbound traffic is allowed to prefix list for S3 addresses within your lab region, enabling S3 requests from your web application instance



These rules should be sufficient to handle user requests to your web application instance and outbound traffic to needed for it to work.



 You reviewed the security group pre-created to manage access to your web application instance.



#### **Task 3: Launch Your Amazon EC2 Instance**

In this task, you create an EC2 instance and provide a bootstrap script to install and configure the requirements for your web application. You also enable SSH (Secure Shell) access to the instance.



12\. At the top of the AWS Management Console, in the search bar, search for and choose EC2.



13\. In the left navigation pane, in the Instances section, choose Instances.



14\. Choose Launch instances.



15\. In the Name and tags section, locate the Name text box, and enter the value Web Application.



16\. In the Application and OS images section, locate the Quick start window, and select Amazon Linux 2023.



 Note: An Amazon Machine Image (AMI) is a supported and maintained image provided by AWS that provides the information required to launch an instance.



17\. Under the Quick start window, locate the  Amazon Machine Image (AMI) dropdown and select the AMI named Amazon Linux 2023 AMI.



18\. Under the Description section, locate the  Architecture dropdown and select 64-bit (x86).



19\. In the Instance type section, locate the  Instance type dropdown and select t3.micro.



20\. In the Key pair (login) section, locate the  key pair name dropdown and select Proceed without a key pair (Not recommended).



 Note: You do not need SSH access this EC2 instance during this lab.



21\. In the Network settings section, select Edit.



22\. Locate the  VPC dropdown and select Lab VPC.



23\. Locate the  Subnet dropdown and select lab-2-subnet-public-1.



24\. Locate the Auto-assign public IP dropdown and select Enable.



 Note: This setting assigns a public IP address to the instance so you can access the application in your browser.



25\. In the Firewall (security groups) section, choose  Select an existing security group.



26\. Locate the Common security groups dropdown and select the security group with name containing WebAppSG.



27\. You can leave the Configure storage section set to the default values.



28\. Scroll down to the  Advanced Details section and expand it.



29\. Locate the  IAM instance profile dropdown and select the profile with name containing LabInstanceProfile.



30\. Scroll down to the User data text box.



 Note: When you launch an instance in Amazon EC2, you have the option of passing user data to the instance that can be used to perform common automated configuration tasks and even run scripts after the instance starts.



Your instance uses an Amazon Linux 2023 operating system; therefore, you need to provide a shell script that will run when the instance starts. This script installs the required application dependencies and launches the application. Without this user data script, you would need to log in to the EC2 Instance and execute all of the commands yourself.



31\. Copy edit: In the User data text box, add the following code:



Replace both S3\_BUCKET\_NAME placeholders with the S3BucketName value listed to the left of these instructions.





\#!/bin/bash -xe



\# Installs Node.js

dnf install nodejs20 nodejs20-npm -y



\# Downloads an NPM cache from S3 to aid package installation

aws s3 cp s3://S3\_BUCKET\_NAME/npm-cache.tar.gz \\

/var/cache/npm-cache.tar.gz



\# Extracts the cache to a directory

mkdir -p /root/.npm

tar xzf /var/cache/npm-cache.tar.gz -C /root/.npm/



\# Downloads the web app code as a zip file

mkdir -p /var/app/

aws s3 cp s3://S3\_BUCKET\_NAME/app.zip \\

/var/app/app.zip



\# Extracts the web app zip to a directory

unzip /var/app/app.zip -d /var/app/



\# Runs an offline npm install for needed packages

cd /var/app

npm install --offline



\# Starts the Node.js web app

npm start



###### **This script performs the following tasks:**

* Installs Node.js
* Creates symbolic links for Node.js and Node Package Manager (NPM)
* Downloads an NPM cache from S3 to aid package installation
* Extracts the cache to a directory
* Downloads the web app code as a zip file
* Extracts the web app zip to a directory
* Runs an offline npm install for needed packages
* Starts the Node.js web app



32\. In Summary section, for Number of instances text box, enter the value 1, if not already done.



33\. Select Launch instance\_.



34\. Wait for the instance to launch. You should receive an message indicating the launch completed. See the message below:



 Successfully initiated launch of instance (instance-id)



35\. Choose View all instances.



 Note: You may need to  refresh the Instances page for the instance to appear in the list of instances.



The instance should appear in a  Pending or  Initializing state, which means it is launching. When the Instance state changes to  Running, the instance is booting.



36\. To see the instance details, choose your  Web Application instance.



 To show more or less information in the Details tab, drag the window divider. You can review the instance details including the instance type, security settings, network settings, etc.



37\. In the Instance window, at the top of the page, locate the Instance state and Status check columns. Wait for the values to indicate the following:



* Instance state:  Running



* Status check:  3/3 checks passed



 Note: You might need to choose  refresh at the top of the page to review the status changes.



38\. In the Details tab, locate the Public IPv4 address section, and copy the IP address.



 Note: If you refreshed the Instances window, you may need to choose your  Web Application instance again.



39\. Open a new browser tab and paste the IP address you copied in the previous step. You should see the following application screen.



Application Home Page



 Note: If you use the open address  link, your browser might try to browse to the application using https://, which won’t work. The application can only be accessed using http:// on port 80.



The following diagram represents the completed lab environment:

[https://us-west-2-tcprod.s3.us-west-2.amazonaws.com/courses/SPL-CX-100-CETEVP/v1.0.2.prod-f573b9d0/instructions/en\_us/images/lab-2-complete-overview.png](https://us-west-2-tcprod.s3.us-west-2.amazonaws.com/courses/SPL-CX-100-CETEVP/v1.0.2.prod-f573b9d0/instructions/en_us/images/lab-2-complete-overview.png)



lab-2-complete-overview



Once you access the web application successfully, you can close the browser tab.



 Congratulations! You successfully created an EC2 Instance and deployed a web application using a user data script.



Lab Complete

 Congratulations! You successfully did the following:



* Understood Amazon VPC configuration
* Validated Subnet and Internet Gateway infrastructure
* Confirmed a Route Table has a Public Route to the Internet
* Created Security Group rules
* Launched an Amazon Elastic Compute Cloud (Amazon EC2) instance
* Configured an EC2 instance to host a web application using a user data script







# **3. AWS Cloud Technical Essentials: Configure a Web Application to use an Amazon S3 Bucket and Amazon DynamoDB Table**



Lab overview

This lab guides you through configuring a web-based employee directory application by integrating Amazon S3 for photo storage and DynamoDB for employee data. You’ll create and configure an S3 bucket to store employee images, set up appropriate bucket policies for access, and upload employee photos. Then you’ll create a DynamoDB table to store employee information, and learn how to manage employee records through both the web interface and AWS Console. By the end of the lab, you’ll have a fully functional employee directory that combines cloud storage and database services to manage employee information and images.



Objectives

After completing this lab, you will be able to:



* Create an Amazon Simple Storage Service (Amazon S3) Bucket
* Create an S3 bucket policy
* Modify an Application to Use an S3 Bucket
* Upload an Object to an S3 Bucket
* Create an Amazon DynamoDB table
* Test an Application Using an Application Web Interface
* Manage Existing DynamoDB Items Using the AWS Management Console
* Create Items in a DynamoDB Table Using the AWS Management Console



Task 1: Create an Amazon Simple Storage Service (Amazon S3) Bucket

To support the lab, we created some required resources for you. These resources include a VPC with two public subnets in two different Availability Zones, an Internet Gateway, a Route Table with a route to the Internet, and an EC2 instance hosting your employee directory application. See below for a resource overview:



Task 1 - Overview



Currently, the application runs in Public Subnet 1. The application does not have access to Amazon S3, but you provide that access later in this lab.



Applications must sign their API requests with AWS credentials to access other AWS resources. AWS Identity and Access Management (IAM) roles enable applications to make secure API requests to an instance, without requiring you to manage the security credentials that the applications use.



Instead of creating and distributing AWS credentials for the application, you can delegate permission to make API requests using IAM roles. In this lab, the application uses the EmployeeDirectoryAppRole IAM role. The role hasn’t been configured to allow Amazon S3 access. The application displays a warning message until Amazon S3 access is granted.



To access the employee directory application, do the following:



On the lab instructions page, in the left pane, copy PublicWebApplicationURL.

In a new browser tab, paste the URL you copied in the previous step. You should see the application, as shown.

Note: You might need to wait a few minutes before the web application becomes available.



Task 1 - Web App



A warning message states the following:



S3: Employee Images bucket not found.

DynamoDB: ‘Employees’ table not found.

First, you must address the S3 configuration. To fix this, you create an S3 bucket and upload images to it. You also configure a policy to allow the application IAM role to access the S3 bucket, allowing the application to display the images.



In this task, you create an S3 bucket. Every object in Amazon S3 is stored in an S3 bucket. When you create your bucket, make sure that you create the bucket in your specific lab Region. You can find the lab region on the instructions page, in the left pane.



At the top of the AWS Management Console, in the search bar, search for and choose S3.



Choose Create bucket, and then configure the following:



Bucket name: employee-photo-bucket-<INITIALS>-<NUMBER>

Replace INITIALS with your initials

Replace NUMBER with a random, four-digit number

For Region, make sure it matches the AWS Region value in the left pane of your instructions.

Example bucket name: employee-photo-bucket-jwf-1234



Note: Each S3 bucket name must be globally unique.



When you select a particular Region, you can optimize latency, minimize costs, and address regulatory requirements, as needed. Objects stored in a Region never leave that Region, unless you explicitly transfer them to another Region.



The Copy settings from an existing bucket option creates a bucket that uses the same settings as another bucket. For this lab, you do not use this option.



In the Block Public Access settings for this bucket section, examine the Block all public access section.

No changes are needed. The default setting is checked,  Block all public access. This prevents all public access to data stored in the bucket.



Navigate to the bottom of the Create bucket page and choose Create bucket.

You should see a message similar to the following:



 Successfully created bucket “employee-photo-bucket-XXX-XXXX”



 Congratulations! You successfully created an Amazon S3 Bucket for your employee directory web application images.



In the next task, you create an Amazon S3 bucket policy.



Task 2: Create an S3 Bucket Policy

A bucket policy contains a set of permissions associated with an S3 bucket. The policy can control access to a entire bucket or to specific directories in a bucket.



Choose the employee-photo-bucket-<INITIALS>-<NUMBER> link for your bucket.



Choose the Permissions tab.



Navigate to the Bucket policy section, and then choose Edit.



The S3 Management Console presents a sample Bucket policy editor. Bucket policies can be created manually or they can be created with the assistance of the AWS Policy Generator. In this lab, you create the policy manually.



Copy and paste the following policy into the Bucket policy editor:



{

  "Version": "2012-10-17",

  "Statement": \[

    {

      "Sid": "AllowS3ReadAccess",

      "Effect": "Allow",

      "Principal": {

        "AWS": "arn:aws:iam::INSERT-ACCOUNT-NUMBER:role/EmployeeDirectoryAppRole"

      },

      "Action": "s3:\*",

      "Resource": \[

        "arn:aws:s3:::INSERT-BUCKET-NAME",

        "arn:aws:s3:::INSERT-BUCKET-NAME/\*"

      ]

    }

  ]

}

Replace the two INSERT-BUCKET-NAME placeholders with your bucket name, employee-photo-bucket-<INITIALS>-<NUMBER>.



In the left pane of the instructions, select and copy the value next to AWSAccountID.



Replace the INSERT-ACCOUNT-NUMBER placeholder with the AWSAccountID value copied in the previous step.



Your bucket policy should look similar to the following example:





{

  "Version": "2012-10-17",

  "Statement": \[

    {

      "Sid": "AllowS3ReadAccess",

      "Effect": "Allow",

      "Principal": {

        "AWS": "arn:aws:iam::000000000000:role/EmployeeDirectoryAppRole"

      },

      "Action": "s3:\*",

      "Resource": \[

        "arn:aws:s3:::employee-photo-bucket-jwf-1234",

        "arn:aws:s3:::employee-photo-bucket-jwf-1234/\*"

      ]

    }

  ]

}

Scroll to the bottom of the ""Edit bucket policy\*\* page and choose Save changes.

Note: If you receive an error regarding the first byte, ensure there is no empty space before the first { character on line 1. If there is, delete the empty space and try again.



If you policy is correct, you should receive a message similar to the following:



 Successfully edited bucket policy



You applied a bucket policy to your S3 bucket. The bucket policy uses the EmployeeDirectoryAppRole IAM role to allow read access from your application to the S3 bucket. With this policy, all objects in your bucket are accessible to your application.



 Congratulations! You successfully created a bucket policy for your Amazon S3 Bucket.



In the next task, you modify the employee directory applications to use the Amazon S3 bucket.



Task 3: Modify the Application to Use the S3 Bucket

In this task, you configure your application to use the bucket as a source for employee images.



Return to the browser tab with the Employee Directory application.



In the Administration section, choose the Configuration.



The Configuration Settings for the Employee Directory should look like this:



Task 2 - Application Configuration



The S3 Access Enabled value  and blank S3 Bucket value indicate an S3 bucket has not been associated with the Employee Directory application.



Use the Configuration Settings section to associate your S3 bucket (employee-photo-bucket-<INITIALS>-<NUMBER>) with the application.



Choose Change in the S3 Bucket field.



Enter your bucket name (i.e. employee-photo-bucket-<INITIALS>-<NUMBER>) in the S3 Bucket field.



Choose Save.



Your Configuration Settings page should now look like the following:



Task 1



The S3 Access Enabled value  and S3 Bucket value of employee-photo-bucket-al-1234 indicate an S3 bucket has been successfully associated with the employee directory web application.



 Congratulations! You successfully configured your employee directory web application to use an Amazon S3 Bucket to host your employee images.



In the next task, you upload the employee images to the Amazon S3 bucket.



Task 4: Upload an Object to an S3 Bucket

You created a bucket and granted permission to it from your EC2 Instance. Next, upload objects (images) to the Amazon S3 Bucket. An object can be any kind of file – text, photo, video, .zip, etc. When you add an object to an S3 bucket, you can include custom metadata with the object and set permissions, providing granular access control.



In this task, you upload objects to your S3 bucket.



In the left pane in the lab instructions, copy the PhotosZipURL URL. Open it in a new browser tab and paste the URL in the new browser tab. This downloads a .zip file that contains 10 sample images.



Extract the compressed files to your computer, in a location of your choice.



Navigate to the extracted files to access the sample images. You should see 10 .png files in the directory.



Next, upload the images to your bucket.



Return to the browser tab displaying your S3 bucket and select the Objects tab.



Choose Upload.



In the Files and Folders section, choose Add files.



Browse to and select the .png files on your computer.



Choose Open.



You should see your selected files in the Files and folders section.



Navigate to the bottom of the Upload page and choose Upload.

You can see the upload progress. When the files are uploaded, you will see a message similar to the following:



 Upload succeeded



Choose Close to return to the S3 dashboard.



Return to the browser tab with the Employee Directory application.



In the Employees section, choose Images.



The application displays the employee images you uploaded. It should look similar to the following image.



Task 4 - Employee Images



 Congratulations! You successfully uploaded objects to your Amazon S3 Bucket and verified the employee direction application backend configuration.



In the next task, you create an Amazon DynamoDB table.



Task 5: Create an Amazon DynamoDB Table

Now that the S3 configuration is complete, the employee directory application is almost ready. But first, you must configure the application to present employee data using Amazon DynamoDB. In this task, you create a DynamoDB table to store all of your employee data for the employee directory application.



At the top of the AWS Management Console, in the search bar, search for and choose DynamoDB.



Choose Create table, and then configure the following:



Note: Depending on the size of the web browser screen, the Create table option may not be visible. If you do not see this option, select Tables in the right pane and select Create table before proceeding.



Important! Do not modify any other fields.



Table name: Employees, use the the same capitalization shown.

Partition key: id, select String .

Navigate to the bottom of the Create table page and choose Create table.

The table creation may take up to a minute. Wait until the table is successfully created before continuing. The status should show as follows:



 Active



 Congratulations! You successfully created a DynamoDB table.



In the next task, you test the employee directory application using the web application user interface.



Task 6: Test the Application Using the Application Web Interface

In your browser, go to the browser tab with the web application, and refresh the page.

Note: If you closed the browser tab, open a new one. From the left pane, copy PublicWebApplicationURL, and paste the URL into the address bar.



On the left side of the web application page, in the Administration section, choose Configuration.

Note: An IAM policy was created for you and attached to the EC2 instance that hosts the employee directory application. The role allows access to the DynamoDB table and allows you to see the DynamoDB table items from the application interface in your web browser.



Notice that the DynamoDB error is gone. This indicates that your employee directory application can now access your DynamoDB table.



Locate the Employees section in the left pane, and choose Management.



Using the Actions  dropdown, choose New Employee.



In the Employee details form, fill in the Name, Location, and Email fields.



In the Selection existing photo section, select the Photo dropdown, and choose an image.



Navigate to the bottom of the Employee details windows and select Add.



The application creates a new record. This record should appear similar to the following:



Lab 3 - Task 5 - Add Employee



For extra hands-on practice, create a few more employees, edit some items, and delete some items.

 Congratulations! You successfully tested the employee directory application by adding, editing, and removing items from DynamoDB using the web interface.



In the next task, you manage existing DynamoDB items using the AWS Management Console.



Task 7: Manage Existing DynamoDB Items Using the AWS Management Console

In the next task, you validate that the your new employee data exists in your DynamoDB table and use the AWS Management Console to edit the data.



Return to the browser table with your DynamoDB table.



In the Tables section, choose the Employees link.



Review the Employees table details, including the Overview and Indexes tabs.



Choose Explore table items.



In the Items returned section, you can see the items in the database created from the application.



Choose an item to review by selecting the id column link.

The Edit item page returns the item attributes. Alternatively, to access the JSON representation, choose JSON at the top of the page.



You can use either view to edit the item attribute values.



Important: You will receive an error if you try to modify the primary key field, id. That field cannot be modified. To modify it, you must delete the item and add it again.



Update the location and email values in JSON, and then choose Save changes. You can also update the photo attribute but the name must be identical to the object in your S3 bucket.

Tip: As you make changes, go to your browser tab with the employee directory application and confirm that the changes return as they change in DynamoDB by refreshing the page.



 Congratulations! You successfully managed existing items in your DynamoDB table and tested the changes in the employee directory application.



In the next task, you create items in a DynamoDB table using the AWS Management Console.



Task 8: Create Items in a DynamoDB Table Using the AWS Management Console

In this task, you use the AWS Management Console to create DynamoDB items in your table.



Go to your browser tab with the DynamoDB table.



In the Items returned section, choose Create item.



For the next steps, use the Form view.



In the Attributes section, provide a value for id. The id must be unique across all items in the table.



Choose Add new attribute , and select String.



Replace NewValue with name, and provide a value for name. For example, John.



Choose Add new attribute , and select String.



Replace NewValue with location, and provide a value for location. For example, New York.



Choose Add new attribute , and select String.



Replace NewValue with email, and provide a value for email. For example, john.doe@example.org.



Choose Add new attribute , and select String.



Replace NewValue with photo, and leave the field empty.



Choose Create item.



The DynamoDB console returns the following message:



 The item has been saved successfully.



Go to your browser tab with the employee directory application and confirm that the new item displays in the Employees list by refreshing the page.



For more hands-on practice, create a few more employees, edit some items, and delete some items. Make sure that you provide the four required attributes: name, location, email, and (empty) photo.



Try to add a photo for each employee.



 Congratulations! You successfully added new items to your DYnamoDB table using the AWS Management Console and testing the changes to the employee directory application.



Conclusion

Congratulations! You can now:



Create an Amazon Simple Storage Service (Amazon S3) Bucket

Create an S3 bucket policy

Modify an Application to Use an S3 Bucket

Upload an Object to an S3 Bucket

Create an Amazon DynamoDB table

Test an Application Using an Application Web Interface

Manage Existing DynamoDB Items Using the AWS Management Console

Create Items in a DynamoDB Table Using the AWS Management Console





# **AWS Cloud Technical Essentials: Configure High Availability for Your Application**



###### **Objectives**

After completing this lab, you will be able to do the following:



* Review an Amazon Elastic Compute Cloud (Amazon EC2) Instance and web application and validate the configuration.
* Create an Application Load Balancer and launch template.
* Set up an Amazon EC2 Auto Scaling group.
* Launch a template.
* Stress test a web application to validate scaling.



###### **Task 1: Review an EC2 Instance and web application to validate the configuration**

Infrastructure

To support the lab, we provisioned some resources for you. The resources include a VPC, an Internet Gateway, two public subnets in different Availability Zones, a route table, a Security Group with restricted egress access, an Amazon Simple Storage Service (Amazon S3) bucket with a bucket policy, a DynamoDB table, and EC2 instance, and an IAM role with the permissions required for your instance to access Amazon S3 and Amazon DynamoDB.



Task 1 - Overview



We deployed the Employee Directory application on an EC2 instance in a single public subnet. In this task, you review the EC2 instance and Employee Directory application.



At the top of the AWS Management Console, in the search bar, search for and choose EC2.



In the left navigation pane, locate the Instances section, and choose Instances.



Select the  Web Application instance, which should appear in a  Running state.



 Note: To show more or less information in the Details tab, drag the window divider.



Here, you can review the instance’s details, including the instance type, security settings, network settings, and other information.



Next, access the web application in your browser.



On the Lab instructions page, in the left pane, copy the PublicWebApplicationURL link.



In a new browser tab, paste the URL you copied in the previous step. You should see the application, as shown.



 Note: You might need to wait up to a minute before the web application becomes available.



Application Preview



In the Employee Directory application, locate the Administration section in the left pane, and choose Configuration.



On this page, you can find information about where the application is running. You can identify the Availability Zone in the Configuration Settings table. You will reference this value to test your load balancer later in the lab, as provided below:



Application Configuration Preview



 Note: Your lab region may differ from the region in the reference above.



 Congratulations! You successfully reviewed the EC2 Instance and Employee Directory application.



###### **Task 2: Create an Application Load Balancer**

In this task, you create an Application Load Balancer, a required target group, and a Launch Template.



Go to the browser tab with the EC2 dashboard.



In the left navigation pane, locate the Load Balancing section, and choose Load Balancers.



Choose Create Load Balancer .



In the Load Balancer types section, below Application Load Balancer, choose the option Create .



On the Create Application Load Balancer page, configure the following:



 Note: Do not modify any other fields.



In the Basic configuration section:



Load balancer name: Web-Application-ALB

In the Network mapping section:



VPC, choose the Lab VPC

Mappings, select both Availability Zones (AZ)

Example: If you are in US West (Oregon), you would choose both  us-west-2a and  us-west-2b.



In the Security Groups section, remove the default security group by selecting the X next to the security group ID.



From the Security groups drop down menu, choose the security group with LoadBalancerSG in the name.



In the Listeners and routing section, under the Default action field, select the Create target group link.



 Note: This will open a new browser tab with the Create target group configuration options.



On the new Target groups browser tab, in the Basic configuration section, configure the following:



Choose Instances.

In the Target group name field, enter lab-app-target-group.

In Health checks, expand Advanced health check settings.



Change the Healthy threshold to 2.



Change the Unhealthy threshold to 5.



Change the Timeout to 20.



Change the Interval to 30.



Navigate to the bottom of the page and choose Next.



In the Available instances section, choose the check box next to the  Web Application instance.



Choose Include as pending below.



Choose Create target group.



You should see a message stating, Successfully created the target group: lab-app-target-group.



Once you see the target group has been created successfully you can close the Create target group browser tab.



Switch back to the load balancer tab, in the Listeners and routing section, and choose the  Refresh button beside the Forward to dropdown under Default action.



In the Forward to field, select lab-app-target-group target group.



Navigate to the bottom of the page and choose Create load balancer.



You should receive a message stating, Successfully created load balancer: Web-Application-ALB.



 Note: Wait for the State to change from provisioning to active. This process can take a few minutes. You might need to choose the  Refresh button at the top-right to see the status changes.



In the Details section, copy the value for the DNS name.



Paste the DNS Name into a new browser tab.



You should see the Employee Directory application.



 Note: It may take up to two minutes for target to be healthy and for the URL to return the Employee Directory application. Refresh the browser tab occasionally until you see the application. Additionally, some browser applications can redirect the website to https:// (443), please ensure we are using http:// (port 80) for this lab.



 Congratulations! You successfully created an Application Load Balancer, target group, security group and confirmed the Employee Directory application has been set up correctly.



###### **Task 3: Create a Launch Template**

Now that you can access your application from a single DNS name, you can scale horizontally. To do so, you need an Auto Scaling group. But before you can create an Auto Scaling group, you need a launch template. In this task, you create a launch template to use later when you create an Auto Scaling group.



At the top of the AWS Management Console, in the search bar, search for and choose EC2.



In the left navigation pane, locate the Instances section, and choose Launch Templates.



Choose Create launch template.



In the Launch template name and description section, configure the following:



Launch template name: lab-app-launch-template

Template version description: A web server for the employee directory app

Auto Scaling guidance: Select the check box  for Provide guidance to help me set up a template that I can use with EC2 Auto Scaling

In the Application and OS Images (Amazon machine Image) - required section, choose the Browse more AMIs link.



Select the Amazon Linux 2023 AMI with the highest version. Select the  64-bit(x86) option and choose Select.



In the Instance type section, select the Instance type dropdown, and choose t3.micro.



In the Key pair (login) section, confirm that the Key pair name dropdown is set to Don’t include in launch template.



 Note: Amazon EC2 uses public key cryptography to encrypt and decrypt login information. To log in to your instance, you must create a key pair, specify the name of the key pair when you launch the instance, and provide the private key when you connect to the instance.



In this lab, you do not connect to the instance.



In the Network settings section, choose the Security group dropdown, and choose the option with LoadBalancerSG in the name.



Expand the Advanced details section at the bottom of the page. In the IAM instance profile, choose EmployeeDirectoryAppRole.



For Metadata version, choose V1 and V2 (Token optional).



Navigate to the bottom of the page and locate the User data section.



When you launch an instance, you can pass user data to the instance. The data can be used to run configuration tasks and scripts.



Your instance uses an Amazon Linux operating system (OS); therefore, you need to provide a shell script that will run when the instance starts. This script installs the application’s required dependencies. It also launches the application so you can access it in your browser.



Copy the user data script below:





\#!/bin/bash -ex



\# Update these three variables with values to the left of these instructions

IMAGES\_BUCKET=UPDATE\_WITH\_IMAGES\_BUCKET\_NAME

INSTALLATION\_BUCKET=UPDATE\_WITH\_INSTALLATION\_BUCKET\_NAME

YOUR\_DEFAULT\_AWS\_REGION=UPDATE\_WITH\_ACTUAL\_REGION



\# Update yum

yum -y update



\# installs nvm (Node Version Manager)

\#curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.40.0/install.sh | bash

\# Download and install nvm

aws s3 cp s3://$INSTALLATION\_BUCKET/install.sh - | bash



export NVM\_DIR="$HOME/.nvm"

\[ -s "$NVM\_DIR/nvm.sh" ] \&\& \\. "$NVM\_DIR/nvm.sh"  # This loads nvm

\[ -s "$NVM\_DIR/bash\_completion" ] \&\& \\. "$NVM\_DIR/bash\_completion"  # This loads nvm bash\_completion



\# download and install Node.js (you may need to restart the terminal)

nvm install 20



\#Install stress tool (for load balancing testing)

yum -y install stress



\# Create a dedicated directory for the application

mkdir -p /var/app



\# Get the app from Amazon S3

\#wget https://aws-tc-largeobjects.s3-us-west-2.amazonaws.com/ILT-TF-100-TECESS-5/app/app.zip

\# Download app from S3

aws s3 cp s3://$INSTALLATION\_BUCKET/app.zip .



\# Extract it into a desired folder

unzip app.zip -d /var/app/

cd /var/app/



\# Configure S3 bucket details

export PHOTOS\_BUCKET=$IMAGES\_BUCKET



\# Configure default AWS Region

export DEFAULT\_AWS\_REGION=$YOUR\_DEFAULT\_AWS\_REGION



\# Enable admin tools for stress testing

export SHOW\_ADMIN\_TOOLS=1



\# Install dependencies

npm install



\# Start your app

npm start

This script performs the following tasks:



Installs system updates

Installs a source repository so the Node.js installer can be downloaded

Installs Node.js

Installs the EPEL repository that provides additional options for package installation

Installs the stress package to stress the CPU

Downloads the application code

Creates a dedicated directory for the web application

Downloads and deploys (extracts) the application into the specified directory

Tells the application the bucket where the images are available

Tells the application the Region where the application is running

Installs the application dependencies

Starts the web application

Paste the previous snippet into the user data field and make the following changes:



For the IMAGES\_BUCKET variable at the top of the code snippet, update the current place holder value with the ImagesBucket value provided in this instruction’s left panel.

For the INSTALLATION\_BUCKET variable at the top of the code snippet, update the current place holder value with the InstallationBucket value provided in this instruction’s left panel.

For the YOUR-DEFAULT-AWS-REGION variable at the top, update the current place holder value with the DefaultAWSRegion value provided in this instruction’s left panel.

Choose Create launch template.



You should see a message stating, Successfully created lab-app-launch-template.



 Congratulations! You successfully created a Launch Template.



###### **Task 4: Create an Auto Scaling group**

In this task, you use your Launch Template to create an Auto Scaling group.



Navigate to the bottom of the Success page from the previous task. Choose View launch templates.



The launch template is now ready. Next, you create an Auto Scaling group.



In the left navigation pane, locate the Auto Scaling section, and choose Auto Scaling Groups.



Choose Create Auto Scaling group.



In the Name section, select the Auto Scaling group name field, and enter app-asg.



In the Launch template section, select the Launch template dropdown, and choose lab-app-launch-template.



Choose Next.



In the Network section, configure the following:



In the VPC dropdown choose Lab VPC.

In the Availability Zones and subnets dropdown, choose Public Subnet 1 and Public Subnet 2.

Choose Next.



In the Load balancing section, choose Attach to an existing load balancer.



In the Attach to an existing load balancer section, configure the following:



Select Choose from your load balancer target groups.

In the Existing load balancer target groups dropdown, choose lab-app-target-group | HTTP.

In the Health checks section, choose  Turn on Elastic Load Balancing health checks.



Choose Next.



In the Group size – optional section, enter the following values:



Desired capacity:2

Minimum capacity: 2

Maximum capacity: 4

In the Scaling policies – optional section, configure the following:



Choose  Target tracking scaling policy.

Change the Target value to 30.

Change the Instance warmup to 300.

 Note: The values used in this lab are for demonstration purposes. In a production environment, you would configure values based on your actual needs.



Choose Next.



In the Add notifications section, choose Add notification.



In the Notification 1 section, locate the SNS Topic option.



Choose Create a topic, and configure the following:



Send a notification to: lab-app-sns-topic

With these recipients: Your email address

Choose Next.



Choose Next again.



Navigate to the bottom of the Review screen, and choose Create Auto Scaling group.



You should see a message stating, app-asg, 1 Scaling policy, 1 Topic, 1 Subscription, 1 Notification created successfully.



Check your email for a message containing the subject AWS Notification – Subscription Confirmation and open it.



In the email, choose the Confirm subscription link.



A new browser tab will open with the subscription confirmation. A message should state Subscription confirmed!. You can close this browser tab.



Navigate back to the browser tab with the Auto Scaling groups. Note the Status may be in an Updating capacity state. Use the  Refresh button to see Status change until you receive a blank message. The Instances columns should return a value of 2.



In the left navigation pane, locate the Load Balancing section, and choose Target Groups.



Choose the lab-app-target-group link.



Choose the Targets tab.



You should see two new instances launching (or already launched) created from the launch template. You should also see the original EC2 instance hosting the employee directory application named Web Application. Wait until the Status shows as  healthy for both instances. Use the  Refresh button to see Status changes.



 Caution: If you do not remove the original EC2 Instance, you may experience performance issues, as the Auto Scaling group you create, using the launch template, does not account for the original EC2 instance. For best results, delete this EC2 Instance!



In the left navigation pane, locate the Instances section, and choose Instances.



Select the EC2 Instance named  Web Application.



From the Instance State dropdown menu, choose Terminate (delete) instance.



Select Terminate (delete).



Use the  Refresh button to see instance state change to Shutting-down.



Wait for the instance state to change to Terminated. Switch to the web browser tab with the public DNS URL of your load balancer. Refresh the browser tab and confirm the application is still available.



Your target group no longer includes your original EC2 instance as a registered target. You can now proceed with the application testing phase of your project.



 Congratulations! You successfully created an Auto Scaling group using a launch template and verified the addition of new EC2 instances to the target group.



###### **Task 5: Test the Application**

In this task, you test the employee directory application and validate the application is load balancing between different availability zones. Then, you conduct a load test to trigger a scaling event to test the horizontal scaling of your application.



Return to the web browser tab with the employee directory application.



 Note: If you closed this browser tab, copy the DNS name of your Load Balancer into a new tab. See the previous tasks for specific instructions.



In the Employee Directory application, locate the Administration section in the left pane, and choose Configuration.



The Configuration Settings page shows the current Availability Zone.



Refresh the page a few times. Notice the change in the Availability Zone.



Now, you create a simulated load on the CPU of the instance to test horizontal scaling.



In The Admin Tools section, select the Stress Application Server For: dropdown, and choose 10 minutes. At the top, a message shows  Stressing….



After approximately 10 minutes, return to the web browser tab with the load balancer page.



Return to the browser tab with the AWS Management Console.



In the left navigation pane, locate the Load Balancing section, and choose Target Groups.



Choose the lab-app-target-group link.



Choose the Targets tab.



The stress test should trigger the provisioning of additional instance(s) to provide a working demo of the horizontal scaling. You should also receive a notification email.



 Note: The time elapsed to trigger a scaling event depends on the settings of the health checks, which you configured during the creation of the Load Balancer. \*Dive Deep to learn more about cooldown periods and health checks and how they impact the horizontal scaling of your application.



If you notice the original EC2 instance in the list of registered targets, select the  Refresh button to update the list of registered targets and it should disappear from the list.



 Congratulations! You successfully tested the employee directory application for high availability and horizontal scaling. Your company couldn’t be happier with the new application and decided to approve it immediately.

