What is AWS responsible for:
- Hardware/Global infrastructure
- Software for compute, storage, database, networking services
What is the customer responsible for:
- Securing data via client/server-side encryption
- Configuration of Virtual Infrastructure and systems
- Configuration of managed services or 3rd party applications![[Pasted image 20240521203548.png]]
Benefits of using the cloud:
- Agility
- Pay as you go pricing - trade captial expenses for operating expenses
- Economies of scale - there are millions of customer you are sharing the costs with
- Global reach
- Security
- Reliability
- Availability
- Scalability
- Elasticity
Advantages with using AWS
- Trade CapEx for variable expense
- Benefit from massive economies of scale
- Stop guessing capacities
- Increase speed and agility
- Stop spending more money on data centers
- Go global in minutes
AWS Well-Architected framework
- Operational Excellence - run and monitor systems
	- Perform operations as code which will limit errors, enable automation
	- Make small, frequent, reversible changes so that the whole application is not overhauled in a couple changes. 
	- Anticipate failure by writing test code to break your architecture so you can test recovery
	- Refine operational procedures frequently by drawing on past events to be able to improve the application
- Security - protect data and systems
	- Implement a strong identity foundation and a principle of least privilege implementation
	- Enable traceability
	- Automate security
	- Protect data in transit and at rest by using SSL/TLS and server/client-side encryption
	- Keep people away from data
	- Anticipate security events to automate recovery
- Reliability - Mitigate and recover
	- Automatically recover from failure
	- Test recovery procedures
	- Scale horizontally to increase availability
	- Make change with code
- Performance Efficiency - Use resources effectively
	- Take advantage of resources specialized for particular use cases and experiment
	- Deploying workloads to multiple AWS regions allows you to provide lower latency and a better customer experience
	- Utilize serverless architecture to remove the need to use time and money running and maintaining physical, dedicated servers
- Cost Optimizations - 
	- Dedicate time and resources to building systems that track costs and notify you of them
	- Pay only for the resources that are used
	- Measure the output-cost ration of systems to remain efficient
	- Stop spending money on heavy lifting
	- Analyze and attribute expenditures
Tenets of AWS Archtecture
- High Availability
	- Services should remain hiighly available by having no single point of failure
	- This is done by having the workload split between AWS regions
	- Use Elastic Load Balancer to distribute traffic across locations and account for node failure
- Scalability
	- Vertical - upgrading current servers to have more resources
	- Horizontal - adding separate servers to compliment your existing servers
- Elasticity
	- The ability to automatically increase or decrease your resources based on metrics
	- Utilize a service such as Auto Scaling Groups to automatically add or remove
- Fault Tolerance
	- The ability to ensure there is no single point of failure and to handle the system appropriately if failure does strike
	- Utilizes failover strategies
- High durability
	- The ability to recover from a disaster with minimal loss
	- RTO - max amount of time that can be afforded to be lost
	- RPO - max amount of data that can be afforded to be lost