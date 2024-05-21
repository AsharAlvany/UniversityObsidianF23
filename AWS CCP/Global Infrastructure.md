AWS Regions (US-East-1) are comprised of at least three availability zones (US-East-1a, US-East-1b, US-East-1d)
<u>Fault-Domains</u> - are sections of a network that is vulnerable to damage if a critical device or system fails. the purpose of a fault domain is that if a failure occurs, damage will not propagate outside that domain
<u>Fault-Level</u> - A fault level is a collection of fault domains
<u>Edge Locations (Also known as Points of Presence (POP)</u> - are datacenters that hold cached copies on the most popular files so that the delivery of distance to the end users are reduced so that a user has the often-accessed information at a datacenter that is closest to them rather than having to travel the entire AWS region to retrieve data
<u>Regional Edge Locations</u> - are datacenters that hold much larger caches of less-popular files to reduce a full round trip and also to reduce the cost of transfer fees
Services that use <u>Point of Presence</u>
- <u>Amazon CloudFront</u> is a Content Delivery Network service that allows developers to point content to Points of Presence so that the data may be cached for users to utilize
- <u>Amazon S3 Transfer Acceleration</u> allows the creation of a URL that can takes uploads at a POP to then be shot through the AWS network to the origin of the S3 bucket, which allows for much faster uploads
- <u>AWS Globale Accerlerator</u> - finds the optimal path from the end-user to your web-server. Global Accelerators are deployed to edge locations so that a user can send traffic to Edge Locations rather than directly to the origin of the web-application
<u>AWS Direct Connect</u> - is a private/dedicated connections between you datacenter, office, co-location and AWS. This helps reduce network costs, increase bandwidth throughput, and create a more consistent network experience.
<u>Direct Connect Locations</u> are trusted partnered datacenters that you can establish a dedicated high speed, low-latency connections from your on-premise to AWS
<u>Local Zones</u> - are datacenters located very close to a densely populated area to provide single-digit millisecond low latency performance for that area. There is a limited subset of AWS services that are available to use local zones
<u>AWS Wavelength Zones</u> - edge-computing on 5G Networks
<u>Data Residency</u> - the geographic location of where an organization or cloud resources can reside
<u>Compliance Boundaries</u> - a regulatory compliance by an entity that describes where data and cloud resources are allowed to reside
<u>Data Sovereignty</u> - the jurisdictional control that can be asserted over data because its physical location is within jurisdictional boundaries
AWS Outposts is a physical rack of servers that you can put in your data center. This will limit the physical residence of where your resources will be located
AWS Config is a Policy as Code service. Rules can be created t check AWS resource configuration. If there is a deviation from expectations alerts can be raised and AWS Config can auto-remediate
<u>GovCloud</u> - aligns with FedRAMP to provide standardization for security assessment, authorization, and continuous monitoring for cloud products and services
<u>AWS CHina</u> - A completely separate system that is only available to those with a Chinese Business license because there is a large amount of regulation with China
