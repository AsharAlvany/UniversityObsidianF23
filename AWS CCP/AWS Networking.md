AWS Networking
![[Pasted image 20240522181126.png]]
<u>Virtual Private Cloud</u> - a logically isolated section of the AWS network where you launch your AWS resources. Uses CIDR notation to specify a range of IPs to be used
<u>Subnets</u> - smaller partitions within your VPC that also utilize IP address ranges. Must have smaller IP range than the VPC. Subnets can be either public or private
<u>Security Groups</u> - work at the instance level, implicitly denies all traffic, work off of allow rules only ==stateful==
<u>Network Access Control List</u> - work at the subnet level, virtual firewall at the network level, uses allow and deny rules ==stateless== (DENY rules override ALLOW)
<u>Virtual Private Network</u> - provides an isolated secure environment to access resources
- AWS VPN establishes a tunnel between your network and the AWS global network
- Site-to-Site VPN - connect on-premise network to VPC
- Client VPN - connect end users to AWS or on-premise networks
<u>AWS Direct Connect</u> - allows you to create a direct, physical connection to AWS from on-premise where your traffic never touches the public internet
<u>7 Layers of Cloud Application Security</u>:
- Data - access to business/customer data
- Application - apps stay updated and have no vulnerabilities
- Compute - controlled access to VMs
- Network - control access to an communication with resources
- Perimeter - filter large scale attacks
- Identity and Access - control access to infrastructure and change management
- Physical - limit access to data center to only authorized personnel
<u>Encryption</u>:
- In transit - SSL/TLS
- At rest - S3 SSE, RDS DB instances, and more
<u>AWS Inspector</u> - runs a security benchmark for specified EC2 instances
<u>AWS Shield</u> - Used to prevent DDOS attacks (inherently used with Route53 and CloudFront)
<u>Amazon GuardDuty</u> - Threat detection services that continuously monitors your accounts for malicious activity. Uses ML to analyze CloudTrail, DNS, and VPC
<u>AWS Web Application Firewall</u> - application-level firewall to write rules to allow or deny traffic. Protects against the 10 most dangerous attacks
AWS Key Management Service - managed service that makes it easy to create and control encryption keys to encrypt your data. Uses envelope encryption![[Pasted image 20240523151601.png]]
