# SOC Overview, Hierarchy, and SOPs

This document explains the **role, importance, and objectives of a SOC**, its **hierarchy**, and the purpose of **Standard Operating Procedures (SOPs)**.

---

## a. SOC — Role, Importance, and Objectives

### Role
A **Security Operations Center (SOC)** is a centralized unit responsible for **monitoring, detecting, analyzing, and responding** to cybersecurity incidents within an organization.

### Importance
- Provides **real-time threat detection** and response.
- Protects critical systems, data, and network infrastructure.
- Reduces **Mean Time to Detect (MTTD)** and **Mean Time to Respond (MTTR)**.
- Ensures **compliance** with regulatory requirements and industry standards.
- Maintains organizational **cyber resilience** against attacks.

### Objectives
- Monitor and analyze security events continuously.
- Detect, investigate, and respond to threats promptly.
- Maintain incident records and documentation for audit and analysis.
- Enhance cybersecurity posture via **threat intelligence, proactive measures, and lessons learned**.

---

## b. SOC Hierarchy — L1, L2, L3 Roles and Responsibilities

| Tier | Role | Responsibilities |
|------|------|-----------------|
| **L1 (Tier 1)** | Monitoring & Triage | - Continuous monitoring of alerts from SIEM, IDS/IPS, EDR.<br>- Validate alerts and filter false positives.<br>- Create and update incident tickets.<br>- Escalate confirmed incidents to L2. |
| **L2 (Tier 2)** | Investigation & Response | - Perform in-depth investigation and root cause analysis.<br>- Contain and mitigate threats.<br>- Eradicate malware or vulnerabilities.<br>- Update tickets with detailed findings.<br>- Escalate complex incidents to L3. |
| **L3 (Tier 3)** | Threat Hunting & Advanced Analysis | - Conduct proactive threat hunting and forensic analysis.<br>- Detect advanced persistent threats (APTs).<br>- Tune SIEM rules and detection logic.<br>- Lead lessons learned and update playbooks.<br>- Provide guidance and support to L1/L2 teams. |

**Workflow:**  
- **L1:** First-line detection and triage.  
- **L2:** Deep analysis and response.  
- **L3:** Strategic detection, advanced threat analysis, and continuous improvement.

---

## c. Standard Operating Procedures (SOPs) — Definition and Purpose

### Definition
**SOPs** are **documented instructions** that outline how specific tasks or processes should be performed consistently within the SOC.  

### Purpose
- Ensure **consistent, repeatable, and efficient operations**.  
- Define **roles, responsibilities, and escalation paths** for incident handling.  
- Support **compliance with industry standards and regulations**.  
- Facilitate **training of new analysts** and knowledge transfer.  
- Improve **incident response effectiveness** and reduce errors.  

**Example SOP Topics in a SOC:**  
- Alert triage and escalation.  
- Malware analysis procedure.  
- Incident documentation and ticketing standards.  
- Threat hunting methodologies.  
- Reporting and post-incident reviews.

---

**Summary:**  
A SOC is **critical for organizational cybersecurity**, structured into **L1/L2/L3 tiers**, and guided by **SOPs** to ensure **efficient, consistent, and compliant incident detection and response**.
