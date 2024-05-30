<u>Principle of Least Privilege</u> - ALWAYS only give enough privileges to a user to accomplish what they need and nothing else
<u>Identity and Access Management</u> - AWS's key service for managing users and permissions based on JSON documentation. In this service you can assign permissions to users and other AWS services
- IAM Identities
	- Users - End users that login to the console or need programmatic access
	- Groups - Groups of end users that you can setup to share permissions
	- Roles - Used to grant other AWS services permissions to do specific API actions
- Components of an IAM Policy
	- Statement ID - Used to label and identify each statement
	- Effect - Specify if this policy will Allow or Deny
	- Action - Which actions the policy will enforce
	- Principal - Account, user, or role you want to control in this policy
	- Resource - the resource that the domain of the policy applies to 
	- Condition (Optional) - Circumstances under which the policy is enacted
Amazon Cognito - service that handles allowing access by utilizing a third party identity provider, also known as federated identities
<u>Root User</u> - a special account that is created upon the creation of your AWS account that has full access to everything. Should be well secured wth MFA and extremely limited access
- Changng account settings
- Restore IAM user permissions
<u>Application Integration</u> - letting multiple independent applications work and communicate with each other while being facilitated by an intermediate system. Systems used for application integration are:
- Queuing - used to process messaging and events that will delete messages once they are consumed, <u>Amazon Simple Queue Service</u> - allows users to create queues so they can decouple and scale systems and applications
- Pub/Sub - consists of publishers (message senders) topics (event handlers) and subscribers (message receivers), commonly used for messaging systems and notifications of events, used by <u>Amazon Simple Notification Service</u> - a fully managed service to handle a pub/sub system
- Streaming - utilizing SNS and SQS, users or services can react to events/messages in real time as they are processed, <u>Amazon Kinesis</u> - primary streaming service to handle analyzing real time incoming events
- API Gateways - can be thought of as the middleman that sits between the application and the backend system, <u>Amazon API Gateway</u> - handles APIs in the cloud environment context and allows you to format requests and responses
- <u>Amazon EventBridge</u> - used with CloudWatch to monitor how the system is performing and what is happening with them. Usually used to monitor what is happening with the EC2 inistances
<u>Containers</u> - allow the running of multiple applications on the same EC2 instance that are completely isolated from each other, comes with everything that an applciation needs to run 
- <u>Elastic Container Service</u> - service that allows you to deploy, manage, and scale containerized applications (uses Docker)
- <u>Elastic Kubernetes Service</u> - More hands-on service that helps kubernetes control nodes, schedule containers, manage application availability, store cluster data, and other tasks. Works with Docker
- <u>AWS Fargate</u> - hands-off version of the EKS, allows the user to focus on building applications and less on dealing with containers and their nuances
<u>AWS Organizations</u> - a service that allows you to create new AWS accounts tied to the business and centrally manage billing access compliance security and share resources
- The root account sits at the top of the organization
- Organizational units are groups of AWS accounts and can be nested
- Service Control policies act as guardrails for the organizational account
- Can enable consolidated billing to send bills to one account
- Can see which account is incurring which costs
- Share resources across accounts![[Pasted image 20240527134554.png]]
<u>Governance and Policies</u> - services that automatically ensure that the cloud resources are all compliant and any changes made are recorded and verified with the rules specified
- <u>AWS Artifact</u> - one stop shop for security and compliance reports
- <u>AWS Config</u> - used to manage changes in your AWS account and make sure they are compliant with processes set by your organization
	- Ensure a resource remains configured in a specific way
	- Keep track of all configuration changes to resources
	- List all resource  within a region
	- Assist with security analysis by detailing historical information and changes
- <u>CloudFormation</u> a service that allows you to make templates to specify how you want architecture deployed
- <u>Tagging</u> - involves identifying resources with key-value pairs, and is one of the best ways to manage costs
	- Manage rsources to see how much a certain resource has allocated
	- Automation
	- Governance and compliance
	- helps classify data and subsequent security impacts
- <u>AWS License Manager</u> - this service allows a user to manage licenses that are required by software to be run
<u>Logging</u> - helps pinpoint failure areas
- <u>AWS CloudWatch</u> - monitors what is happening within the infrastructure
	- Logs, Metrics, EventBridge, Alarms, Dashboards
	- OK, ALARM, INSUFFICIENT_DATA
- <u>AWS CloudTrail</u> - monitors API calls and actoins made on an AWS account
	- Where - Source IP address, When, Who, What - Resource/Region/Action
	- Stored in S3 and are analyzed using <u>Amazon Athena</u> - serverless service used to analyze data stored in S3
- <u>Total Cost of Ownership</u> - Used to compare the cost of owning and maintaining you own on-premise physical servers and data centers, and hiring people versus using AWS server and adopting a pay as you go model
- <u>AWS Pricing Calculator</u> - used to estimate the various AWS services. contains over 100 services you can use in the estimate, can be used to figure out final TCO as estimating the costs in the cloud and comparing them to the on-premise costs
	- <u>AWS Budgets</u> - Setup budgets that can send alerts if approaching or exceeding defined budget and can create budget reports 
	- <u>AWS Cost and Usage Reports</u> - detailed spreadsheets that help better analyze and understand AWS costs and will contain allocation tags
	- <u>AWS Cost Explorer</u> - Helps visualize understand and manage AWS costs and usage over time and can view data at a monthly or daily level of granularity
	- <u>AWS Consolidated Billing</u> - feature of AWS Organizations that allows you to pay for multiple AWS accounts with one bill
	<u>AWS Support Plans</u> - ![[Pasted image 20240527143120.png]]