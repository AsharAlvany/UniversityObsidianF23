Timeline:
- Dedicated server - one physical machine to single business
	- Runs a single web-app/site
	- Expensive, high maintenance, but high security
- Virtual Private Server (VPS) - one physical machine dedicated to a single business the physical machine is virtualized into sub-machines.
	- Runs multiple web-apps/sites
	- Better utilization and isolation of resources
- Shared Hosting - one physical machine, shared by hundreds of businesses
	- Relies on most tenants under-utilizing their resources
	- Very cheap, limited functionality, poor isolation
- Cloud Hosting - multiple physical machines that act as one system
	- The system is abstracted into multiple cloud services
	- flexible, salable, secure, cost-effective, high configuration
What is Amazon?
- "An American multinational computer technology corporation headquarterd in Seattle, Washington"
- Founded in 1994 by Jeff Bezos and the company started as an online eCommerce bookstore 
- Andy Jassy is the current CEO
What is AWS?
- Cloud Service Provider (CSP)
- Simple Queue Service (SQS) -> Simple Storage Service (S3) -> Elastic Compute Cloud (EC2) -> 2010 migration -> 2013 AWS training
- CEO Adam Selipsky, CTO Werner Vogels
What is CSP?
- provides multiple cloud services
- can be chained together to create cloud architectures
- are accessible via Single Unified API (AWS API)
- utilizes metered billing based on usafe (per second, per CPU, per GB of storage etc)
- have rich monitoring built in (AWS CloudTrail)
- Infrastructure as a Service (IaaS) offering
- offer Automation vie Infrastructure as Code (IaC)![[Pasted image 20240518180815.png]]
- If a company do not meet these requirements, t would be referred to as a Cloud Platform
Landscape of CSPs
- Tier-1 (Top Tier) - Early to market, wide offering, strong synergy
	- AWS
	- Azure
	- Google Cloud Platform
	- Alibaba Cloud
- Tier-2 (Mid Tier) - Backed by well-known tech comanies, slow to innovate and turned to specialization
	- IBM Cloud
	- Oracle Cloud
	- Huawei Cloud
	- Tencent Cloud
- Tier-3 (Light Tier) - VPS turned to offer core IaaS offering. Simple, cost-effective
	- Vultr
	- Digital Ocean
	- Linode
- Tier-4 (Private Tier) - Infrastructure as Service software deployed to run in an organization's own private data center
	- OpenStack
	- Apache CloudStack
	- Vmware vSphere
Main CPS Technologies - 
- Compute - this is where we have virtual computation done off-site. AWS's implementaion/service for this technology s EC2 Compute
- Storage - data is stored off-site. AWS has EFS, S3, and EBS
- Database - off-site managed database service. AWS has RDS.
- Networking - management of routing, connections, and network isolation. AWS VPC
Types of Cloud Computing
- SaaS - made for customers. A product is run and managed by the service provider.
- PaaS - made for developers. Focus on the development and management of your apps
- IaaS - made for admins. Provides access to networking features, computers and data storage space.
Cloud Computing Deployment Models
- Public Cloud - a cloud-first strategy where everything is on the cloud
- Private Cloud - a strategy where a privately-owned datacenter is used with a cloud-like software (such as OpenStack) to extend functionality, but all costs, data, and infrastructure is managed and owned by the company
- Hybrid - using both private and public to interact with each other
- Cross-Cloud - multiple cloud providers together![[Pasted image 20240518183438.png]]
Cloud Advantages
- Trade capital expense for variable expense - pay on demand
- Benefit from massive economies of scale - sharing the cost with other customers
- Stop guessing capacity - scale up or down
- Increase speed and agility - launch resources within a few clicks in minutes
- Stop spending money on running and maintaining data centers - focus on your own customers
- Go global in minutes - deploy you app in multiple regions around the world with a few clicks