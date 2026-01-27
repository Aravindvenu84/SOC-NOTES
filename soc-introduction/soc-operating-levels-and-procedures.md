# SOC Tier Operations: L1, L2, L3

This guide summarizes the **standard procedures** for SOC Tier 1, Tier 2, and Tier 3 operations and how they coordinate to ensure efficient threat detection and response.

---

## a. L1 – Monitoring & Triage

**Role:** First line of defense; continuously monitors alerts and performs initial triage.  

**Standard Procedures:**
- **Alert Monitoring:** Continuously monitor SIEM dashboards, IDS/IPS alerts, endpoint logs, and network traffic.  
- **Initial Triage:** Validate alerts, categorize incidents (low, medium, high severity), and filter false positives.  
- **Ticketing:** Create and update incident tickets with relevant details (timestamp, affected systems, alert source).  
- **Escalation:** Forward confirmed incidents to L2 if severity or complexity exceeds L1 scope.  
- **Communication:** Notify relevant stakeholders for critical alerts while maintaining escalation protocols.  

**Key Tools:** SIEM (Splunk, ELK, QRadar), IDS/IPS, EDR, ticketing platforms (ServiceNow, Jira, TheHive).  

**Real-World Example:** Detecting multiple failed login attempts indicating a potential brute-force attack and escalating to L2 for investigation.

---

## b. L2 – Investigation & Response

**Role:** Incident investigation and response; deeper analysis than L1.  

**Standard Procedures:**
- **Alert Analysis:** Examine L1 escalations in detail using logs, packet captures, endpoint telemetry, and threat intelligence.  
- **Root Cause Identification:** Determine attack vector, scope of compromise, and affected assets.  
- **Containment & Mitigation:** Isolate affected systems, block malicious IPs, terminate malicious processes.  
- **Remediation Actions:** Patch vulnerabilities, remove malware, reset compromised accounts.  
- **Documentation:** Update tickets with investigation findings, actions taken, and recommendations.  
- **Escalation:** Forward highly complex or persistent threats to L3 for advanced analysis.  

**Key Tools:** SIEM, EDR, forensic tools, packet analysis software (Wireshark), malware analysis sandboxes.

**Real-World Example:** Investigating malware infection escalated from L1, isolating the infected system, removing malware, and restoring service.

---

## c. L3 – Threat Hunting & Advanced Analysis

**Role:** Specialized, proactive, and in-depth threat analysis; develops detection strategies and hunts for unknown threats.  

**Standard Procedures:**
- **Proactive Threat Hunting:** Search for undetected threats using hypotheses, historical data, and threat intelligence.  
- **Advanced Forensics:** Perform deep forensic analysis on endpoints, memory dumps, and network traffic.  
- **Detection Tuning:** Refine SIEM correlation rules, alerts, and detection signatures.  
- **Strategic Threat Response:** Identify advanced persistent threats (APTs), ransomware variants, and sophisticated attacks.  
- **Knowledge Sharing:** Document findings, update SOC playbooks, and train L1/L2 teams.  

**Key Tools:** Threat intelligence platforms, advanced EDR/forensics tools, SIEM tuning dashboards, malware analysis sandboxes.  

**Real-World Example:** Detecting and analyzing an APT attack targeting internal systems, tuning detection rules to prevent recurrence, and updating SOC playbooks.

---

## d. Comparative Summary: L1, L2, L3 Coordination

| Tier | Main Role | Key Responsibilities | Coordination |
|------|-----------|--------------------|-------------|
| **L1** | Monitoring & Triage | Monitor alerts, validate incidents, filter false positives, escalate | Acts as the **first line**, escalating confirmed alerts to L2 for deeper investigation. |
| **L2** | Investigation & Response | Analyze escalated incidents, determine root cause, contain threats, remediate | Collaborates with L1 for alert context; escalates complex incidents to L3 if advanced analysis is needed. |
| **L3** | Threat Hunting & Advanced Analysis | Hunt unknown threats, perform forensic analysis, tune detection systems | Supports L2 with expertise; develops detection rules and knowledge base to improve L1/L2 efficiency. |

**Workflow Overview:**
1. **L1** detects and triages alerts → creates incident tickets.  
2. **L2** investigates, contains, and remediates escalated incidents.  
3. **L3** performs threat hunting, advanced analysis, and feedback loop for improving detection and response.  

**Summary:**  
SOC tiers operate as a **layered defense system**: L1 ensures constant monitoring, L2 provides in-depth incident response, and L3 drives proactive threat hunting and detection improvements. Effective coordination reduces MTTR and strengthens organizational security posture.
