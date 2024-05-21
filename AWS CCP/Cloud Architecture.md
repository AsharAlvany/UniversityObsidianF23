<u>Solutions Architect</u> - A role that architects a technical solution using multiple systems via researching, documentation, and experimentation
<u>Cloud Architect</u> - A solutions architect that is focused on architecting technical solutions using cloud services
<u>Availability</u> - your ability to ensure a service remains available
- No single point of failure, using <u>Elastic Load Balancer</u>
<u>Scalability</u> - your ability to grow rapidly or unimpeded
- Increase your capacity based on the increasing demand of traffic (horizontal and vertical expansion)
<u>Elasticity</u> - your ability to shrink and grow to meet the demand
- Automatic scalability out and in using <u>Auto Scaling Groups</u> - an AWS feature that will automatically add or remove servers based on scaling rules that you define
<u>Fault Tolerance</u> - your ability to prevent a failure
- Ensure that there is no single point of failure. A failover database
<u>Disaster Recovery</u> - your ability to recover from a failure
- Backups, speed of restore, lack of backup corruptoin <u>CloudEndure Disaster Recovery</u> - continuously replicates machines into a low-cost staging area in your AWS account and preferred Region enabling fast and reliable recovery in case of IT data center failures
<u>Business Continuity Plan</u> - documentation that outline how a business will continue operating during an unplanned disruption
<u>Recovery Point Objective (RPO)</u> - the maximum acceptable amount of data loss after an unplanned data-loss incident, expressed as an amount of time "How much data are we willing to lose?"
<u>Recovery Time Objective (RTO)</u> - the maximum amount of downtime that our business can tolerate without incurring significant financial loss " how much time are we willing to go down?"
<u>Disaster Recovery Options</u>
- Backup and Restore - data is backed up and we can restore to the new infrastructure (Hours)
- Pilot Light - data is replicated to another region with the minimal resources running (Minutes)
- Warm Standby - scaled down copy of your infrastructure running ready to scale (Minutes)
- Multi-site Active/Active - Scaled up copy of your infrastructure in another region (Real-time)