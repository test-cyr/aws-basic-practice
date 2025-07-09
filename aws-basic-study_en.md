# aws-basic-practice
AWS Basic Study

## Cloud Computing
* cloud : Utility-style usage
- IT resource are provided over the Internet on-demand, and you pay only what you use
* on-demane : Responds to demand
- Applies investment cost model
- Can be used immediately
- No need for physical infrastructure
- Flexible usage
- Pay-as-you-go : OnDemand
* Advantage : Replaces large upfront cost with variable costs based on usage

## Cloud Computing Models
- Software as a Service (Public Cloud )
- Infrastructure as Service (Hybrid Cloud )
- Platform as a Service (On-premise -> deprecated model )

## Application Configuration
- OS : Window / Linux
- Computing : CPU + RAM
- Storage : HDD / SDD

* laaS : Infrastructure as a Service
  - Provides only the infrastructure
  - Users must install their own OS and develop or install the necessary software
  - Simialr to renting a virtual computer
ex) AWS EC2
    Receipe, cooking ingredients, kitchen (users prepares recipe, ingredients, etc)
    * laaS is think of it like renting a kitchen

* PaaS : Platform as a Service
  - Provides infrastructure + OS + runtime (other necessary components to run a program)
  - Configured so you can upload your code and run it right away
  ex) Firebase, Google App Engine etc
      * Provides kitchen, ingredients
       user only needs to prepare the recipe (i.e, code)

 * SaaS : Software as a Service : Provides infrastructure + OS + necessary software
   - APP : Service is provided
   - OS : Ready-to-use services without any setup
   - computing
   - storage
   - network
- Accessible without any installation

## Cloud Computing Deployment Models
- Public Cloud
  - All components run in the cloud
  - Low cost
  - High scalability

- Hybrid Cloud
  - A combination of public and private cloud environments
  - Used in the process of converting from private to public cloud
  - Or used as a backup for the private cloud
 
- Private Cloud (operated directly)
  - High level of customization possible
  - Expensive initial setup cost
  - High maintenance cost
  - High security
 
## AWS Architecture
- Region : The physical location where AWS services are provided
           Each region has a unique code
           Available services vary by region
- ARN : A unique ID for AWS resources
- Availability Zone (AZ) : A subdivision of a region
                          Each region consists of at least two AZs
                          An AZ is made up of one or more data centers
                          Regions are interconnected through high-speed dedicated networks
                          They are physically separated at a certain distance
 * Services that store data belong to a region-based service
- Edge Location : Temporary data storage location (point of presence)
                  AWS CloudFront (CDN), ensuring fast and reliable content distribution to end users
- Global Services : Services and data that are accessible across all AWS regions
                 ex) CloudFront, IAM, Route53, WAF
- Regional Services : Provide data and services based on a specific region
               ex) Most services, S3(file storage service)

## IAM
* Global Service : Once created, it applies to all of AWS
- User / Group / Policy / Role
- access control
- Granting and denying access
- Provides authentication credentials for service usage
- Manages user creation, account security, and password policies
- Password policy management
- Enable resource sharing between different AWS accounts

* Root User : Has full administrative access to the AWS account, including billing management
              Recommended to use only for administrative purpose, not for everyday tasks
              Account recovery is very difficult if compromised -> MFA is strongly advised
              MFA (Multi-factor authentication) : Generates one-time passwords for enhanced security
* IAM User : A user created and managed through AWS IAM
             Represents an individual person or an application
             Can be granted console login permissions
             Can be authorized to access AWS ervices based on assigned permissions
* Access Key (user name)
* Secret Access Key (password) 

## JSON
- Java Script Object Notation
- Commonly used for exchanging data between different programs and systems
- Supported natively by many programming languages or through plugins
- Structured as key - value pairs

## Virtualization
- Dividing a single physical computer into multiple virtual computers

Operating system(OS) : Manages hardware and software resources of the system
                       ex) Windows, Linux ...
Privileged Instructions : Commands that communicate directly with system components - only the OS can excute these
                          Typically, only one OS runs per physical hardware system

## HVM (Hardware virtual Machine)
- Third-generation virtualization technology
- Virtualization supported directly by hardware
- Guest OS communicates directly with hardware, enabling near bare-metal performance and high speed (near bare-metal)

## EC2 (Elastic Compare Cloud)
- A service that lets you rent virtual computers
- A web service that provides secure and scalable computing power in the cloud
* Essentially, a service for renting computing resources

. EC2 Features
 - On-demand pricing billed by the second
 - Fast deployment speed and high scalability
 - Supports a wide range of configurations
 - Integrates seamlessly with various AWS services

## EC2 구성
- Instance : - Instance : A virtual server in the cloud responsible for CPU, memory, GPU, and other computing resources
- EBS : Elastic Block Storage, Virtual hard disk used by EC2 instances in the cloud
- AMI(Amazon Machine Image) : An image containing information required to launch an EC2 instance
- Security Group : A virtual firewall that controls inbound and outbound traffic

. On-Demand : Pay only for what you use

.  EC2 Instance : Represents a single virtual computer
                 ex) if you need 5 computers, you create 5 instances

. EC2 : Functions as an independent computer
        Supports Linux, Window operating system
        Commonly use as web servers or application servers

. S3 (Simple Storage Service)
 - Object storage service (file server)
 - Virtually unlimited data storage capacity
 - Amazon infrastructure handles all scaling
 - Supports storing individual files ranging from 1byte to 5TB

. RDS (Relational Database Service)
 - Managed relational databases (MSSQL, NySQL, Oracle)
 - Automated backups and replication handled by Amazon infrastructure

. ELB (Elastic Loab Balancing)
 - Distributes incoming traffic across multiple EC2 instances
 - Automatically detects and excludes unhealthy EC2 instances
 - Works with Auto Scaling to automatically launch or terminate EC2 instances based on demand
