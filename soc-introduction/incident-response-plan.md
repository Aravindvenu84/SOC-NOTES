# Incident Response Plan (IRP) Stages Guide

This guide outlines the **six stages of an Incident Response Plan (IRP)**, explains each stage, provides real-world SOC examples, and includes a visual flowchart representation.

---

## a. Six IRP Stages
1. **Preparation**
2. **Identification**
3. **Containment**
4. **Eradication**
5. **Recovery**
6. **Lessons Learned**

---

## b. Short Explanation for Each Stage

### 1. Preparation
- **Explanation:** Establish policies, procedures, tools, and trained personnel before an incident occurs.  
- **SOC Example:** SOC deploys SIEM, endpoint monitoring, and employee security awareness programs to detect threats proactively.

### 2. Identification
- **Explanation:** Detect and confirm the occurrence of a security incident using monitoring tools, logs, and alerts.  
- **SOC Example:** SOC receives alerts from SIEM about multiple failed login attempts indicating a potential brute-force attack.

### 3. Containment
- **Explanation:** Limit the spread and impact of the incident while maintaining evidence for analysis.  
- **SOC Example:** SOC isolates a compromised endpoint from the network to prevent malware propagation.

### 4. Eradication
- **Explanation:** Remove the root cause of the incident, such as malware, compromised accounts, or vulnerabilities.  
- **SOC Example:** SOC removes ransomware from affected systems and patches the exploited vulnerability.

### 5. Recovery
- **Explanation:** Restore systems and services to normal operation, ensuring no residual threat remains.  
- **SOC Example:** SOC restores files from clean backups and verifies system integrity before reconnecting to the network.

### 6. Lessons Learned
- **Explanation:** Review the incident, update policies, and improve detection/prevention measures to prevent recurrence.  
- **SOC Example:** SOC documents the incident timeline, identifies gaps in monitoring, and updates alert rules for future attacks.

---

## c. Visual Flowchart of IRP Stages

```text
         ┌─────────────┐
         │ Preparation │
         └─────┬──────┘
               │
               ▼
        ┌────────────┐
        │ Identification │
        └─────┬───────┘
               │
               ▼
        ┌────────────┐
        │ Containment │
        └─────┬──────┘
               │
               ▼
        ┌────────────┐
        │ Eradication │
        └─────┬──────┘
               │
               ▼
        ┌────────────┐
        │  Recovery   │
        └─────┬──────┘
               │
               ▼
        ┌──────────────┐
        │ Lessons Learned │
        └──────────────┘
`````
## d. Real-World SOC Examples for Each Stage

| Stage           | SOC Example                                                                                                 |
| --------------- | ----------------------------------------------------------------------------------------------------------- |
| Preparation     | Deploy SIEM, EDR, firewall rules, and train analysts on phishing detection.                                 |
| Identification  | Detect malware alert from endpoint or anomalous login attempts from SIEM dashboards.                        |
| Containment     | Quarantine infected systems, block malicious IP addresses, and suspend compromised accounts.                |
| Eradication     | Remove malware, patch vulnerabilities, disable malicious scripts or user accounts.                          |
| Recovery        | Restore systems from backups, validate network and application functionality, and resume normal operations. |
| Lessons Learned | Conduct post-incident review, update SOPs, improve detection rules, and conduct staff security training.    |
