---
title: "Week 3 Worklog"
date: 2024-01-01
weight: 1
chapter: false
pre: " <b> 1.3. </b> "
---

### Week 3 Objectives

* Continue learning AWS networking services after the VPC and Session Manager topics.
* Understand how VPC Peering connects two VPCs privately.
* Learn how route tables, Network ACLs, and DNS settings affect communication between peered VPCs.
* Study Transit Gateway as a scalable hub for connecting multiple VPCs and networks.

### Tasks to be carried out this week

| Day | Task | Start Date | Completion Date | Reference Material |
| --- | ---- | ---------- | --------------- | ------------------ |
| 1 | **000019 - Set Up VPC Peering** <br> - Preparation steps <br> - Update Network ACL <br> - Create a peering connection <br> - Configure route tables <br> - Enable Cross-Peer DNS | 25/05/2026 | 28/05/2026 | <https://github.com/AWS-First-Cloud-Journey/FCJ-2023> |
| 2 | **000020 - Set Up Transit Gateway** <br> - Set up infrastructure <br> - Create Transit Gateway <br> - Create Transit Gateway attachments <br> - Create route table for TGW <br> - Add gateway to route tables and verify the result | 29/05/2026 | 31/05/2026 | <https://github.com/AWS-First-Cloud-Journey/FCJ-2023> |

### Week 3 Achievements

* Understood the purpose of VPC Peering and when it should be used to connect two VPCs.
* Practiced the key steps required for VPC Peering, including route table updates, Network ACL configuration, and Cross-Peer DNS.
* Learned the limitations of VPC Peering and why a more centralized connectivity model may be needed as the network grows.
* Studied Transit Gateway as a hub-and-spoke networking service for connecting multiple VPCs and on-premises networks.
* Practiced creating Transit Gateway attachments and route tables.
* Improved understanding of how AWS network routing decisions affect private connectivity between workloads.
