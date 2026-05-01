# **AWS(Amazon Web Services)**



**Welcome to the Course**

**AWS Cloud Technical Essentials is a fundamental-level course. It’s designed to build your competence, confidence, and credibility with practical cloud skills that can help you innovate and advance your professional future. Here’s a quick overview of the skills that you will learn in each week of this first course.**



**Week 1: Getting Started with AWS Cloud**



**In this week, you will learn the definition of cloud computing and how to describe the cloud value proposition. You will learn how to differentiate between workloads that run on premises compared to workloads that run in the cloud, and how to create an AWS account. You will also get an overview of AWS, including how to differentiate between AWS Regions and Availability Zones, and the different ways that you can interact with AWS. Finally, you will learn best practices for using AWS Identity and Access Management (IAM).**



**Week 2: AWS Compute \& Networking**



**Week 2 is where you will learn how AWS compute services differ from other AWS services. The content for this week covers the basic components of Amazon Elastic Compute Cloud (Amazon EC2) architecture, and how to differentiate between a container and a virtual machine. You will also learn about the features and advantages of using serverless technologies, in addition to basic networking concepts and the features of Amazon Virtual Private Cloud (Amazon VPC).**



**Week 3: Storage \& Databases on AWS**



**This week, you will learn important concepts for AWS storage services—such as buckets and objects for Amazon Simple Storage Service (Amazon S3), and how Amazon Elastic Block Store (Amazon EBS) is used on AWS. You will also explore databases on AWS, and the use cases for each AWS storage service.**



**Week 4: Monitoring, Optimizing, and Going Serverless on AWS**



**In Week 4, you will learn about the benefits of monitoring on AWS, and how to optimize solutions on AWS. You will also learn about the function of Elastic Load Balancing (ELB), and how to differentiate between vertical scaling and horizontal scaling.**







## **AWS: What is cloud computing?**

Cloud computing is the on-demand delivery of IT resources over the Internet with pay-as-you-go pricing. Instead of buying, owning, and maintaining physical data centers and servers, you can access technology services, such as computing power, storage, and databases, on an as-needed basis from a cloud provider like Amazon Web Services (AWS).



### **Who is using cloud computing?**

Organizations of every type, size, and industry are using the cloud for a wide variety of use cases, such as data backup, disaster recovery, email, virtual desktops, software development and testing, big data analytics, and customer-facing web applications. For example, healthcare companies are using the cloud to develop more personalized treatments for patients. Financial services companies are using the cloud to power real-time fraud detection and prevention. And video game makers are using the cloud to deliver online games to millions of players around the world.



**What are cloud services?**

Cloud services are **IT resources** managed by AWS and delivered on demand over the internet. Traditionally, organizations had to purchase and configure everything from server hardware and storage systems to networking and security technologies before launching any digital system. Provisioning and managing IT infrastructure is expensive, complicated; and takes time away from innovation.



**What are cloud managed services?**

Cloud services are also called cloud managed services because the underlying infrastructure is fully managed by AWS. All required hardware, operating systems, and other infrastructure layers are stored and managed in highly secure AWS data centers distributed around the globe. We purchase and maintain all types of IT resources, making them available as services you can access in your application code.



**Example uses of cloud services:**

Cloud services can be used for everything—from **provisioning servers** and **storage** to **data analytics**, **artificial** **intelligence**, and **end-to-end security** for every application.



#### **The Six Benefits of Cloud Computing:**

**Pay as you go**. Instead of investing in data centers and hardware before you know how you are going to use them, you pay only when you use computing resources, and pay only for how much you use.



**Benefit from massive economies of scale**. By using cloud computing, you can achieve a lower cost than you can get on your own. Because usage from hundreds of thousands of customers is aggregated in the cloud, AWS can achieve higher economies of scale, which translates into lower pay as-you-go prices.



**Stop guessing capacity**. Eliminate guessing on your infrastructure capacity needs. When you make a capacity decision prior to deploying an application, you often end up either sitting on expensive idle resources or dealing with limited capacity. With cloud computing, these problems go away. You can access as much or as little capacity as you need, and scale up and down as required with only a few minutes notice.



**Increase speed and agility**. IT resources are only a click away, which means that you reduce the time to make those resources available to your developers from weeks to just minutes. This results in a dramatic increase in agility for the organization since the cost and time it takes to experiment and develop is significantly lower.



**Stop spending money running and maintaining data centers**. Focus on projects that differentiate your business, not the infrastructure. Cloud computing lets you focus on your customers, rather than on the heavy lifting of racking, stacking, and powering physical infrastructure. This is often referred to as undifferentiated heavy lifting.



**Go global in minutes**. Easily deploy your application in multiple Regions around the world with just a few clicks. This means you can provide lower latency and a better experience for your customers at a minimal cost.





#### **Types of cloud computing:**

**The three main types of cloud computing include -**

**1. Infrastructure as a Service**

**2. Platform as a Service**

**3. Software as a Service**



**Each type of cloud computing provides different levels of control, flexibility, and management so that you can select the right set of services for your needs.**





**Infrastructure as a Service (IaaS):**

IaaS contains the basic building blocks for cloud IT. It typically provides access to networking features, computers (virtual or on dedicated hardware), and data storage space. IaaS gives you the highest level of flexibility and management control over your IT resources. It is most similar to the existing IT resources with which many IT departments and developers are familiar.



**Platform as a Service (PaaS)**

PaaS removes the need for you to manage underlying infrastructure (usually hardware and operating systems), and allows you to focus on the deployment and management of your applications. This helps you be more efficient as you don’t need to worry about resource procurement, capacity planning, software maintenance, patching, or any of the other undifferentiated heavy lifting involved in running your application.



**Software as a Service (SaaS)**

SaaS provides you with a complete product that is run and managed by the service provider. In most cases, people referring to SaaS are referring to end-user applications (such as web-based email). With a SaaS offering, you don’t have to think about how the service is maintained or how the underlying infrastructure is managed. You only need to think about how you will use that particular software.





### **AWS Global Infrastructure**

Infrastructure, like data centers and networking connectivity, still exists as the foundation of every cloud application. In AWS, this physical infrastructure makes up the AWS Global Infrastructure, in the form of Availability Zones and Regions.



**REGIONS**

Regions are geographic locations worldwide where AWS hosts its data centers. AWS Regions are named after the location where they reside. For example, in the United States, there is a Region in Northern Virginia called the Northern Virginia Region and a Region in Oregon called the Oregon Region. There are Regions in Asia Pacific, Canada, Europe, the Middle East, and South America, and AWS continues to expand to meet the needs of its customers. Each AWS Region is associated with a geographical name and a Region code.





Here are a few examples of Region codes:



us-east-1: This is the first Region created in the east of the US. The geographical name for this Region is N. Virginia.



ap-northeast-1: The first Region created in the northeast of Asia Pacific. The geographical name for this Region is Tokyo.



AWS Regions are independent from one another. This means that your data is not replicated from one Region to another, without your explicit consent and authorization.



##### **CHOOSE THE RIGHT AWS REGION:**

Consider four main aspects when deciding which AWS Region to host your applications and workloads:

1. **latency**
2. **price**
3. **service availability**
4. **compliance**.





**Latency**. If your application is sensitive to latency, choose a Region that is close to your user base. This helps prevent long wait times for your customers. Synchronous applications such as gaming, telephony, WebSockets, and IoT are significantly affected by higher latency, but even asynchronous workloads, such as ecommerce applications, can suffer from an impact on user connectivity.



**Price**. Due to the local economy and the physical nature of operating data centers, prices may vary from one Region to another. The pricing in a Region can be impacted by internet connectivity, prices of imported pieces of equipment, customs, real estate, and more. Instead of charging a flat rate worldwide, AWS charges based on the financial factors specific to the location.



**Service** **availability**. Some services may not be available in some Regions. The AWS documentation provides a table containing the Regions and the available services within each one.



**Data compliance**. Enterprise companies often need to comply with regulations that require customer data to be stored in a specific geographic territory. If applicable, you should choose a Region that meets your compliance requirements.



###### **Availability Zones (AZ)**

Inside every Region is a cluster of Availability Zones (AZ). An AZ consists of one or more data centers with redundant power, networking, and connectivity. These data centers operate in discrete facilities with undisclosed locations. They are connected using redundant high-speed and low-latency links. AZs also have a code name. Since they’re located inside Regions, they can be addressed by appending a letter to the end of the Region code name. For example:



us-east-1a: an AZ in us-east-1 (Northern Virginia Region)



sa-east-1b: an AZ in sa-east-1 (São Paulo Region in South America)







### **Interacting with AWS**

**Every action you make in AWS is an API call** that is authenticated and authorized. In AWS, you can make API calls to services and resources through the AWS Management Console, the AWS Command Line Interface (CLI), or the AWS Software Development Kits (SDKs).



Ways to Interact with AWS API:

1. **The AWS Management Console**: One way to manage cloud resources is through the web-based console, where you log in and click on the desired service. This can be the easiest way to create and manage resources when you’re first begin working with the cloud. The services are placed in categories, such as compute, database, storage and security, identity and compliance.
2. **The AWS Command Line Interface**: The AWS CLI is a unified tool to manage AWS services. With just one tool to download and configure, you control multiple AWS services from the command line and automate them with scripts. The AWS CLI is open-source, and there are installers available for Windows, Linux, and Mac OS.
3. **The AWS Software Development Kits**: API calls to AWS can also be performed by executing code with programming languages. You can do this by using AWS Software Development Kits (SDKs). SDKs are open-source and maintained by AWS for the most popular programming languages, such as C++, Go, Java, JavaScript, .NET, Node.js, PHP, Python, and Ruby. Developers commonly use AWS SDKs to integrate their application source code with AWS services.



Here is an example of code you can implement to work with AWS resources using the Python AWS SDK.



**import boto3**

**ec2 = boto3.client('ec2')**

**response = ec2.describe\_instances()**

**print(response)**





### **Security and the AWS Shared Responsibility Model**

When you begin working with the AWS Cloud, managing security and compliance is a shared responsibility between AWS and you. To depict this shared responsibility, AWS created the shared responsibility model. This distinction of responsibility is commonly referred to as security of the cloud, versus security in the cloud.



**WHAT IS AWS RESPONSIBLE FOR?**

AWS is responsible for security of the cloud. This means AWS is required to protect and secure the infrastructure that runs all the services offered in the AWS Cloud. AWS is responsible for:



1. Protecting and securing AWS Regions, Availability Zones, and data centers, down to the physical security of the buildings



2\. Managing the hardware, software, and networking components that run AWS services, such as the physical server, host operating systems, virtualization layers, and AWS networking components



**WHAT IS THE CUSTOMER RESPONSIBLE FOR?**

You’re responsible for security in the cloud. When using any AWS service, you’re responsible for properly configuring the service and your applications, as well as ensuring your data is secure.







### **Introduction to AWS Identity and Access Management (IAM)**



#### **WHAT IS IAM?**

IAM is a web service that enables you to manage access to your AWS account and resources. It also provides a centralized view of **who and what are allowed inside your AWS account (authentication)**, and **who and what have permissions to use and work with your AWS resources (authorization)**. With IAM, you can share access to an AWS account and resources without having to share your set of access keys or password. You can also provide granular access to those working in your account, so that people and services only have permissions to the resources they need. For example, to provide a user of your AWS account with read-only access to a particular AWS service, you can granularly select which actions and which resources in that service they can access.



###### **GET TO KNOW THE IAM FEATURES**

To help control access and manage identities within your AWS account, IAM offers many features to ensure security.



1. IAM is global and not specific to any one Region. This means you can see and use your IAM configurations from any Region in the AWS Management Console.

2\. IAM is integrated with many AWS services by default.

3\. You can establish password policies in IAM to specify complexity requirements and mandatory rotation periods for users.

4\. IAM supports MFA.

5\. IAM supports identity federation, which allows users who already have passwords elsewhere—for example, in your corporate network or with an internet identity provider—to get temporary access to your AWS account.

6\. Any AWS customer can use IAM; the service is offered at no additional charge.



###### **WHAT IS AN IAM USER?**

An IAM user represents a person or service that interacts with AWS. You define the user within your AWS account. And any activity done by that user is billed to your account. Once you create a user, that user can sign in to gain access to the AWS resources inside your account. You can also add more users to your account as needed. For example, for your cat photo application, you could create individual users in your AWS account that correspond to the people who are working on your application. Each person should have their own login credentials. Providing users with their own login credentials prevents sharing of credentials.



###### **IAM USER CREDENTIALS**

An IAM user consists of a name and a set of credentials. When creating a user, you can choose to provide the user:



1. Access to the AWS Management Console



2\. Programmatic access to the AWS Command Line Interface (AWS CLI) and AWS Application Programming Interface (AWS API)



To access the AWS Management Console, provide the users with a user name and password. For programmatic access, AWS generates a set of access keys that can be used with the AWS CLI and AWS API.



IAM user credentials are considered permanent, in that they stay with the user until there’s a forced rotation by admins. When you create an IAM user, you have the option to grant permissions directly at the user level. This can seem like a good idea if you have only one or a few users. However, as the number of users helping you build your solutions on AWS increases, it becomes more complicated to keep up with permissions.



###### **WHAT IS AN IAM GROUP?**

An IAM group is a collection of users. All users in the group inherit the permissions assigned to the group. This makes it easy to give permissions to multiple users at once. It’s a more convenient and scalable way of managing permissions for users in your AWS account. This is why using IAM groups is a best practice. If you have a an application that you’re trying to build and have multiple users in one account working on the application, you might decide to organize these users by job function. You might want IAM groups organized by developers, security, and admins. You would then place all of your IAM users in the respective group for their job function. This provides a better view to see who has what permissions within your organization and an easier way to scale as new people join, leave, and change roles in your organization.



Consider the following examples.



1. A new developer joins your AWS account to help with your application. You simply create a new user and add them to the developer group, without having to think about which permissions they need.



2\. A developer changes jobs and becomes a security engineer. Instead of editing the user’s permissions directly, you can instead remove them from the old group and add them to the new group that already has the correct level of access.



###### **Keep in mind the following features of groups.**



1. Groups can have many users.

2\. Users can belong to many groups.

3\. Groups cannot belong to groups.



The root user can perform all actions on all resources inside an AWS account by default. This is in contrast to creating new IAM users, new groups, or new roles.

New IAM identities can perform no actions inside your AWS account by default until you explicitly grant them permission. The way you grant permissions in IAM is by using IAM policies.



###### **WHAT IS AN IAM POLICY?**

To manage access and provide permissions to AWS services and resources, you create IAM policies and attach them to IAM users, groups, and roles. Whenever a user or role makes a request, AWS evaluates the policies associated with them.



For example, if you have a developer inside the developers group who makes a request to an AWS service, AWS evaluates any policies attached to the developers group and any policies attached to the developer user to determine if the request should be allowed or denied.



**IAM POLICY EXAMPLES**

Most policies are stored in AWS as JSON documents with several policy elements. Take a look at the following example of what providing admin access through an IAM identity-based policy looks like.



{

"Version": "2012-10-17",



     \*\*"Statement": \[{



          "Effect": "Allow",



          "Action": "\*",



          "Resource": "\*"

     }]







}



In this policy, there are four major JSON elements: **Version, Effect, Action, and Resource**.



1. The **Version** element defines the version of the policy language. It specifies the language syntax rules that are needed by AWS to process a policy. To use all the available policy features, include "Version": "2012-10-17" before the "Statement" element in all your policies.



2\. The **Effect** element specifies whether the statement will allow or deny access. In this policy, the Effect is "Allow", which means you’re providing access to a particular resource.



3\. The **Action** element describes the type of action that should be allowed or denied. In the above policy, the action is **"\*"**. This is called a **wildcard**, and it is used to symbolize every action inside your AWS account.



4\. The **Resource** element specifies the object or objects that the policy statement covers. In the policy example above, the resource is also the wildcard "\*". This represents all resources inside your AWS console.



**Putting all this information together, you have a policy that allows you to perform all actions on all resources inside your AWS account. This is what we refer to as an administrator policy.**



Let’s look at another example of a more granular IAM policy.



**{"Version": "2012-10-17",**



     "Statement": \[{



          "Effect": "Allow",



          "Action": \[



               "iam: ChangePassword",

               "iam: GetUser"

               ]

          "Resource": \\\\\\\*\\\\\\\*"arn:aws:iam::123456789012:user/${aws:username}"\\\\\\\*\\\\\\\*



























     }]



**}**



After looking at the JSON, you can see that this policy allows the IAM user to change their own IAM password (iam:ChangePassword) and get information about their own user (iam:GetUser). It only permits them to access their own credentials because the resource restricts access with the variable substitution ${aws:username}.





###### **Understand Policy Structure**



**Element : Description : Required : Example**



1. Effect : Specifies whether the statement results in an allow or an explicit deny : ✔ : "Effect": "Deny"



2\. Action : Describes the specific actions that will be allowed or denied : ✔ : "Action": "iam:CreateUser"



3\. Resource : Specifies the object or objects that the statement covers : ✔ : "Resource": "arn:aws:iam::account-ID-without-hyphens:user/Bob"





**The basic structure of an IAM policy:**

**Effect** indicates whether to Allow or Deny the permissions.

**Action** specifies the API calls allowed to an AWS service (such as cloudwatch:ListMetrics).

**Resource** defines the scope of entities covered by the policy rule (i.e., a specific Amazon S3 bucket, Amazon EC2 instance, or \\\*, which indicates any resource).





An IAM policy contains a series of elements, including a Version, Statement, Sid, Effect, Principal, Action, Resource, and Condition.





### **IAM Roles:**

1. No static login credentials
2. IAM Roles are assumed programmatically
3. Credentials are temporary for a configurable amount of time
4. Credentials expire and rotated



##### **Role Based Access in AWS**



A brief summary of some of the most important IAM best practices you need to be familiar with before building out solutions on AWS.



1. **LOCK DOWN THE AWS ROOT USER**



The root user is an all-powerful and all-knowing identity within your AWS account. If a malicious user were to gain control of root-user credentials, they would be able to access every resource within your account, including personal and billing information. To lock down the root user:



* Don’t share the credentials associated with the root user.



* Consider deleting the root user access keys.



* Enable MFA on the root account.





**2. FOLLOW THE PRINCIPLE OF LEAST PRIVILEGE**



Least privilege is a standard security principle that advises you to grant only the necessary permissions to do a particular job and nothing more. To implement least privilege for access control, start with the minimum set of permissions in an IAM policy and then grant additional permissions as necessary for a user, group, or role.



**3. USE IAM APPROPRIATELY**



IAM is used to secure access to your AWS account and resources. It simply provides a way to create and manage users, groups, and roles to access resources within a single AWS account.



IAM is not used for website authentication and authorization, such as providing users of a website with sign-in and sign-up functionality. IAM also does not support security controls for protecting operating systems and networks.



**4. USE IAM ROLES WHEN POSSIBLE**



Maintaining roles is easier than maintaining users. When you assume a role, IAM dynamically provides temporary credentials that expire after a defined period of time, between 15 minutes and 36 hours. Users, on the other hand, have long-term credentials in the form of user name and password combinations or a set of access keys.



User access keys only expire when you or the admin of your account rotates these keys. User login credentials expire if you have applied a password policy to your account that forces users to rotate their passwords.



When a user assumes a role, AWS Identity and Access Management (IAM) dynamically provides temporary credentials that expire after a defined period of time, between 15 minutes and 36 hours.



**5. CONSIDER USING AN IDENTITY PROVIDER**



If you decide to make your cat photo application into a business and begin to have more than a handful of people working on it, consider managing employee identity information through an identity provider (IdP). Using an IdP, whether it be an AWS service such as AWS IAM Identity Center (Successor to AWS Single Sign-On) or a third-party identity provider, provides you a single source of truth for all identities in your organization. You no longer have to create separate IAM users in AWS. You can instead use IAM roles to provide permissions to identities that are federated from your IdP.



For example, you have an employee, Martha, that has access to multiple AWS accounts. Instead of creating and managing multiple IAM users named Martha in each of those AWS accounts, you can manage Martha in your company’s IdP. If Martha moves within the company or leaves the company, Martha can be updated in the IdP, rather than in every AWS account you have.



**6. CONSIDER AWS IAM IDENTITY CENTER**



If you have an organization that spans many employees and multiple AWS accounts, you may want your employees to sign in with a single credential. AWS IAM Identity Center is an IdP that lets your users sign in to a user portal with a single set of credentials. It then provides them access to all their assigned accounts and applications in one central location. AWS IAM Identity Center is similar to IAM, in that it offers a directory where you can create users, organize them in groups, and set permissions across those groups, and grant access to AWS resources. However, AWS IAM Identity Center has some advantages over IAM.



For example, if you’re using a third-party IdP, you can sync your users and groups to AWS IAM Identity Center. This removes the burden of having to re-create users that already exist elsewhere, and it enables you to manage those users from your IdP. More importantly, AWS IAM Identity Center separates the duties between your IdP and AWS, ensuring that your cloud access management is not inside or dependent on your IdP.





###### **AWS IAM LAB:**

1. Explore IAM Users and Groups
2. Inspect IAM policies applied to groups
3. Follow a real-world scenario that adds users to groups and explores group permissions
4. Locate and use the IAM sign-in URL
5. Experiment with policies and service access



IAM Roles for EC2:

1. Create roles
2. Add to groups (create if not exists)
3. Assign policies on groups
4. Create user and add it to group



###### **EC2 instance: One Single Virtual Machine**





###### **IAM Roles and the Employee Directory Application**

Throughout the demos, you’ll notice that the Amazon EC2 instance is using an IAM role to manage access to AWS APIs for the employee directory application. This is a common way to provide AWS credentials to applications that need to access AWS APIs. This IAM role is providing temporary credentials that are rotated automatically via the instance profile for the EC2 instance. The AWS SDK is automatically pulling these credentials and refreshing them as needed and using the credentials to authenticate the AWS API calls being made to Amazon S3 and Amazon DynamoDB by the code for the employee directory app. Without this role, the application would not be authenticated and the API calls to those services would fail.



In the video Demo AWS IAM you saw Morgan create an IAM role called EmployeeWebApp which used the managed policies AmazonS3FullAccess and AmazonDynamoDBFullAccess. Later in the Hosting the Employee Directory Application on AWS video and subsequent demos you may see an IAM role named S3DynamoDBFullAccessRole being used when configuring the EC2 instance. Both of these roles use the same policies Morgan selected in the Demo AWS IAM role.



The next video in this course demonstrates how to host the employee directory application on AWS using services like Amazon EC2 and Amazon VPC. While watching this video, you may be looking for a copy of the scripts used so you can follow along. The exercises in next weeks content includes step by step instructions on how to launch the employee direction application, including the user data script. For this next video, we recommend that you watch without following along yet so you can understand the AWS services at a high level, then next week you will have the opportunity to walk through this demonstration in your AWS account using the instructions included in the exercises.



A VPC is a private network for AWS resources.



##### **Default Amazon Machine Image (AMI) for Amazon EC2**

**Amazon Linux 2023 user data script:**



          #!/bin/bash -ex



          wget

https://aws-tc-largeobjects.s3-us-west-2.amazonaws.com/DEV-AWS-MO-GCNv2/FlaskApp.zip



          unzip FlaskApp.zip



          cd FlaskApp/



          yum -y install python3-pip



          pip install -r requirements.txt



          yum -y install stress



          export PHOTOS\_BUCKET=${SUB\_PHOTOS\_BUCKET}



          export AWS\_DEFAULT\_REGION=<INSERT REGION HERE>



          export DYNAMO\_MODE=on



          FLASK\_APP=application.py /usr/local/bin/flask run --host=0.0.0.0 --port=80



 



When using the user data scripts, remember to replace the <INSERT REGION HERE> with whatever AWS region you are operating in, and ensure you remove both brackets as well.





# **Module-2: Compute \& Networking**



#### **Compute as a Service (CaaS) on AWS**



###### **Understanding Servers**

The first building block you need to host an application is a server. Servers often times can handle Hypertext Transfer Protocol (HTTP) requests and send responses to clients following the client-server model, though any API based communication also falls under this model. A client being a person or computer that sends a request, and a server handling the requests is a computer, or collection of computers, connected to the internet serving websites to internet users. These servers power your application by providing CPU, memory, and networking capacity to process users’ requests and transform them into responses.



For context, common HTTP servers include:



1. Windows options, such as Internet Information Services (IIS).
2. Linux options, such as Apache HTTP Web Server, Nginx, and Apache Tomcat.



To run an HTTP server on AWS, you need to find a service that provides compute power in the AWS Management Console. You can log into the console and view the complete list of AWS compute services.



**Compute:**

1. AWS App Runner: Build and run production web applications at scale
2. Batch: Fully managed batch processing at any scale
3. EC2: Virtual Servers in the Cloud
4. EC2 Image Builder: A managed service to automate build, customize and deploy OS images
5. Elastic Beanstalk: Run and Manage Web Apps
6. Lambda: Run Code without Thinking about Servers
7. Lightsail: Launch and Manage Virtual Private Servers
8. AWS Outposts: Run AWS Services On Premises
9. Serverless Application Repository: Assemble, deploy, and share serverless applications within teams or publicly



**Choose the Right Compute Option**

If you’re responsible for setting up servers on AWS to run your infrastructure, you have many compute options. You need to know which service to use for which use case.

At a fundamental level, there are three types of compute options:

1. virtual machines
2. container services
3. serverless



If you’re coming to AWS with prior infrastructure knowledge, a virtual machine can often be the easiest compute option in AWS to understand. This is because a virtual machine emulates a physical server and allows you to install an HTTP server to run your applications. To run these virtual machines, you install a hypervisor on a host machine. This hypervisor provisions the resources to create and run your virtual machines. In AWS, these virtual machines are called Amazon Elastic Compute Cloud or Amazon EC2. Behind the scenes, AWS operates and manages the host machines and the hypervisor layer. AWS also installs the virtual machine operating system, called the guest operating system. Some AWS compute services use Amazon EC2 or use virtualization concepts under the hood, therefore it is best to understand this service first before moving on to container services and serverless compute.



### **Introduction to Amazon Elastic Compute Cloud**



Amazon Machine Image (AMI)

Root volume template:

* Typically contains the OS
* Applications pre-installed on instance at boost

Launch permissions

Block device mapping



###### **What Is Amazon EC2?**



Amazon EC2 is a web service that provides secure, resizable compute capacity in the cloud.

It allows you to provision **virtual servers called EC2 instances**.

Although AWS uses the phrase “web service” to describe it, it doesn’t mean that you are limited to running just web servers on your EC2 instances.

You can create and manage these instances through the AWS Management Console, the AWS Command Line Interface (CLI), AWS Software Development Kits (SDKs), or through automation tools and infrastructure orchestration services.



In order to create an EC2 instance, you need to define:



* Hardware specifications, like CPU, memory, network, and storage.
* Logical configurations, like networking location, firewall rules, authentication, and the operating system of your choice.



When launching an EC2 instance, the first setting you configure is which operating system you want by selecting an Amazon Machine Image (AMI).



###### **What Is an AMI?**

A**n AMI is a template that contains the software configuration (operating system, application server, and applications) required to launch your instance**. You can select an AMI provided by AWS, AWS user community, or the AWS Marketplace; or you can select one of your own AMIs.



In the traditional infrastructure world, the process of spinning up a server consists of installing an operating system from installation disks, installation drives, or installation wizards over the network. In the AWS Cloud, this operating system installation is no longer your responsibility, and is instead built into the AMI that you choose. Not only does an AMI let you configure which operating system you want, you can also select storage mappings, the architecture type (such as 32-bit, 64-bit, or 64-bit ARM), and additional software installed.



###### **What Is the Relationship Between AMIs and EC2 Instances?**

EC2 instances are live instantiations of what is defined in an AMI, much like a cake is a live instantiation of a cake recipe. If you are familiar with software development, you can also see this kind of relationship between a Class and an Object.



A Class is something you model and define, while an object is something you interact with. In this case, the AMI is how you model and define your instance, while the EC2 instance is the entity you interact with, where you can install your web server, and serve your content to users. When you launch a new instance, AWS allocates a virtual machine that runs on a hypervisor. Then the AMI you selected is copied to the root device volume, which contains the image used to boot the volume. In the end, you get a server you can connect to and install packages and any additional software. In this case, you install a web server along with the properly configured source code of your employee directory app.



One advantage of using AMIs is that they are reusable.



You might choose a Linux-based AMI and configure the HTTP server, application packages, and any additional software you may need to run your application.



* If you wanted to create a second EC2 instance with the same configurations, how can you easily do that? One option is to go through the entire instance creation and configuration process and try to match your settings to the first instance. However, this is time consuming and leaves room for human error.



* The second, better option, is to create an AMI from your running instance and use this AMI to start a new instance. This way, your new instance will have all the same configurations as your current instance, because the configurations set in the AMIs are the same.





###### Where Can You Find AMIs?

You can select an AMI from the following categories.



* **Quick Start AMIs** that are premade by AWS and allow you to get started quickly.
* **AWS Marketplace AMIs** that provide popular open source and commercial software from third-party vendors.
* **My AMIs** that are created from your EC2 instances.
* **Community AMIs** that are provided by the AWS user community.
* Build your own custom image with **EC2 Image Builder**.



Each AMI in the AWS Management Console has an **AMI ID**, which is prefixed by “**ami-**”, followed by a **random hash of numbers and letters**. These IDs are unique to each AWS region.



### **Amazon EC2 Instance Lifecycle**



AMI ->(launching) -> Pending -> Running (chargeable); -> (Reboot) -> Rebooting; -> (Stop) or (Stop-Hibernate) -> Stopping -> Stopped -> (Start) -> Pending or Terminated; -> Shutting-down -> (Terminate) -> Terminated



Terminated: means it cannot be found, recovered, lost just like throwing in ocean and there's no hope of finding it.



Note: Terminated instances remain visible in the AWS Management Console for some time after they have been terminated, but make no mistake, they are deleted.



###### **What Makes Up an EC2 Instance**

Combination of vCPUs, memory, network, storage, and GPUs (optional).



Instance types = family prefix + size (e.g., c5.large → compute-optimized, 5th gen, large capacity).



###### **Instance Families**

**General purpose**: Balanced compute, memory, networking.

**Use cases**: Web servers, microservices, caching, dev environments.



**Compute optimized**: High-performance processors.

**Use cases**: Scientific modeling, batch processing, analytics, HPC, ML, gaming.



**Memory optimized**: Large in-memory datasets.

**Use cases**: Databases, caching, big-data analytics.



**Accelerated computing**: Hardware accelerators (GPU, FPGA).

**Use cases**: 3D rendering, video encoding, graphics workloads.



**Storage optimized**: High sequential read/write, low-latency IOPS.

**Use cases**: NoSQL DBs, data warehousing, Elasticsearch, analytics.



###### **Networking \& Placement**

**Default placement**: Default VPC (public, internet-accessible).



**Best practice**: Use custom VPCs for private data.



Instances reside in Availability Zones → design for high availability (multiple instances across zones).



##### **Lifecycle States**

1. Pending → preparing instance (AMI copy, networking setup). Billing not started.



2\. Running → instance ready, billing starts. Actions: reboot, stop, terminate.



3\. Reboot → OS-level restart, same host/IP, data preserved.



4\. Stop/Start → instance may move to new host, new public IP, private IP same. Instance store data lost.



5\. Terminate → instance deleted, IPs lost, instance store erased. Cannot access again.



###### **Stop vs Stop-Hibernate**

Stop: RAM data lost, EBS storage persists.



Stop-Hibernate: RAM contents saved to EBS, restored on restart. Useful for caching layers.



###### **Pricing Model**

1. On-Demand: Pay per second/hour, no commitment. Flexible but costlier.



2\. Reserved Instances (RI): 1–3 year commitment, discounted rates. Payment options: All Upfront > Partial Upfront > No Upfront.



3\. Spot Instances: Up to 90% cheaper, but can be interrupted (2-min warning). Best for fault-tolerant workloads (big data, CI/CD, high-performance computing (HPC) , rendering).





### **Container Services on AWS**



Container Orchestration Services:

* Amazon Elastic Container Service (Amazon ECS)
* Amazon Elastic Kubernetes Service (Amazon EKS)



AWS Fargate is a serverless compute platform for Amazon ECS and Amazon EKS.



The three main categories of compute are virtual machines, containers, and serverless. There is no one-size-fits-all service because it depends on your needs.



###### **What is a Container?**

A container is a standardized unit that packages up your code and all of its dependencies. This package is designed to run reliably on any platform, because the container creates its own independent environment. This makes it easy to carry workloads from one place to another, such as from development to production or from on-premises to the cloud.



###### **What is DOCKER?**

Docker is a popular container runtime that simplifies the management of the entire operating system stack needed for container isolation, including networking and storage. Docker makes it easy to create, package, deploy, and run containers.



###### **WHAT IS THE DIFFERENCE BETWEEN CONTAINERS AND VMS?**



Containers share the same operating system and kernel as the host they exist on, whereas virtual machines contain their operating system. Since each virtual machine has to maintain a copy of an operating system, there’s a degree of wasted space. A container is more lightweight. They spin up quicker, almost instantly. This difference in startup time becomes instrumental when designing applications that need to scale quickly during input/output (I/O) bursts. While containers can provide speed, virtual machines offer you the full strength of an operating system and offer more resources, like package installation, a dedicated kernel, and more.



###### **ORCHESTRATE CONTAINERS**

In AWS, containers run on EC2 instances. For example, you may have a large instance and run a few containers on that instance. While running one instance is easy to manage, it lacks high availability and scalability. Most companies and organizations run many containers on many EC2 instances across several Availability Zones.

If you’re trying to manage your compute at a large scale, you need to know:



* How to place your containers on your instances.
* What happens if your container fails.
* What happens if your instance fails.
* How to monitor deployments of your containers.



This coordination is handled by a **container orchestration service**.

AWS offers two container orchestration services: Amazon Elastic Container Service (**ECS**) and Amazon Elastic Kubernetes Service (**EKS**).





###### **MANAGE CONTAINERS WITH AMAZON ELASTIC CONTAINER SERVICE (AMAZON ECS)**

Amazon ECS is an end-to-end container orchestration service that allows you to quickly spin up new containers and manage them across a cluster of EC2 instances.



To run and manage your containers, you need to install the Amazon ECS Container Agent on your EC2 instances. This agent is open source and responsible for communicating back to the Amazon ECS service about cluster management details. You can run this agent on both Linux and Windows AMIs.

An instance with the container agent installed is often called a **container instance**.



To prepare your application to run on Amazon ECS, you create a task definition. The task definition is a text file, in JSON format, that describes one or more containers.

A task definition is similar to a blueprint that describes the resources you need to run that container, such as CPU, memory, ports, images, storage, and networking information.



**Simple Task Definition that the runs on the Nginx web server.**



{



     "family": "webserver",



     "containerDefinitions": \[ {



          "name": "web",



          "image": "nginx",



          "memory": "100",



          "cpu": "99"



     } ],



     "requiresCompatibilities": \[ "FARGATE" ],



     "networkMode": "awsvpc",



     "memory": "512",



     "cpu": "256"



}



###### **USE KUBERNETES WITH AMAZON ELASTIC KUBERNETES SERVICE (AMAZON EKS)**

Kubernetes is a portable, extensible, open source platform for managing containerized workloads and services. By bringing software development and operations together by design, Kubernetes created a rapidly growing ecosystem that is very popular and well established in the market. If you already use Kubernetes, you can use Amazon EKS to orchestrate these workloads in the AWS Cloud. Amazon EKS is conceptually similar to Amazon ECS, but there are some differences.



* An EC2 instance with the ECS Agent installed and configured is called a container instance. In Amazon EKS, it is called a worker node.



* An ECS Container is called a task. In the Amazon EKS ecosystem, it is called a pod.



* While Amazon ECS runs on AWS native technology, Amazon EKS runs on top of Kubernetes.



If you have containers running on Kubernetes and want an advanced orchestration solution that can provide simplicity, high availability, and fine-grained control over your infrastructure, Amazon EKS is the tool for you.



### **Serverless and AWS Lambda**

**REMOVE THE UNDIFFERENTIATED HEAVY LIFTING**



If you run your code on Amazon EC2, AWS is responsible for the physical hardware and you are responsible for the logical controls, such as guest operating system, security and patching, networking, security, and scaling.



If you run your code in containers on Amazon ECS and Amazon EKS, AWS is responsible for more of the container management, such as deploying containers across EC2 instances and managing the container cluster. However, when running ECS and EKS on EC2, you are still responsible for maintaining the underlying EC2 instances.



If you want to deploy your workloads and applications without having to manage any EC2 instances, you can do that on AWS with serverless compute.



**GO SERVERLESS**



* Every definition of serverless mentions four aspects.
* No servers to provision or manage.
* Scales with usage.
* You never pay for idle resources.
* Availability and fault tolerance are built-in.



With serverless, spend time on the things that differentiate your application, rather than spending time on ensuring availability, scaling, and managing servers. AWS has several serverless compute options, including **AWS Fargate and AWS Lambda**.



**EXPLORE SERVERLESS CONTAINERS WITH AWS FARGATE**



Amazon ECS and Amazon EKS enable you to run your containers in two modes.



* Amazon EC2 mode
* AWS Fargate mode



AWS Fargate is a purpose-built serverless compute engine for containers. Fargate scales and manages the infrastructure, allowing developers to work on what they do best: application development.



It achieves this by allocating the right amount of compute, eliminating the need to choose and handle EC2 Instances and cluster capacity and scaling. Fargate supports both Amazon ECS and Amazon EKS architecture and provides workload isolation and improved security by design.



AWS Fargate abstracts the EC2 instance so you’re not required to manage it. However, with AWS Fargate, you can use all the same ECS primitives, APIs, and AWS integrations.



**RUN YOUR CODE ON AWS LAMBDA**



If you want to deploy your workloads and applications without having to manage any EC2 instances or containers, you can use AWS Lambda. AWS Lambda lets you run code without provisioning or managing servers or containers. You can run code for virtually any type of application or backend service, including data processing, real-time stream processing, machine learning, WebSockets, IoT backends, mobile backends, and web apps, like your corporate directory app!



AWS Lambda requires zero administration from the user. You upload your source code and Lambda takes care of everything required to run and scale your code with high availability. There are no servers to manage, bringing you continuous scaling with subsecond metering and consistent performance.



**HOW LAMBDA WORKS**



There are three primary components of a Lambda function:

1\. trigger

2\. code

3\. configuration.



The code is source code, that describes what the Lambda function should run. This code can be authored in three ways.



* You create the code from scratch.
* You use a blueprint that AWS provides.
* You use same code from the AWS Serverless Application Repository, a resource that contains sample applications, such as “hello world” code, Amazon Alexa Skill sample code, image resizing code, video encoding, and more.



When you create your Lambda function, you specify the runtime you want your code to run in. There are built-in runtimes such as **Python, Node.js, Ruby, Go, Java, .NET Core**, or you can implement your Lambda functions to run on a custom runtime.



The configuration of a Lambda function consists of information that describes how the function should run. In the configuration, you specify network placement, environment variables, memory, invocation type, permission sets, and other configurations.



Triggers describe when the Lambda function should run.



A trigger integrates your Lambda function with other AWS services, enabling you to run your Lambda function in response to certain API calls that occur in your AWS account. This makes you quicker to respond to events in your console without having to perform manual actions. All you need is the what, how, and when of a Lambda function to have functional compute capacity that runs only when you need it to.





### **Networking on AWS**



**WHAT IS NETWORKING?**



Networking is how you connect computers around the world and allow them to communicate with one another. In this trail, you’ve already seen a few examples of networking. One is the AWS global infrastructure. AWS has created a network of resources using data centers, Availability Zones, and Regions.



**KNOW THE NETWORKING BASICS**



Think about sending a letter. When sending a letter, there are three pieces of information you need.



* The payload or letter inside the envelope.
* The address of the sender in the From section.
* The address of the recipient in the To section.



Let’s go further. Each address must contain information such as:



* Name of sender and recipient
* Street
* City
* State or province
* Zip, area, or postal code
* Country



You need all parts of an address to ensure that your letter gets to its destination. Without the correct address, postal workers are not able to properly deliver the message. In the digital world, computers handle the delivery of messages in a similar way. This is called routing.



**WHAT ARE IP ADDRESSES?**



In order to properly route your messages to a location, you need an address. Just like each home has a mail address, **each computer has an IP address**. However, instead of using the combination of street, city, state, zip code, and country, the **IP address uses a combination of bits, 0s and 1s**.



Here is an example of a 32-bit address in binary format:

11000000 10101000 00000001 00011110



It’s called 32-bit because you have 32 digits. Feel free to count!



**WHAT IS IPV4 NOTATION?**



Typically, you don’t see an IP address in this binary format. Instead, it’s converted into decimal format and noted as an Ipv4 address.



In the diagram below, the 32 bits are grouped into groups of 8 bits, also called octets. Each of these groups is converted into decimal format separated by a period.

192.168.1.30



In the end, this is what is called an **Ipv4 address**. This is **important to know when trying to communicate to a single computer**. But remember, you’re working with a network. This is where CIDR Notation comes in.



**USE CIDR (Classless Inter-Domain Routing) NOTATION**



192.168.1.30 is a single IP address. If you wanted to express IP addresses between the range of 192.168.1.0 and 192.168.1.255, how can you do that?



One way is by using Classless Inter-Domain Routing (CIDR) notation. **CIDR notation is a compressed way of specifying a range of IP addresses**. **Specifying a range determines how many IP addresses are available to you**.



CIDR notation looks like this:

**192.168.1.0/24**



It begins with a starting **IP address** and is separated by a **forward slash** (the “/” character) followed by a number. The **number at the end specifies how many of the bits of the IP address are fixed**. In this example, the first 24 bits of the IP address are fixed. The rest are flexible.



32 total bits subtracted by 24 fixed bits leaves 8 flexible bits. Each of these flexible bits can be either 0 or 1, because they are binary. That means you have two choices for each of the 8 bits, providing 256 IP addresses in that IP range.



The **higher the number after the /, the smaller the number of IP addresses in your network**. For example, a range of 192.168.1.0/24 is smaller than 192.168.1.0/16.



When working with networks in the AWS Cloud, you choose your network size by using CIDR notation. In AWS, the **smallest IP range you can have is /28**, **which provides you 16 IP addresses. The largest IP range you can have is a /16, which provides you with 65,536 IP addresses**.





### **Introduction to Amazon VPC**

A VPC is an isolated network you create in the AWS cloud, similar to a traditional network in a data center. When you create a VPC, you need to choose three main things.

* The name of your VPC.
* A Region for your VPC to live in. Each VPC spans multiple Availability Zones within the Region you choose.
* A IP range for your VPC in CIDR notation. This determines the size of your network. Each VPC can have up to four /16 IP ranges.



Using this information, AWS will provision a network and IP addresses for that network.



Create a Subnet After you create your VPC, you need to create subnets inside of this network. Think of subnets as smaller networks inside your base network—or virtual area networks (VLANs) in a traditional, on-premises network. In an on-premises network, the typical use case for subnets is to isolate or optimize network traffic. In AWS, subnets are used for high availability and providing different connectivity options for your resources. When you create a subnet, you need to choose three settings.

* The VPC you want your subnet to live in, in this case VPC (10.0.0.0/16).
* The Availability Zone you want your subnet to live in, in this case AZ1.
* A CIDR block for your subnet, which must be a subset of the VPC CIDR block, in this case 10.0.0.0/24.



When you launch an EC2 instance, you launch it inside a subnet, which will be located inside the Availability Zone you choose.





High Availability with A VPC When you create your subnets, keep high availability in mind. In order to maintain redundancy and fault tolerance, create at least two subnets configured in two different Availability Zones.



As you learned earlier in the trail, it’s important to consider that “everything fails all the time.” In this case, if one of these AZs fail, you still have your resources in another AZ available as backup.





**Reserved IPs For AWS** to configure your VPC appropriately, AWS reserves five IP addresses in each subnet. These IP addresses are used for routing, Domain Name System (DNS), and network management.



For example, consider a VPC with the IP range 10.0.0.0/22. The VPC includes 1,024 total IP addresses. This is divided into four equal-sized subnets, each with a /24 IP range with 256 IP addresses. Out of each of those IP ranges, there are only 251 IP addresses that can be used because AWS reserves five.



Since AWS reserves these five IP addresses, it can impact how you design your network. A common starting place for those who are new to the cloud is to create a VPC with a IP range of /16 and create subnets with a IP range of /24. This provides a large amount of IP addresses to work with at both the VPC and subnet level.



#### **Gateways**



**Internet Gateway**



To enable internet connectivity for your VPC, you need to create an internet gateway. Think of this gateway as similar to a modem. Just as a modem connects your computer to the internet, the internet gateway connects your VPC to the internet. Unlike your modem at home, which sometimes goes down or offline, an internet gateway is highly available and scalable. After you create an internet gateway, you then need to attach it to your VPC.



**Virtual Private Gateway**



A virtual private gateway allows you to connect your AWS VPC to another private network. Once you create and attach a VGW to a VPC, the gateway acts as anchor on the AWS side of the connection. On the other side of the connection, you’ll need to connect a customer gateway to the other private network. A customer gateway device is a physical device or software application on your side of the connection. Once you have both gateways, you can then establish an encrypted VPN connection between the two sides.



### **Amazon VPC Routing and Security**

###### 

###### **The Main Route Table**

When you create a VPC, AWS creates a route table called the main route table. A route table contains a set of rules, called routes, that are used to determine where network traffic is directed. AWS assumes that when you create a new VPC with subnets, you want traffic to flow between them. Therefore, the default configuration of the main route table is to allow traffic between all subnets in the local network. Below is an example of a main route table:



There are two main parts to this route table.



* The destination, which is a range of IP addresses where you want your traffic to go. In the example of sending a letter, you need a destination to route the letter to the appropriate place. The same is true for routing traffic. In this case, the destination is the IP range of our VPC network.
* The target, which is the connection through which to send the traffic. In this case, the traffic is routed through the local VPC network.



###### **Custom Route Tables**

While the main route table controls the routing for your VPC, you may want to be more granular about how you route your traffic for specific subnets. For example, your application may consist of a frontend and a database. You can create separate subnets for these resources and provide different routes for each of them.



If you associate a custom route table with a subnet, the subnet will use it instead of the main route table. By default, each custom route table you create will have the local route already inside it, allowing communication to flow between all resources and subnets inside the VPC.



[https://d3c33hcgiwev3.cloudfront.net/imageAssetProxy.v1/lzRNbgqzQQioh0fpHy6zWg\_bd8b7ce5e5514fd39b01059f416511f1\_image.png?expiry=1767759465811\&hmac=\_I7Ya1ja\_tf\_M3HzHLmi9c-aZUroxsn93biZPknsyBU](https://d3c33hcgiwev3.cloudfront.net/imageAssetProxy.v1/lzRNbgqzQQioh0fpHy6zWg_bd8b7ce5e5514fd39b01059f416511f1_image.png?expiry=1767759465811&hmac=_I7Ya1ja_tf_M3HzHLmi9c-aZUroxsn93biZPknsyBU)



**🌐 VPC Route Tables**



Main Route Table: Created automatically with a new VPC.



Default: allows traffic between all subnets in the local VPC network.



Contains destination (IP range) and target (connection path).



Custom Route Tables:



Can be associated with specific subnets for granular control.



Always include the local route by default to enable communication inside the VPC.



**🔒 Network ACLs (Access Control Lists)**



Act as firewalls at the subnet level.



Default ACL: allows all inbound and outbound traffic.



Can restrict traffic by protocol, port, and IP range.



Stateless: rules must be defined for both inbound and outbound traffic.



Example:



Allow inbound HTTPS (port 443) and RDP (port 3389) from specific sources.



Allow outbound responses on ephemeral ports (1025–65535).



**🛡️ Security Groups**



Firewalls at the EC2 instance level.



Default configuration:



* Blocks all inbound traffic.
* Allows all outbound traffic.



Stateful: automatically allows return traffic for initiated connections.



Must explicitly open inbound ports for services (e.g., HTTP 80, HTTPS 443).



Common design:



* Web tier → Application tier (HTTP).
* Application tier → Database tier (MySQL).
* Provides isolation similar to VLANs in traditional networks.



**✅ Key Takeaways**



* Route tables manage where traffic flows.
* Network ACLs secure subnets (stateless).
* Security groups secure EC2 instances (stateful).



Together, they provide layered security and routing flexibility in AWS VPCs.



### **Common network troubleshooting steps for Amazon VPC**

In the demos throughout this course, you will see the Employee Directory Application being launched onto a Amazon EC2 instance that is placed in a public subnet in an Amazon VPC. There are multiple networking configurations that play into whether an instance is accessible to the internet or not.



Below we will run down a list of configurations you should check if you ever have a public EC2 instance with a web application that is not loading as expected.



1\. Internet gateway



Ensure that an Internet Gateway (IGW) is attached to your VPC. Without the internet gateway, no traffic will be allowed in or out of the VPC.



2\. Route tables



Check the route table associated with the subnet of your EC2 instance. Ensure there is a route with a destination of 0.0.0.0/0 that points to the Internet Gateway. This route allows outbound traffic to the internet.



3\. Security groups



Review the security group settings attached to your EC2 instance. Make sure there are inbound rules allowing HTTP (port 80) and/or HTTPS (port 443) traffic from the internet (0.0.0.0/0). Also, verify that outbound rules allow traffic to leave the instance.



4\. Network Access Control Lists



Check the NACLs associated with your subnet. Ensure that they allow inbound and outbound traffic for HTTP and HTTPS. Unlike security groups, NACLs are stateless, so you must explicitly allow both inbound and outbound rules.



5\. Public IP address



Ensure your EC2 instance has a public IP address assigned. You can check this in the EC2 console under the instance details. If it does not have a public IP, relaunch the instance and ensure you have the configuration for assigning a public IP address set correctly.



6\. HTTP vs HTTPS



Confirm that your application is accessible via the correct protocol. If your application is configured for HTTPS, ensure SSL/TLS certificates are correctly installed and configured. Also, check if the web browser is trying to connect via the wrong protocol (HTTP instead of HTTPS or vice versa). For this course, the application is operating via HTTP, double check that your browser is not trying to connect via HTTPS. You can do this by selecting the address bar in the browser and making sure the address starts with http and not https.



7\. User data script



If your instance uses a user data script to configure the application on launch, verify that the script has run successfully. Check the instance logs (/var/log/cloud-init.log or /var/log/cloud-init-output.log) for any errors that may have occurred during the execution of the user data script.



8\. Permissions



Verify the permissions and roles attached to your EC2 instance. Ensure the instance has the necessary IAM roles and policies to access any required AWS services, such as S3, DynamoDB, or RDS.



9\. Personal network permissions



Ensure that your personal or corporate network does not have restrictions blocking access to the public IP address of your EC2 instance. Some networks might have firewalls or proxy settings that could block outbound traffic to certain IP ranges or ports.



10\. Application



Ensure that your application code is correctly deployed and running. Check the application's logs to diagnose any runtime errors. Also, make sure the web server (e.g., Apache, Nginx) is installed and running.





# **Storage \& Databases on AWS**

#### **Storage Types on AWS**

AWS storage services are grouped into three different categories:

1. block storage
2. file storage
3. object storage.



**File Storage**

File storage is ideal when you require centralized access to files that need to be easily shared and managed by multiple host computers. Typically, this storage is mounted onto multiple hosts and requires file locking and integration with existing file system communication protocols.

Common use cases for file storage include:

* Large content repositories
* Development environments
* User home directories



**Block Storage**



While file storage treats files as a singular unit, block storage splits files into fixed-size chunks of data called blocks that have their own addresses. Since each block is addressable, blocks can be retrieved efficiently.



When data is requested, these addresses are used by the storage system to organize the blocks in the correct order to form a complete file to present back to the requestor. Outside of the address, there is no additional metadata associated with each block. So, when you want to change a character in a file, you just change the block, or the piece of the file, that contains the character. This ease of access is why block storage solutions are fast and use less bandwidth.



Since block storage is optimized for low-latency operations, it is a typical storage choice for high-performance enterprise workloads, such as databases or enterprise resource planning (ERP) systems, that require low-latency storage.



**Object Storage**



Objects, much like files, are also treated as a single unit of data when stored. However, unlike file storage, these objects are stored in a flat structure instead of a hierarchy. Each object is a file with a unique identifier. This identifier, along with any additional metadata, is bundled with the data and stored.



Changing just one character in an object is more difficult than with block storage. When you want to change one character in a file, the entire file must be updated.



With object storage, you can store almost any type of data, and there is no limit to the number of objects stored, making it easy to scale. Object storage is generally useful when storing large data sets, unstructured files like media assets, and static assets, such as photos.





#### **Amazon EC2 Instance Storage and Amazon Elastic Block Store (EBS)**



**Amazon EC2 Instance Store**



 Amazon EC2 Instance Store provides temporary block-level storage for your instance. This storage is located on disks that are physically attached to the host computer. This ties the lifecycle of your data to the lifecycle of your EC2 instance. If you delete your instance, the instance store is deleted as well. Due to this, instance store is considered ephemeral storage. Read more about it in the

 AWS documentation

.



Instance store is ideal if you are hosting applications that replicate data to other EC2 instances, such as Hadoop clusters. For these cluster-based workloads, having the speed of locally attached volumes and the resiliency of replicated data helps you achieve data distribution at high performance. It’s also ideal for temporary storage of information that changes frequently, such as buffers, caches, scratch data, and other temporary content.



**Amazon Elastic Block Storage (Amazon EBS)**  As the name implies, Amazon EBS is a block-level storage device that you can attach to an Amazon EC2 instance. These storage devices are called Amazon EBS volumes. EBS volumes are essentially drives of a user-configured size attached to an EC2 instance, similar to how you might attach an external drive to your laptop.



 EBS volumes act similarly to external drives in more than one way.



Most Amazon EBS volumes can only be connected with one computer at a time. Most EBS volumes have a one-to-one relationship with EC2 instances, so they cannot be shared by or attached to multiple instances at one time. Note: Recently, AWS announced the Amazon EBS multi-attach feature that enables volumes to be attached to multiple EC2 instances at one time. This feature is not available for all instance types and all instances must be in the same Availability Zone.



You can detach an EBS volume from one EC2 instance and attach it to another EC2 instance in the same Availability Zone, to access the data on it.



The external drive is separate from the computer. That means, if an accident happens and the computer goes down, you still have your data on your external drive. The same is true for EBS volumes.



You’re limited to the size of the external drive, since it has a fixed limit to how scalable it can be. For example, you may have a 2 TB external drive and that means you can only have 2 TB of content on there. This relates to EBS as well, since volumes also have a max limitation of how much content you can store on the volume.



**Scale Amazon EBS Volumes**

You can scale Amazon EBS volumes in two ways.



* **Increase the volume size**, as long as it doesn’t increase above the maximum size limit. For EBS volumes, the maximum amount of storage you can have is 16 TB. That means if you provision a 5 TB EBS volume, you can choose to increase the size of your volume until you get to 16 TB.



* **Attach multiple volumes to a single Amazon EC2 instance**. EC2 has a one-to-many relationship with EBS volumes. You can add these additional volumes during or after EC2 instance creation to provide more storage capacity for your hosts.



**Amazon EBS Use Cases**

Amazon EBS is useful when you need to retrieve data quickly and have data persist long-term. Volumes are commonly used in the following scenarios.



* Operating systems: Boot/root volumes to store an operating system. The root device for an instance launched from an Amazon Machine Image (AMI) is typically an Amazon EBS volume. These are commonly referred to as EBS-backed AMIs.



* Databases: A storage layer for databases running on Amazon EC2 that rely on transactional reads and writes.



* Enterprise applications: Amazon EBS provides reliable block storage to run business-critical applications.



* Throughput-intensive applications: Applications that perform long, continuous reads and writes.



**Amazon EBS Volume Types**



1. **EBS Provisioned IOPS SSD**: Highest performance SSD designed for latency-sensitive transactional workloads : I/O-intensive NoSQL and relational databases : volume size (4 GB-16 TB) : Max IOPS/Volume (64,000) : Max Throughput/Volume (1,000 MB/s)



2\. **EBS General Purpose SSD**: General purpose SSD that balances price and performance for a wide variety of transactional workloads : Boot volumes, low-latency interactive apps, development, and test : volume size (1 GB-16 TB) : Max IOPS/Volume (16,000) : Max Throughput/Volume (250 MB/s)



3\. **Throughput Optimized HDD**: Low-cost HDD designed for frequently accessed, throughput intensive workloads : Big data, data warehouses, log processing : volume size (500 GB-16 TB) : Max IOPS/Volume (500) : Max Throughput/Volume (500 MB/s)



4\. **Cold HDD**: Lowest cost HDD designed for less frequently accessed workloads: Colder data requiring fewer scans per day : volume size (500 GB-16 TB) : Max IOPS/Volume (250) : Max Throughput/Volume (250 MB/s)



There are two main categories of Amazon EBS volumes: **solid-state drives (SSDs) and hard-disk drives (HDDs)**.

SSDs provide strong performance for random input/output (I/O), while HDDs provide strong performance for sequential I/O. AWS offers two types of each.





**Benefits of Using Amazon EBS**

Here are the following benefits of using Amazon EBS (in case you need a quick cheat sheet).



* High availability: When you create an EBS volume, it is automatically replicated within its Availability Zone to prevent data loss from single points of failure.



* Data persistence: The storage persists even when your instance doesn’t.



* Data encryption: All EBS volumes support encryption.



* Flexibility: EBS volumes support on-the-fly changes. You can modify volume type, volume size, and input/output operations per second (IOPS) capacity without stopping your instance.



* Backups: Amazon EBS provides you the ability to create backups of any EBS volume.





**EBS Snapshots**

Errors happen. One of those errors is not backing up data, and then, inevitably losing that data. To prevent this from happening to you, you should back up your data—even in AWS. Since your EBS volumes consist of the data from your Amazon EC2 instance, you’ll want to take **backups of these volumes**, called **snapshots**.



EBS snapshots are incremental backups that only save the blocks on the volume that have changed after your most recent snapshot. For example, if you have 10 GB of data on a volume, and only 2 GB of data have been modified since your last snapshot, only the 2 GB that have been changed are written to Amazon Simple Storage Service (Amazon S3).



When you take a snapshot of any of your EBS volumes, these backups are stored redundantly in multiple Availability Zones using Amazon S3. This aspect of storing the backup in Amazon S3 will be handled by AWS, so you won’t need to interact with Amazon S3 to work with your EBS snapshots. You simply manage them in the EBS console (which is part of the EC2 console).



EBS snapshots can be used to create multiple new volumes, whether they’re in the same Availability Zone or a different one. When you create a new volume from a snapshot, it’s an exact copy of the original volume at the time the snapshot was taken.



#### 

#### **Object Storage with Amazon S3**



Amazon Simple Storage Service (Amazon S3) is a standalone object storage service that is not tied to compute resources, unlike Amazon EBS. It allows users to store and retrieve data from anywhere on the web, similar to online backup services, but it uses object storage rather than block or file storage. Object storage stores data in a flat structure, where each object consists of a file, its metadata, and a unique identifier. Amazon S3 supports storing an unlimited number of objects.



Core Concepts of Amazon S3



In Amazon S3, all objects must be stored inside buckets, and a bucket must be created before uploading any object. When creating a bucket, two mandatory choices are required:



* AWS Region – Objects in a bucket are redundantly stored across multiple devices and multiple Availability Zones within the chosen region, providing 99.999999999% durability and 99.99% availability annually.



* Bucket Name – The name must be globally unique across all AWS accounts. Once deleted, the name becomes available for reuse.



Each object in Amazon S3 is identified using a URL, which includes the bucket name, service name (s3), AWS provider, and the object key (name). Although folders can be used for organization, S3 does not have a true hierarchical file system; it is internally a flat structure, with folders serving only as logical prefixes for easier human understanding.



Common Amazon S3 Use Cases



* Amazon S3 supports a wide range of use cases, including:
* Backup and storage, including EBS snapshots
* Media hosting for videos, photos, and music (objects up to 5 TB each)
* Software distribution for downloadable applications
* Data lakes with scalable storage from gigabytes to petabytes
* Static website hosting using HTML, CSS, and client-side scripts
* Static content storage with global web access and unlimited scalability
* Access Control and Connectivity



All Amazon S3 resources (buckets, folders, and objects) are private by default and accessible only by the creating AWS account. Resources can be made public, but public access allows anyone on the internet to view them. For more granular access control, Amazon S3 uses IAM policies and S3 bucket policies.



IAM policies are attached to users, groups, or roles and are best used when managing multiple buckets with different permissions or when centralized policy management is needed.



S3 bucket policies are attached directly to buckets, written in JSON, and control what actions are allowed or denied on bucket resources. They are commonly used for cross-account access or when IAM policy size limits are exceeded. Bucket policies apply to all objects in the bucket but cannot be applied to individual folders or objects.



###### **Encryption in Amazon S3**



Amazon S3 supports encryption in transit and at rest:



* Server-side encryption: Amazon S3 encrypts data before storing it and decrypts it upon retrieval.
* Client-side encryption: Data is encrypted before upload, with the user managing keys and tools.
* Encryption in transit is achieved using client-side encryption or SSL.



###### **Object Versioning**



Amazon S3 uses object names (keys) to identify objects. Without versioning, uploading an object with the same name overwrites the existing one. S3 Versioning allows multiple versions of the same object to coexist in a bucket, preventing data loss from accidental deletions or overwrites.



When versioning is enabled:



* Each object receives a unique version ID
* Deleted objects are marked with a delete marker instead of being permanently removed
* Overwrites create new object versions while preserving older ones



Versioning states include:



* Unversioned (default) – No versioning
* Versioning-enabled – All objects are versioned
* Versioning-suspended – New objects are unversioned, existing versions remain



All versions incur storage costs, so unused versions may need to be deleted to reduce expenses.



###### **Amazon S3 Storage Classes**



Amazon S3 offers multiple storage classes to optimize cost based on access patterns:



* S3 Standard – General-purpose storage for frequently accessed data
* S3 Intelligent-Tiering – Automatically moves data between frequent and infrequent access tiers
* S3 Standard-Infrequent Access (IA) – For infrequently accessed data with rapid retrieval needs
* S3 One Zone-IA – Lower-cost IA storage in a single Availability Zone
* S3 Glacier Instant Retrieval – Low-cost archival storage with millisecond retrieval
* S3 Glacier Flexible Retrieval – Lower-cost archival storage with asynchronous retrieval
* S3 Glacier Deep Archive – Lowest-cost storage for long-term retention (7–10+ years)
* Amazon S3 on Outposts – Object storage for on-premises AWS Outposts environments



###### **Lifecycle Management**



Amazon S3 lifecycle policies automate storage management through:



* Transition actions, which move objects between storage classes
* Expiration actions, which permanently delete objects



Lifecycle management is ideal for:



* Periodic logs that are needed temporarily
* Data with changing access frequency, such as documents that are frequently accessed initially, later archived for compliance, and eventually deleted



**S3 Bucket Policies:**

* Use JSON format
* Specify what actions are allowed or denied on the bucket
* Can only be placed on buckets





#### **Choose the Right Storage Service**

Here’s a recap of all the storage services mentioned so far. By the end of this reading, you should be able to better answer the question “Which storage service should I use?” for some of the more common scenarios.



###### **Amazon EC2 Instance Store**

Instance store is ephemeral block storage. This is preconfigured storage that exists on the same physical server that hosts the EC2 instance and cannot be detached from Amazon EC2. You can think of it as a built-in drive for your EC2 instance. Instance store is generally well-suited for temporary storage of information that is constantly changing, such as buffers, caches, and scratch data. It is not meant for data that is persistent or long-lasting. If you need persistent long-term block storage that can be detached from Amazon EC2 and provide you more management flexibility, such as increasing volume size or creating snapshots, then you should use Amazon EBS.



###### **Amazon EBS**

Amazon EBS is meant for data that changes frequently and needs to persist through instance stops, terminations, or hardware failures. Amazon EBS has two different types of volumes: SSD-backed volumes and HDD-backed volumes.



SSD-backed volumes have the following characteristics.



* Performance depends on IOPS (input/output operations per second).
* Ideal for transactional workloads such as databases and boot volumes.



HDD-backed volumes have the following characteristics:



* Performance depends on MB/s.
* Ideal for throughput-intensive workloads, such as big data, data warehouses, log processing, and sequential data I/O.



Here are a few important features of Amazon EBS that you need to know when comparing it to other services.



* It is block storage.
* You pay for what you provision (you have to provision storage in advance).
* EBS volumes are replicated across multiple servers in a single Availability Zone.
* Most EBS volumes can only be attached to a single EC2 instance at a time.



###### **Amazon S3**

If your data doesn’t change that often, Amazon S3 might be a more cost-effective and scalable storage solution. S3 is ideal for storing static web content and media, backups and archiving, data for analytics, and can even be used to host entire static websites with custom domain names.Here are a few important features of Amazon S3 to know about when comparing it to other services.



* It is object storage.
* You pay for what you use (you don’t have to provision storage in advance).
* Amazon S3 replicates your objects across multiple Availability Zones in a Region.
* Amazon S3 is not storage attached to compute.



###### **File Storage: Amazon EFS and Amazon FSx**

When File Storage is Needed:

* When multiple EC2 instances need shared access
* When POSIX or Windows file systems are required



Services Overview



Amazon EFS : Fully managed NFS file system



Amazon FSx for Windows File Server : SMB protocol , Windows-based workloads



Amazon FSx for Lustre : High-performance workloads, Integrated with Amazon S3



Here are a few important features of Amazon EFS and FSx to know about when comparing them to other services.



* It is file storage.
* You pay for what you use (you don’t have to provision storage in advance).
* Amazon EFS and Amazon FSx can be mounted onto multiple EC2 instances



###### **Quick Decision Guide (When to Choose What)**



* Temporary data → EC2 Instance Store
* Persistent block storage → Amazon EBS
* Highly scalable, durable object storage → Amazon S3
* Shared file systems across EC2 → Amazon EFS / FSx
* Long-term archival \& compliance data → S3 Glacier / Deep Archive





#### **Explore Databases on AWS**

###### **1. History of Enterprise Databases**



In the early days of enterprise computing, choosing a database was simple because very few options were available.



Businesses typically selected one database vendor and used it for all applications.



Often, organizations chose a database before fully understanding their use case.



Since the 1970s, the most commonly used database type in enterprises has been the relational database.



###### **2. What Is a Relational Database?**



A relational database organizes data into tables.



Data in one table can be linked to data in other tables using relationships.



Tables consist of:



* Rows (records): Contain all information about a specific entry.
* Columns (attributes): Describe properties of that entry.



The attribute which appears in multiple tables, create a relationship between them.



Schema:

Tables, rows, columns, and their relationships together form a logical schema.



In relational databases:



* The schema is fixed
* Schema changes are difficult after deployment
* Most data modeling must be done upfront before the database becomes operational



###### **3. Relational Database Management System (RDBMS)**

An RDBMS allows users to: Create, Update, Administer a relational database



Common RDBMS examples: MySQL, PostgreSQL, Oracle, SQL Server, Amazon Aurora



SQL and Querying : Most RDBMS use Structured Query Language (SQL).



SQL enables:

* Simple queries
* Complex queries across multiple tables
* Joins allow querying data from multiple tables together, such as linking sales data with book and author information to identify business patterns.



4\. Benefits of Using a Relational Database



Joins: Enable meaningful relationships between tables



Reduced redundancy: Data is stored once and referenced across tables



Familiarity: Relational databases have been widely used since the 1970s



Many professionals already have experience with them



Accuracy and integrity



Data adheres to the ACID principles: Atomicity, Consistency, Isolation, Durability



###### **5. Use Cases for Relational Databases**



Relational databases power many mission-critical applications worldwide.



Best suited for:



* Applications with a stable schema that changes infrequently
* Lift-and-shift applications moved from on-premises to the cloud with minimal modification
* Ideal for applications requiring persistent, ACID-compliant storage, such as:

 	1. Enterprise Resource Planning (ERP) systems

 	2. Customer Relationship Management (CRM) systems

 	3. Commerce and financial applications



###### **6. Choosing Between Unmanaged and Managed Databases on AWS**

Core Concept



The choice between managed and unmanaged databases is a tradeoff between:

* Control
* Convenience



This concept is similar to the AWS Shared Responsibility Model.



###### **7. On-Premises Databases**



The customer is responsible for everything, including:

* Data center security
* Power and cooling
* Physical hardware
* Host machine management
* Database management
* Query optimization
* Customer data security



**Provides maximum control, but also maximum operational responsibility**.



###### **8. Unmanaged Databases on AWS (Database on EC2)**



When running a database on Amazon EC2, AWS manages:



* Physical infrastructure
* Hardware
* Operating system installation
* Customer manages:
* EC2 instance configuration
* Database installation and management
* Query optimization
* Customer data



This approach is called the unmanaged database option on AWS.



**AWS controls infrastructure, while the customer controls the host and database**.



###### **9. Managed Databases on AWS**



AWS handles:

* EC2 instance setup
* Database setup
* High availability
* Scalability
* Patching
* Backups



The customer remains responsible for:

* Database tuning
* Query optimization
* Securing customer data



Provides: Maximum convenience, but Least control compared to on-premises and unmanaged options



**Final Takeaway:**

* Relational databases remain essential for structured, mission-critical workloads.
* AWS offers flexibility through on-premises, unmanaged, and managed database models, allowing organizations to choose the right balance between control and operational simplicity.



### **Amazon Relational Database Service (Amazon RDS)**



Amazon Relational Database Service (Amazon RDS) is a fully managed service that enables you to create, operate, and scale relational databases in the cloud without handling traditional database administration tasks. It allows organizations to focus on application and business goals instead of infrastructure-related activities such as provisioning, patching, scaling, backups, and recovery.



Amazon RDS supports multiple database engines, including commercial databases (Oracle, SQL Server), open-source databases (MySQL, PostgreSQL, MariaDB), and a cloud-native option, Amazon Aurora, which is MySQL- and PostgreSQL-compatible and offers higher durability, availability, and performance than standard RDS engines.



RDS databases run on DB instances, which provide the compute and memory resources for the database engine. These instances are built on EC2 but are managed through the RDS console. RDS supports standard, memory-optimized, and burstable performance instance families, and uses Amazon EBS for storage, with options such as General Purpose SSD, Provisioned IOPS SSD, and Magnetic storage (not recommended).



Amazon RDS operates inside an Amazon VPC, using private subnets and DB subnet groups to enhance security. Network access is controlled through security groups, network ACLs, and IAM policies, ensuring only authorized applications and users can access the database.



For data protection, Amazon RDS provides automated backups (enabled by default) with point-in-time recovery for up to 35 days, and manual snapshots for long-term retention and compliance needs. Both backup methods are commonly used together.



To improve availability and fault tolerance, Amazon RDS offers Multi-AZ deployments, which maintain a synchronously replicated standby database in another Availability Zone. In case of failure, RDS performs an automatic failover using a single DNS endpoint, ensuring minimal downtime and continued database availability.



### **Introduction to Amazon DynamoDB**

###### **What Is Amazon DynamoDB?**

Amazon DynamoDB is a fully managed NoSQL database service that provides fast and predictable performance with seamless scalability. DynamoDB lets you offload the administrative burdens of operating and scaling a distributed database so that you don't have to worry about hardware provisioning, setup and configuration, replication, software patching, or cluster scaling.



With DynamoDB, you can create database tables that can store and retrieve any amount of data and serve any level of request traffic. You can scale up or scale down your tables' throughput capacity without downtime or performance degradation. You can use the AWS Management Console to monitor resource utilization and performance metrics.



DynamoDB automatically spreads the data and traffic for your tables over a sufficient number of servers to handle your throughput and storage requirements, while maintaining consistent and fast performance. All of your data is stored on solid-state disks (SSDs) and is automatically replicated across multiple Availability Zones in an AWS Region, providing built-in high availability and data durability.



###### **Core Components of Amazon DynamoDB**

In DynamoDB, **tables, items,** and **attributes** are the core components that you work with. A table is a collection of items, and each item is a collection of attributes. DynamoDB uses primary keys to uniquely identify each item in a table and secondary indexes to provide more querying flexibility.



**The following are the basic DynamoDB components:**



1. **Tables** – Similar to other database systems, DynamoDB stores data in tables. A table is a collection of data. For example, see the example table called People that you could use to store personal contact information about friends, family, or anyone else of interest. You could also have a Cars table to store information about vehicles that people drive.
2. **Items** – Each table contains zero or more items. An item is a group of attributes that is uniquely identifiable among all of the other items. In a People table, each item represents a person. For a Cars table, each item represents one vehicle. Items in DynamoDB are similar in many ways to rows, records, or tuples in other database systems. In DynamoDB, there is no limit to the number of items you can store in a table.
3. **Attributes** – Each item is composed of one or more attributes. An attribute is a fundamental data element, something that does not need to be broken down any further. For example, an item in a People table contains attributes called PersonID, LastName, FirstName, and so on. For a Department table, an item might have attributes such as DepartmentID, Name, Manager, and so on. Attributes in DynamoDB are similar in many ways to fields or columns in other database systems.



**Security with Amazon DynamoDB**

DynamoDB also offers **encryption at rest**, which eliminates the operational burden and complexity involved in protecting sensitive data.



#### **Choose the Right AWS Database Service**



###### **AWS Database Services**

AWS has a variety of different database options for different use cases.



**Database Type	::		Use Cases				::		AWS Service**



Relational	::	Traditional applications, ERP, CRM, e-commerce 	:: 	Amazon RDS, Amazon Aurora, Amazon Redshift



Key-value	::	High-traffic web apps, e-commerce systems, gaming applications	::	Amazon DynamoDB



In-memory	::Caching, session management, gaming leaderboards, geospatial applications ::Amazon ElastiCache for Memcached, Amazon ElastiCache for Redis



Document	::	Content management, catalogs, user profiles	::	Amazon DocumentDB (with MongoDB compatibility)



Wide column	::High-scale industrial apps for equipment maintenance, fleet management, and route optimization :: Amazon Keyspaces (for Apache Cassandra)



Graph		::	Fraud detection, social networking, recommendation engines	::	Amazon Neptune



Time series	::	IoT applications, DevOps, industrial telemetry	::	Amazon Timestream



Ledger		::	Systems of record, supply chain, registrations, banking transactions	:: 	Amazon QLDB





###### **Breaking Up Applications and Databases**

As the industry changes, applications and databases change too. Today, with larger applications, you no longer see just one database supporting it. Instead, these applications are being broken into smaller services, each with their own purpose-built database supporting it.



This shift removes the idea of a one-size-fits-all database and replaces it with a complimentary database strategy. You can give each database the appropriate functionality, performance, and scale that the workload requires.





# **Module-4: Monitoring and Optimizaion**





Data Points generated from resources -> Metrics/Time=Statistics



Amazon EC2 Metrics Example: CPUUtilization, NetworkIN, NetworkOut



Amazon RDS Example: DatabaseConnections





Elastic Load Balancer (ELB): Highly available, Automatically Scalable, Regional service



ELB Types:

1. Application Load Balancer - Layer 7: HTTP/HTTPS
2. Network Load Balancer - Layer 4: TCP/UDP/TLS
3. Gateway Load Balancer - Layer 3+4: IP (Third Party)



ALB Components:

1. Listener
2. Target group
3. Rule



3-tier application:

Presentation layer - User interface: HTML, CSS, JS

Application layer - Business/application logic

Data layer - Database





### **Reading 4.1: Monitoring on AWS**

When operating a website like the Employee Directory Application on AWS you may have questions like:



* How many people are visiting my site day to day?
* How can I track the number of visitors over time?
* How will I know if the website is having performance or availability issues?
* What happens if my Amazon Elastic Compute Cloud (EC2) instance runs out of capacity?
* Will I be alerted if my website goes down?



You need a way to collect and analyze data about the operational health and usage of your resources.



**The act of collecting, analyzing, and using data to make decisions or answer questions about your IT resources and systems is called monitoring.**   Monitoring enables you to have a near real-time pulse on your system and answer the questions listed above. You can use the data you collect to watch for operational issues caused by events like over-utilization of resources, application flaws, resource misconfiguration, or security-related events.   Think of the data collected through monitoring as outputs of the system, or metrics.



###### **Use Metrics to Solve Problems**

The resources that host your solutions on AWS all create various forms of data that you might be interested in collecting. You can think of each individual data point that is created by a resource as a metric. Metrics that are collected and analyzed over time become statistics, like the example of average CPU utilization over time below, showing a spike at 1:30.  Consider this: One way to evaluate the health of an Amazon EC2 instance is through **CPU utilization**. Generally speaking, if an EC2 instance has a high CPU utilization, it can mean a flood of requests. Or it can reflect a process that has encountered an error and is consuming too much of the CPU. When analyzing CPU utilization, take a process that exceeds a specific threshold for an unusual length of time. Use that abnormal event as a cue to either manually or automatically resolve the issue through actions like scaling the instance.  This is one example of a metric.

Other examples of metrics EC2 instances have are **network utilization, disk performance, memory utilization, and the logs** created by the applications running on top of EC2.



###### **Know the Different Types of Metrics**

Different resources in AWS create different types of metrics. An Amazon Simple Storage Service (S3) bucket would not have CPU utilization like an EC2 instance does. Instead, S3 creates metrics related to the objects stored in a bucket like the overall size, or the number of objects in a bucket. S3 also has metrics related to the requests made to the bucket such as reading or writing objects.  Amazon Relational Database Service (RDS) creates metrics such as database connections, CPU utilization of an instance, or disk space consumption. This is not a complete list for any of the services mentioned, but you can see how different resources create different metrics. You could be interested in a wide variety of metrics depending on the types of resources you are using, the goals you have, or the types of questions you want answered.



###### **Understand the Benefits of Monitoring**

Monitoring gives you visibility into your resources, but the question now is, "Why is that important?" The following are some of the benefits of monitoring.



1. Respond to operational issues proactively before your end users are aware of them. It’s a bad practice to wait for end users to let you know your application is experiencing an outage. Through monitoring, you can keep tabs on metrics like error response rate or request latency, over time, that help signal that an outage is going to occur. This enables you to automatically or manually perform actions to prevent the outage from happening—fixing the problem before your end users are aware of it.
2. Improve the performance and reliability of your resources. Monitoring the different resources that comprise your application provides you with a full picture of how your solution behaves as a system. Monitoring, if done well, can illuminate bottlenecks and inefficient architectures. This enables you to drive performance and reliability improvement processes.
3. Recognize security threats and events. When you monitor resources, events, and systems over time, you create what is called a baseline. A baseline defines what activity is normal. Using a baseline, you can spot anomalies like unusual traffic spikes or unusual IP addresses accessing your resources. When an anomaly occurs, an alert can be sent out or an action can be taken to investigate the event.
4. Make data-driven decisions for your business. Monitoring is not only to keep an eye on IT operational health. It also helps drive business decisions. For example, let’s say you launched a new feature for your cat photo app, and want to know whether it’s being used. You can collect application-level metrics and view the number of users who use the new feature. With your findings, you decide whether to invest more time into improving the new feature.
5. Create more cost-effective solutions. Through monitoring, you can view resources that are being underutilized and rightsize your resources to your usage. This helps you optimize cost and make sure you aren’t spending more money than necessary.



###### **Enable Visibility**

AWS resources create data you can monitor through metrics, logs, network traffic, events, and more. This data is coming from components that are distributed in nature, which can lead to difficulty in collecting the data you need if you don’t have a centralized place to review it all. AWS has already done that for you with a service called Amazon CloudWatch.



**Amazon CloudWatch is a monitoring and observability service that collects data like those mentioned in this module**. CloudWatch provides actionable insights into your applications, and enables you to respond to system-wide performance changes, optimize resource utilization, and get a unified view of operational health. This unified view is important.



You can use CloudWatch to:



* Detect anomalous behavior in your environments.
* Set alarms to alert you when something’s not right.
* Visualize logs and metrics with the AWS Management Console.
* Take automated actions like scaling.
* Troubleshoot issues.
* Discover insights to keep your applications healthy.





### **Reading 4.2: Introduction to Amazon CloudWatch**

###### **How CloudWatch Works**

The great thing about CloudWatch is that all you need to get started is an AWS account. It is a managed service, which enables you to focus on monitoring, without managing any underlying infrastructure.



The employee directory app is built with various AWS services working together as building blocks. It would be difficult to monitor all of these different services independently, so CloudWatch acts as one centralized place where metrics are gathered and analyzed. You already learned how EC2 instances post CPU utilization as a metric to CloudWatch. Different AWS resources post different metrics that you can monitor. You can view a list of services that send metrics to CloudWatch in the resources section of this unit.



Many AWS services send metrics automatically for free to CloudWatch at a rate of one data point per metric per 5-minute interval, without you needing to do anything to turn on that data collection. This by itself gives you visibility into your systems without you needing to spend any extra money to do so. This is known as basic monitoring. For many applications, basic monitoring does the job.



For applications running on EC2 instances, you can get more granularity by posting metrics every minute instead of every 5 minutes using a feature like detailed monitoring. Detailed monitoring has an extra fee associated. You can read about pricing on the CloudWatch Pricing Page linked in the resources section of this unit.



###### **Break Down Metrics**

Each metric in CloudWatch has a timestamp and is organized into containers called namespaces. Metrics in different namespaces are isolated from each other—you can think of them as belonging to different categories.



AWS services that send data to CloudWatch attach dimensions to each metric. A dimension is a name/value pair that is part of the metric’s identity. You can use dimensions to filter the results that CloudWatch returns. For example, you can get statistics for a specific EC2 instance by specifying the InstanceId dimension when you search.



###### **Set Up Custom Metrics**

Let’s say for your application you wanted to record the number of page views your website gets. How would you record this metric to CloudWatch? It’s an application-level metric, meaning that it’s not something the EC2 instance would post to CloudWatch by default. This is where custom metrics come in. Custom metrics allows you to publish your own metrics to CloudWatch.



If you want to gain more granular visibility, you can use high-resolution custom metrics, which enable you to collect custom metrics down to a 1-second resolution. This means you can send one data point per second per custom metric.



Other examples of custom metrics are:



* Web page load times
* Request error rates
* Number of processes or threads on your instance
* Amount of work performed by your application



Note: You can get started with custom metrics by programmatically sending the metric to CloudWatch using the PutMetricData API.



###### **Understand the CloudWatch Dashboards**

Once you’ve provisioned your AWS resources and they are sending metrics to CloudWatch, you can then visualize and review that data using the CloudWatch console with dashboards. Dashboards are customizable home pages that you use for data visualization for one or more metrics through the use of widgets, such as a graph or text.



You can build many custom dashboards, each one focusing on a distinct view of your environment. You can even pull data from different Regions into a single dashboard in order to create a global view of your architecture.



CloudWatch aggregates statistics according to the period of time that you specify when creating your graph or requesting your metrics. You can also choose whether your metric widgets display live data. Live data is data published within the last minute that has not been fully aggregated.



You are not bound to using CloudWatch exclusively for all your visualization needs. You can use external or custom tools to ingest and analyze CloudWatch metrics using the GetMetricData API.



As far as security goes, you can control who has access to view or manage your CloudWatch dashboards through AWS Identity and Access Management (IAM) policies that get associated with IAM users, IAM groups, or IAM roles.



###### **Get to Know CloudWatch Logs**

CloudWatch can also be the centralized place for logs to be stored and analyzed, using CloudWatch Logs. CloudWatch Logs can monitor, store, and access your log files from applications running on Amazon EC2 instances, AWS Lambda functions, and other sources.



CloudWatch Logs allows you to query and filter your log data. For example, let’s say you’re looking into an application logic error for your application, and you know that when this error occurs it will log the stack trace. Since you know it logs the error, you query your logs in CloudWatch Logs to find the stack trace. You also set up metric filters on logs, which turn log data into numerical CloudWatch metrics that you graph and use on your dashboards.



Some services are set up to send log data to CloudWatch Logs with minimal effort, like AWS Lambda. With AWS Lambda, all you need to do is give the Lambda function the correct IAM permissions to post logs to CloudWatch Logs. Other services require more configuration. For example, if you want to send your application logs from an EC2 instance into CloudWatch Logs, you need to first install and configure the CloudWatch Logs agent on the EC2 instance.



The CloudWatch Logs agent enables Amazon EC2 instances to automatically send log data to CloudWatch Logs. The agent includes the following components.



* A plug-in to the AWS Command Line Interface (CLI) that pushes log data to CloudWatch Logs.
* A script that initiates the process to push data to CloudWatch Logs.
* A cron job that ensures the daemon is always running.



After the agent is installed and configured, you can then view your application logs in CloudWatch Logs.



###### **Learn the CloudWatch Logs Terminology**

Log data sent to CloudWatch Logs can come from different sources, so it’s important you understand how they’re organized and the terminology used to describe your logs.



1. Log event: A log event is a record of activity recorded by the application or resource being monitored, and it has a timestamp and an event message.
2. Log stream: Log events are then grouped into log streams, which are sequences of log events that all belong to the same resource being monitored. For example, logs for an EC2 instance are grouped together into a log stream that you can then filter or query for insights.
3. Log groups: Log streams are then organized into log groups. A log group is composed of log streams that all share the same retention and permissions settings. For example, if you have multiple EC2 instances hosting your application and you are sending application log data to CloudWatch Logs, you can group the log streams from each instance into one log group. This helps keep your logs organized.



###### **Configure a CloudWatch Alarm**

You can create CloudWatch alarms to automatically initiate actions based on sustained state changes of your metrics. You configure when alarms are triggered and the action that is performed.



**You first need to decide what metric you want to set up an alarm for, then you define the threshold at which you want the alarm to trigger. Next, you define the specified time period(amount of time) of which the metric should(would) cross the threshold for the alarm to be triggered.**



For example, if you wanted to set up an alarm for an EC2 instance to trigger when the CPU utilization goes over a threshold of 80%, you also need to specify the time period the CPU utilization is over the threshold. You don’t want to trigger an alarm based on short temporary spikes in the CPU. You only want to trigger an alarm if the CPU is elevated for a sustained amount of time, for example if it is over 80% for 5 minutes or longer, when there is a potential resource issue.



Keeping all that in mind, **to set up an alarm you need to choose:**

1. the metric
2. the threshold
3. the time period



An alarm has three possible states.



* OK: The metric is within the defined threshold. Everything appears to be operating like normal.



* ALARM: The metric is outside of the defined threshold. This could be an operational issue.



* INSUFFICIENT\_DATA: The alarm has just started, the metric is not available, or not enough data is available for the metric to determine the alarm state.



An alarm can be triggered when it transitions from one state to another. Once an alarm is triggered, it can initiate an action.

Actions can be:

1. an Amazon EC2 action
2. an Auto Scaling action
3. a notification sent to Amazon Simple Notification Service (SNS).



Use CloudWatch Alarms to Prevent and Troubleshoot Issues

CloudWatch Logs uses metric filters to turn the log data into metrics that you can graph or set an alarm on. For the employee directory application, let’s say you set up a metric filter for 500-error response codes.



Then, you define an alarm for that metric that will go into the ALARM state if 500-error responses go over a certain amount for a sustained time period. Let’s say if it’s more than five 500-error responses per hour, the alarm should enter the ALARM state. Next, you define an action that you want to take place when the alarm is triggered.



In this case, it makes sense to send an email or text alert to you so you can start troubleshooting the website, hopefully fixing it before it becomes a bigger issue. Once the alarm is set up, you feel comfortable knowing that if the error happens again, you’ll be notified promptly.



You can set up different alarms for different reasons to help you prevent or troubleshoot operational issues. In the scenario just described, the alarm triggered an SNS notification that went to a person who looked into the issue manually. Another option is to have alarms trigger actions that automatically remediate technical issues.



For example, you can set up an alarm to trigger an EC2 instance to reboot, or scale services up or down. You can even set up an alarm to trigger an SNS notification, which then triggers an AWS Lambda function. The Lambda function then calls any AWS API to manage your resources, and troubleshoot operational issues. By using AWS services together like this, you respond to events more quickly.







### **Reading 4.3: Optimizing Solutions on AWS**

###### **What Is Availability?**

The availability of a system is typically expressed as a percentage of uptime in a given year or as a number of nines. Below, you can see a list of the percentages of availability based on the downtime per year, as well as its notation in nines.



**Availability (%)	:	Downtime (per year)**



90% ("one nine")	:	36.53 days



99% ("two nines")	:	3.65 days



99.9% ("three nines")	:	8.77 hours



99.95% ("three and a half nines"): 4.38 hours



99.99% ("four nines")	:	52.60 minutes



99.995% ("four and a half nines"): 26.30 minutes



99.999% ("five nines")	:	5.26 minutes



To increase availability, you need redundancy. This typically means more infrastructure: more data centers, more servers, more databases, and more replication of data. You can imagine that adding more of this infrastructure means a higher cost. Customers want the application to always be available, but you need to draw a line where adding redundancy is no longer viable in terms of revenue.



###### **Improve Application Availability**

In the current application, there is only one EC2 instance used to host the application, the photos are served from Amazon Simple Storage Service (S3) and the structured data is stored in Amazon DynamoDB. That single EC2 instance is a single point of failure for the application. Even if the database and S3 are highly available, customers have no way to connect if the single instance becomes unavailable. One way to solve this single point of failure issue is by adding one more server.



**Use a Second Availability Zone**

The physical location of that server is important. On top of having software issues at the operating system or application level, there can be a hardware issue. It could be in the physical server, the rack, the data center or even the Availability Zone hosting the virtual machine. An easy way to fix the physical location issue is by deploying a second EC2 instance in a different Availability Zone. That would also solve issues with the operating system and the application. However, having more than one instance brings new challenges.



**Manage Replication, Redirection, and High Availability**

1. Create a Process for Replication: The first challenge is that you need to create a process to replicate the configuration files, software patches, and application itself across instances. The best method is to automate where you can.
2. Address Customer Redirection: The second challenge is how to let the clients, the computers sending requests to your server, know about the different servers. There are different tools that can be used here. The most common is using a **Domain Name System (DNS)** where the client uses one record which points to the IP address of all available servers. However, the time it takes to update that list of IP addresses and for the clients to become aware of such change, sometimes called **propagation**, is typically the reason why this method isn’t always used.



   Another option is to use a **load balancer** which takes care of health checks and distributing the load across each server. Being between the client and the server, the load balancer avoids propagation time issues. We discuss load balancers later.

   

1. Understand the Types of High Availability: The last challenge to address when having more than one server is the type of availability you need—either be an active-passive or an active-active system.

   

   Active-Passive: With an active-passive system, only one of the two instances is available at a time. One advantage of this method is that for stateful applications where data about the client’s session is stored on the server, there won’t be any issues as the customers are always sent to the same server where their session is stored.

   

   Active-Active: A disadvantage of active-passive and where an active-active system shines is scalability. By having both servers available, the second server can take some load for the application, thus allowing the entire system to take more load. However, if the application is stateful, there would be an issue if the customer’s session isn’t available on both servers. Stateless applications work better for active-active systems.

   

   

   **Stateful**: storing client session on the server

   **Stateless**: Not storing any client session on the server

   

   ### **Reading 4.4: Route Traffic with Amazon Elastic Load Balancing**

   ###### **WHAT’S A LOAD BALANCER?**

   Load balancing refers to the process of distributing tasks across a set of resources. In the case of the corporate directory application, the resources are EC2 instances that host the application, and the tasks are the different requests being sent. It’s time to distribute the requests across all the servers hosting the application using a load balancer.

   

   To do this, you first need to enable the load balancer to take all of the traffic and redirect it to the backend servers based on an algorithm. The most popular algorithm is round-robin, which sends the traffic to each server one after the other.

   

   A typical request for the application would start from the browser of the client. It’s sent to a load balancer. Then, it’s sent to one of the EC2 instances that hosts the application. The return traffic would go back through the load balancer and back to the client browser. Thus, the load balancer is directly in the path of the traffic.

   

   Although it is possible to install your own software load balancing solution on EC2 instances, AWS provides a service for that called **Elastic Load Balancing (ELB)**.

   

   ###### **FEATURES OF ELB**

   The ELB service provides a major advantage over using your own solution to do load balancing, in that you don’t need to manage or operate it. It can distribute incoming application traffic across EC2 instances as well as containers, IP addresses, and AWS Lambda functions.

   

   The fact that ELB can load balance to IP addresses means that it can work in a hybrid mode as well, where it also load balances to on-premises servers.

   

   ELB is highly available. The only option you have to ensure is that the load balancer is deployed across multiple Availability Zones.

   

   In terms of scalability, ELB automatically scales to meet the demand of the incoming traffic. It handles the incoming traffic and sends it to your backend application.

   

   ###### **HEALTH CHECKS**

   Taking the time to define an appropriate health check is critical. Only verifying that the port of an application is open doesn’t mean that the application is working. It also doesn’t mean that simply making a call to the home page of an application is the right way either.

   

   For example, the employee directory application depends on a database, and S3. The health check should validate all of those elements. One way to do that would be to create a monitoring webpage like “/monitor” that will make a call to the database to ensure it can connect and get data, and make a call to S3. Then, you point the health check on the load balancer to the “/monitor” page.

   

   After determining the availability of a new EC2 instance, the load balancer starts sending traffic to it. If ELB determines that an EC2 instance is no longer working, it stops sending traffic to it and lets EC2 Auto Scaling know. EC2 Auto Scaling’s responsibility is to remove it from the group and replace it with a new EC2 instance. Traffic only sends to the new instance if it passes the health check.

   

   In the case of a scale down action that EC2 Auto Scaling needs to take due to a scaling policy, it lets ELB know that EC2 instances will be terminated. ELB can prevent EC2 Auto Scaling from terminating the EC2 instance until all connections to that instance end, while preventing any new connections. That feature is called **connection draining**.

   

   ###### **ELB COMPONENTS**

   The ELB service is made up of three main components.

   

1. Listeners: The client connects to the listener. This is often referred to as client-side. To define a listener, a port must be provided as well as the protocol, depending on the load balancer type. There can be many listeners for a single load balancer.
2. Target groups: The backend servers, or server-side, is defined in one or more target groups. This is where you define the type of backend you want to direct traffic to, such as EC2 Instances, AWS Lambda functions, or IP addresses. Also, a health check needs to be defined for each target group.
3. Rules: To associate a target group to a listener, a rule must be used. Rules are made up of a condition that can be the source IP address of the client and a condition to decide which target group to send the traffic to.

   

   ###### **APPLICATION LOAD BALANCER (ALB)**

   Here are some primary features of Application Load Balancer (ALB).

   

* ALB routes traffic based on request data. It makes routing decisions based on the HTTP protocol like the URL path (/upload) and host, HTTP headers and method, as well as the source IP address of the client. This enables granular routing to the target groups.

  

* Send responses directly to the client. ALB has the ability to reply directly to the client with a fixed response like a custom HTML page. It also has the ability to send a redirect to the client which is useful when you need to redirect to a specific website or to redirect the request from HTTP to HTTPS, removing that work from your backend servers.

  

* ALB supports TLS offloading. Speaking of HTTPS and saving work from backend servers, ALB understands HTTPS traffic. To be able to pass HTTPS traffic through ALB, an SSL certificate is provided by either importing a certificate via Identity and Access Management (IAM) or AWS Certificate Manager (ACM) services, or by creating one for free using ACM. This ensures the traffic between the client and ALB is encrypted.

  

* Authenticate users. On the topic of security, ALB has the ability to authenticate the users before they are allowed to pass through the load balancer. ALB uses the OpenID Connect protocol and integrates with other AWS services to support more protocols like SAML, LDAP, Microsoft AD, and more.

  

* Secure traffic. To prevent traffic from reaching the load balancer, you configure a security group to specify the supported IP address ranges.

  

* ALB uses the **round-robin routing algorithm**. ALB ensures each server receives the same number of requests in general. This type of routing works for most applications.

  

* ALB uses the **least outstanding request routing algorithm**. If the requests to the backend vary in complexity where one request may need a lot more CPU time than another, then the least outstanding request algorithm is more appropriate. It’s also the right routing algorithm to use if the targets vary in processing capabilities. **An outstanding request is when a request is sent to the backend server and a response hasn’t been received yet.**

  

  For example, if the EC2 instances in a target group aren’t the same size, one server’s CPU utilization will be higher than the other if the same number of requests are sent to each server using the round-robin routing algorithm. That same server will have more outstanding requests as well. Using the least outstanding request routing algorithm would ensure an equal usage across targets.

  

* ALB has sticky sessions. In the case where requests need to be sent to the same backend server because the application is stateful, then use the sticky session feature. This feature uses an HTTP cookie to remember across connections which server to send the traffic to.

  

  **Finally, ALB is specifically for HTTP and HTTPS traffic. If your application uses a different protocol, then consider the Network Load Balancer (NLB).**

  

  ###### **NETWORK LOAD BALANCER**

  Here are some primary features of Network Load Balancer (NLB).Network Load Balancer supports TCP, UDP, and TLS protocols. HTTPS uses TCP and TLS as protocol. However, NLB operates at the connection layer, so it doesn’t understand what a HTTPS request is. That means all features discussed above that are required to understand the HTTP and HTTPS protocol, like routing rules based on that protocol, authentication, and least outstanding request routing algorithm, are not available with NLB.

  

  NLB uses a **flow hash routing algorithm**. The algorithm is based on:

  

* The protocol
* The source IP address and source port
* The destination IP address and destination port
* The TCP sequence number

  

  If all of these parameters are the same, then the packets are sent to the exact same target. If any of them are different in the next packets, then the request may be sent to a different target.

  

* NLB has sticky sessions. Different from ALB, these sessions are based on the source IP address of the client instead of a cookie.

  

* NLB supports TLS offloading. NLB understands the TLS protocol. It can also offload TLS from the backend servers similar to how ALB works.

  

* NLB handles millions of requests per second. While ALB can also support this number of requests, it needs to scale to reach that number. This takes time. NLB can instantly handle this amount of requests.

  

* NLB supports static and elastic IP addresses. There are some situations where the application client needs to send requests directly to the load balancer IP address instead of using DNS. For example, this is useful if your application can’t use DNS or if the connecting clients require firewall rules based on IP addresses. In this case, NLB is the right type of load balancer to use.

  

* NLB preserves source IP address. NLB preserves the source IP address of the client when sending the traffic to the backend. With ALB, if you look at the source IP address of the requests, you will find the IP address of the load balancer. While with NLB, you would see the real IP address of the client, which is required by the backend application in some cases.

  

  ###### **SELECT BETWEEN ELB TYPES**

  Selecting between the ELB service types is done by determining which feature is required for your application. Below you can find a list of the major features that you learned in this unit and the previous.

  

  **Feature		:	Application Load Balancer(ALB)	:	Network Load Balancer(NLB)**

  

  Protocols	:	HTTP, HTTPS			:	TCP, UDP, TLS

  

  Connection draining (deregistration delay): ✔		:

  

  IP addresses as targets: ✔				:	✔

  

  Static IP and Elastic IP address:			:	✔

  

  Preserve Source IP address:				:	✔

  

  Routing based on Source IP address, path, host, HTTP headers, HTTP method, and query string: ✔	:

  

  Redirects	:	✔				:

  

  Fixed response	:	✔				:

  

  User authentication:	✔				:

  

  

  ### **Reading 4.5: Amazon EC2 Auto Scaling**

  Availability and reachability is improved by adding one more server. However, the entire system can again become unavailable if there is a capacity issue. Let’s look at that load issue with both types of systems we discussed, active-passive and active-active.

  

  ###### **Vertical Scaling**

  If there are too many requests sent to a single active-passive system, the active server will become unavailable and hopefully failover to the passive server. But this doesn’t solve anything. With active-passive, you need vertical scaling. This means increasing the size of the server. With EC2 instances, you select either a larger type or a different instance type. This can only be done while the instance is in a stopped state. In this scenario, the following steps occur:

  

* Stop the passive instance. This doesn’t impact the application since it’s not taking any traffic.

  

* Change the instance size or type, then start the instance again.

  

* Shift the traffic to the passive instance, turning it active.

  

* The last step is to stop, change the size, and start the previous active instance as both instances should match.

  

  When the amount of requests reduces, the same operation needs to be done. Even though there aren’t that many steps involved, it’s actually a lot of manual work to do. Another disadvantage is that a server can only scale vertically up to a certain limit.

  

  Once that limit is reached, the only option is to create another active-passive system and split the requests and functionalities across them. This could require massive application rewriting. This is where the active-active system can help. When there are too many requests, this system can be scaled horizontally by adding more servers.

  

  ###### **Horizontal Scaling**

  As mentioned above, for the application to work in an active-active system, it’s already created as stateless, not storing any client session on the server. This means that having two servers or having four wouldn’t require any application changes. It would only be a matter of creating more instances when required and shutting them down when the traffic decreases.

  

  The Amazon EC2 Auto Scaling service can take care of that task by automatically creating and removing EC2 instances based on metrics from Amazon CloudWatch.

  

  You can see that there are many more advantages to using an active-active system in comparison with an active-passive. Modifying your application to become **stateless enables scalability**.

  

  ###### **Integrate ELB with EC2 Auto Scaling**

  The ELB service integrates seamlessly with EC2 Auto Scaling. As soon as a new EC2 instance is added to or removed from the EC2 Auto Scaling group, ELB is notified. However, before it can send traffic to a new EC2 instance, it needs to validate that the application running on that EC2 instance is available.

  

  This validation is done via the health checks feature of ELB. Monitoring is an important part of load balancers, as it should route traffic to only healthy EC2 instances. That’s why **ELB supports two types of health checks**.

  

1. Establishing a connection to a backend EC2 instance using TCP, and marking the instance as available if that connection is successful.

   

   2\. Making an HTTP or HTTPS request to a webpage that you specify, and validating that an HTTP response code is returned.

   

   

   ###### **Differentiate Between Traditional Scaling and Auto Scaling**

   With a traditional approach to scaling, you buy and provision enough servers to handle traffic at its peak. However, this means that at night time, there is more capacity than traffic. This also means you’re wasting money. Turning off those servers at night or at times where the traffic is lower only saves on electricity.

   

   The cloud works differently, with a pay-as-you-go model. It’s important to turn off the unused services, especially EC2 instances that you pay for On-Demand. One could manually add and remove servers at a predicted time. But with unusual spikes in traffic, this solution leads to a waste of resources with over-provisioning or with a loss of customers due to under-provisioning.

   

   The need here is for a tool that automatically adds and removes EC2 instances according to conditions you define—that’s exactly what the EC2 Auto Scaling service does.

   

   ###### **Use Amazon EC2 Auto Scaling**

   The EC2 Auto Scaling service works to add or remove capacity to keep a steady and predictable performance at the lowest possible cost. By adjusting the capacity to exactly what your application uses, you only pay for what your application needs. And even with applications that have steady usage, EC2 Auto Scaling can help with fleet management. If there is an issue with an EC2 instance, EC2 Auto Scaling can automatically replace that instance. This means that EC2 Auto Scaling helps both to scale your infrastructure and ensure high availability.

   

   ###### **Configure EC2 Auto Scaling Components**

   There are three main components to EC2 Auto Scaling.

   

1. Launch template or configuration: What resource should be automatically scaled?
2. EC2 Auto Scaling Group: Where should the resources be deployed?
3. Scaling policies: When should the resources be added or removed?

   

   ###### **Learn About Launch Templates**

   There are multiple parameters required to create EC2 instances: Amazon Machine Image (AMI) ID, instance type, security group, additional Amazon Elastic Block Store (EBS) volumes, and more. All this information is also required by EC2 Auto Scaling to create the EC2 instance on your behalf when there is a need to scale. This information is stored in a launch template.

   

   You can use a launch template to manually launch an EC2 instance. You can also use it with EC2 Auto Scaling. It also supports versioning, which allows for quickly rolling back if there was an issue or to specify a default version of your launch template. This way, while iterating on a new version, other users can continue launching EC2 instances using the default version until you make the necessary changes.

   

   

   **You can create a launch template one of three ways.**

   

1. The fastest way to create a template is to use an existing EC2 instance. All the settings are already defined.
2. Another option is to create one from an already existing template or a previous version of a launch template.
3. The last option is to create a template from scratch. The following options will need to be defined: **AMI ID, instance type, key pair, security group, storage, and resource tags.**

   

   Note: Another way to define what Amazon EC2 Auto Scaling needs to scale is by using a launch configuration. It’s similar to the launch template, but it doesn’t allow for versioning using a previously created launch configuration as a template. Nor does it allow for creating one from an already existing EC2 instance. For these reasons and to ensure that you’re getting the latest features from Amazon EC2, use a launch template instead of launch configuration.

   

   ###### **Get to Know EC2 Auto Scaling Groups**

   The next component that EC2 Auto Scaling needs is an EC2 Auto Scaling Group (ASG). An ASG enables you to define where EC2 Auto Scaling deploys your resources. This is where you specify the Amazon Virtual Private Cloud (VPC) and subnets the EC2 instance should be launched in.

   

   EC2 Auto Scaling takes care of creating the EC2 instances across the subnets, so it’s important to select at least two subnets that are across different Availability Zones.

   

   ASGs also allow you to specify the type of purchase for the EC2 instances. You can use On-Demand only, Spot only, or a combination of the two, which allows you to take advantage of Spot instances with minimal administrative overhead.

   

   To specify how many instances EC2 Auto Scaling should launch, there are three capacity settings to configure for the group size.

   

1. Minimum: The minimum number of instances running in your ASG even if the threshold for lowering the amount of instances is reached.
2. Maximum: The maximum number of instances running in your ASG even if the threshold for adding new instances is reached.
3. Desired capacity: The amount of instances that should be in your ASG. This number can only be within or equal to the minimum or maximum. EC2 Auto Scaling automatically adds or removes instances to match the desired capacity number.

   

   When EC2 Auto Scaling removes EC2 instances because the traffic is minimal, it keeps removing EC2 instances until it reaches a minimum capacity. Depending on your application, using a minimum of two is a good idea to ensure high availability, but you know how many EC2 instances at a bare minimum your application requires at all times. When reaching that limit, even if EC2 Auto Scaling is instructed to remove an instance, it does not, to ensure the minimum is kept.

   

   On the other hand, when the traffic keeps growing, EC2 Auto Scaling keeps adding EC2 instances. This means the cost for your application will also keep growing. That’s why it’s important to set a maximum amount to make sure it doesn’t go above your budget.

   

   The desired capacity is the amount of EC2 instances that EC2 Auto Scaling creates at the time the group is created. If that number decreases, then EC2 Auto Scaling removes the oldest instance by default. If that number increases, then EC2 Auto Scaling creates new instances using the launch template.

   

   ###### **Ensure Availability with EC2 Auto Scaling**

   

   Using different numbers for minimum, maximum, and desired capacity is used for dynamically adjusting the capacity. However, if you prefer to use EC2 Auto Scaling for fleet management, you can configure the three settings to the same number, for example four. EC2 Auto Scaling will ensure that if an EC2 instance becomes unhealthy, it replaces it to always ensure that four EC2 instances are available. This ensures high availability for your applications.

   

   ###### **Enable Automation with Scaling Policies**

   By default, an ASG will be kept to its initial desired capacity. Although it’s possible to manually change the desired capacity, you can also use scaling policies.

   

   In the AWS Monitoring module, you learned about Amazon CloudWatch metrics and alarms. You use metrics to keep information about different attributes of your EC2 instance like the CPU percentage. You use alarms to specify an action when a threshold is reached. Metrics and alarms are what scaling policies use to know when to act. For example, you set up an alarm that says when the CPU utilization is above 70% across the entire fleet of EC2 instances, trigger a scaling policy to add an EC2 instance.

   

   There are three types of scaling policies:

4. simple scaling
5. step scaling
6. target tracking scaling

   

   ###### **Simple Scaling Policy**

   A simple scaling policy allows you to do exactly what’s described above. You use a CloudWatch alarm and specify what to do when it is triggered. This can be a number of EC2 instances to add or remove, or a specific number to set the desired capacity to. You can specify a percentage of the group instead of using an amount of EC2 instances, which makes the group grow or shrink more quickly.

   

   Once this scaling policy is triggered, it waits a cooldown period before taking any other action. This is important as it takes time for the EC2 instances to start and the CloudWatch alarm may still be triggered while the EC2 instance is booting. For example, you could decide to add an EC2 instance if the CPU utilization across all instances is above 65%. You don’t want to add more instances until that new EC2 instance is accepting traffic.

   

   However, what if the CPU utilization was now above 85% across the ASG? Only adding one instance may not be the right move here. Instead, you may want to add another step in your scaling policy. Unfortunately, a simple scaling policy can’t help with that.

   

   ###### **Step Scaling Policy**

   This is where a step scaling policy helps. Step scaling policies respond to additional alarms even while a scaling activity or health check replacement is in progress. Similar to the example above, you decide to add two more instances in case the CPU utilization is at 85%, and four more instances when it’s at 95%.

   

   Deciding when to add and remove instances based on CloudWatch alarms may seem like a difficult task. This is why the third type of scaling policy exists: target tracking.

   

   ###### **Target Tracking Scaling Policy**

   If your application scales based on average CPU utilization, average network utilization (in or out), or based on request count, then this scaling policy type is the one to use. All you need to provide is the target value to track and it automatically creates the required CloudWatch alarms.

   

   

   #### **Self Graded Project:**

   As part of this assignment, you will create a high-level architecture diagram that uses

    AWS service icons and arrows

    to depict an AWS solution for the given scenario. Create your diagram by using a tool like

    diagrams.net

   , or you can select a different tool by from the

    AWS Architecture Icons

    page by scrolling to the Drawing and diagramming tools section.

   

   Scenario: You have a web application that accepts requests from the internet. Clients can send requests to query for data. When a request comes in, the web application queries a MySQL database and returns the data to the client.

   

   Instructions: Design a three-tier architecture that follows AWS best practices by using services such as Amazon Virtual Private Cloud (Amazon VPC), Amazon Elastic Compute Cloud (Amazon EC2), Amazon Relational Database Service (Amazon RDS) with high availability, and Elastic Load Balancing (ELB). Create an architecture diagram that lays out your design, including the networking layer, compute layer, database layer, and anything else that’s needed to accurately depict the architecture. Write a few paragraphs that explain why you chose the AWS services that you used and how they would support the solution for the given scenario. Your explanation must describe how traffic flows through the different AWS components—from the client to the backend database, and back to the client.

   

   

   Amazon Q Capabilities:

7. Generate code
8. Troubleshooting
9. AWS question and answer
10. Business specific applications
11. Multi-step project planning

    

    Amazon Q Business:

12. Question and answer
13. Knowledge discovery
14. Writing emails and documents
15. Summarizing text
16. Crafting documents
17. Brainstorming ideas

    

    Custom plugins:

18. Connect Amazon Q applications to third-party applications
19. Query data or take actions

    

    IDE-style completions for command line interfaces:

* git
* npm
* docker
* aws
