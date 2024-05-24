Three tools used to manage AWS resources
- Management console
- Software Development Kits
- Command Line Interface
<u>Access keys</u> - used to login as a user from outside of the AWS console
<u>Compute workloads</u>:
- EC2 - flagship AWS compute service that allows tyou to launch virtual machines called instances
	- Instances (VMs) are an emulation of a physical computer using software, multiple of these instances can run on the same physical server, allowing the economies of scale principle to come into play
	- AMI's are the templates for creating EC2 instances (RAM, processor core, network bandwidth, OS)
	- Instance types:
		- General purpose - balanced
		- Compute optimized - high processing power
		- Memory optimized - large data sets in memory
		- Accelerated optimized - ML
		- Storage optimized - High read/write access to large data sets on local storage
	- Tenancy is what allows for cost savings between customers:
		- Shared - multiple AWS accounts are using the same physical hardware
		- Dedicated instance - instance runs on single-tenant hardware
		- Dedicated host - Instance runs on its own physical server that you can control and configure
	- Pricing Models
		- On-Demand - pay as you go, pay only for what is used, hourly rate
		- Reserved Instances - commit for 1 or 3 years of usage, can be standard or convertible, can be shared between accounts
		- Spot Instances - unused compute capacity that can be bought from AWS with 90% savings, designed for workloads that have flexible start and end times because, AWS can take back spot computing capacity at any time if it is needed by other on-demand customers
- Auto scaling groups and Load balancers - these two services together are what allows you to achieve high elasticity and scalability for compute workloads
	- Auto Scaling Groups - responsible for automatically adding or removiing  instances to meet performance requirements
	- Elastic Load Balancers - distribute traffic between instances to achieve best possible latency
		- Application Load Balancer - used for distributing traffic from the web to targets (EC2, containers, etc) in your network
		- Network Load Balancer - used to handle millions of requests per second
- VM's and Containers - utilize software to simulate using an actual server (lightsail) and containers have everything an application needs to run on a server (elastic container service for docker, ECS Fargate more hands-off container management service, and Elastic Kubernetes Service more hands-on container management service that utilizes kubernetes)
- Serverless - refers to an absence of physical, dedicated servers. in other words, your programs and workloads aren't tied to a specific server.
	- AWS Lambda is the primary serverless compute tool. Run code without provisioning servers.
	- AWS Elastic Beanstalk is a fully managed service to allow you to deploy serverless web applications.
- Storage is different from databases in that with storage, you have more flexibility on how data you sotre is formatted
	- Elastic Block Storage - most compatible with EC2 instances and utilizes block storage
		- Most useful for EC2 instances as it can be directly accessed by the OS of the instance
		- Can be attached to multiple instances but only one at a time
		- SSD based and HDD based
	- Elastic File Storage - file storage is useful when multiple users need access to the same drive
		- Automatically grows or shrinks based on usage
		- Commonly mounted on EC2 instances but an also be mounted on AWS containers or Lambda functions
		- Storage classes:
			- Standard
			- Standard IA
			- One zone
			- One zone IA
	- Simple Storage Service (S3) - object key-value pair storage, most widely used AWS service
		- S3 standard - most expensive 99.99% availability, replicates across 3 Az's, Fast retrieval
		- S3 Intelligent tiering - uses ML to move objects to most appropriate storage class
		- S3 Standard-IA (Infrequent Access) - best used for objects being retrieved less than once a month, cheaper, still fast data retrieval
		- S3 one zone IA - same as abovve but only lives in one AZ
		- S3 Glacier - Long term storage ideal for archves. Very cheap nut data retrieval takes minutes to hours
		- S3 Glacier Deep Archive - cheaper and slower than the above
	- AWS Snow Family - Used to migrate data in or out of AWS cloud
		- AWS Snowcone - supports 8TB of storage for HDD, 14TB for SSD
		- AWS Snowball - storage optimized (80TB HDD) compute optimized (28TB SSD)
		- AWS Snowmobile - A literal semi truck of storage with 100PB+ of storage
<u>Databases</u> - stores semi structured and structured data. This is the primary difference between database and storage, as storage is a lot more flexible in the data structure it accepts. Used to structure data so that it is easier to query
RDBS:
- AWS Relational Database Service - support for most common SQL based databases such as MySQL, MariaDB, PostgreSQL, Oracle, and Microsoft SQL server
- Amazon Aurora - Fully managed RDBS service, highly available, can be serverless
Non-RDBS:
- DynamoDB - Primary noSQL database from AWS, designed for speed and availability
- DocumentDB - NoSQL document database, used for MongoDB
Other Database Services:
- Redshift - data warehouse solution, designed to store data in a manner similar to SQL and run extremely large and complex queries. Used for Online Analytical Processing
- Elasticache - based off of memcached, in memory data store designed to cache data for quicker access for end users
- Database Migration Service - On-premise database to AWS, from two databases in different or same AWS accounts, from SQL to NoSQL
