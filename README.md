**Distributed System Threat Modeling Case Study
Overview**

This case study presents a structured threat modeling assessment of a distributed monitoring and control system consisting of telemetry sources, Data Acquisition & Control (DAC) servers, historical storage (HIS), operator workstations, and web-facing customer access nodes. A parallel Quality Assurance System (QAS) environment mirrors Production (PROD) for validation and testing.

The objective of this assessment was to evaluate architectural trust boundaries, identify systemic security risks, and propose mitigations aligned with least privilege and segmentation principles.


System Context
The evaluated architecture includes:
 - Remote telemetry sources transmitting operational data
 - Centralized Production DAC servers responsible for data aggregation and control dispatch
 - Internal operator workstations with control capability
 - Web-facing servers providing view-only customer access
 - Historical Information Servers (HIS) for archival storage
 - A replicated QAS environment synchronized from Production for testing

Key architectural assumptions included network isolation of Production systems and restricted administrative access.


Identified Risk Areas
The threat modeling exercise identified several systemic risks:
 - Cross-environment network exposure between QAS and Production telemetry networks
 - Internet-accessible QAS servers, expanding attack surface
 - Shared administrative service accounts, limiting traceability and accountability

These conditions collectively increased the risk of:
 - Lateral movement between environments
 - Unauthorized control signaling to telemetry-connected assets
 - Reduced incident attribution and response effectiveness

In control-capable distributed systems, these exposures extend beyond data confidentiality into potential operational disruption.


Mitigation Strategy
Two primary mitigation categories were proposed:

1. Network Segmentation & Isolation
 - Removal of QAS access to Production telemetry networks
 - Elimination of unnecessary internet connectivity on QAS servers
 - Restoration of strict environment trust boundaries

2. Identity & Access Controls
 - Replacement of shared service accounts with individual administrator accounts
 - Improved auditability and traceability of system changes
 - Recommendation for centralized identity management to reduce operational overhead

These mitigations reduce lateral movement opportunities, improve containment, and strengthen incident response capability.


Security Principles Applied
 - Least Privilege
 - Network Segmentation
 - Trust Boundary Enforcement
 - Identity Accountability
 - Blast Radius Reduction


Key Takeaway
In distributed industrial systems, security posture is primarily determined by architectural discipline rather than isolated vulnerabilities. Preserving environment separation and eliminating shared identity models significantly reduces both the likelihood and impact of compromise.


Full Case Study
The complete case study document, including architectural diagrams and detailed mitigation analysis, is available in this repository.
