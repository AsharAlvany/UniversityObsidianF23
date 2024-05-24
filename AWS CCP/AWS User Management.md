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
- <u>Amazon EventBridge</u> - used with CloudWatch to monitor how the system is performing and what is happening with them. Usually used to monitor what is happening with the EC2 inistances.