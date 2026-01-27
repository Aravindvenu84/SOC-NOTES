# Common Cyberattacks and SOC Response Guide

This document outlines 10 common cyberattacks, their mechanisms, indicators of compromise (IOCs), detection/mitigation tools, and SOC response per IRP stages.

---

## 1. Brute Force Attack
- **What it is:** Attempting to gain unauthorized access by systematically guessing passwords.
- **How it occurs:** Automated scripts try multiple username/password combinations until successful.
- **Indicators of Compromise:** Multiple failed login attempts, account lockouts, unusual authentication patterns.
- **Detection & Mitigation Tools:** SIEM alerts, IDS/IPS, MFA enforcement, account lockout policies.

**SOC Response per IRP Stage:**
- **Preparation:** Ensure password policies, MFA, and monitoring are in place.
- **Identification:** Detect abnormal login attempts via SIEM or IDS.
- **Containment:** Lock affected accounts, block malicious IPs.
- **Eradication:** Reset compromised passwords, remove malicious sessions.
- **Recovery:** Restore user access with secure credentials.
- **Lessons Learned:** Strengthen password policies, educate users, review detection rules.

---

## 2. Phishing Attack
- **What it is:** Fraudulent emails or messages tricking users into revealing sensitive information.
- **How it occurs:** Attackers send emails with malicious links or attachments.
- **Indicators of Compromise:** Unexpected email attachments, suspicious links, credential theft reports.
- **Detection & Mitigation Tools:** Email filtering, endpoint protection, URL scanning, threat intelligence.

**SOC Response per IRP Stage:**
- **Preparation:** Employee training, anti-phishing filters, threat intelligence feeds.
- **Identification:** User reports or automated detection of malicious emails.
- **Containment:** Quarantine phishing emails, block malicious URLs.
- **Eradication:** Remove malware, reset compromised accounts.
- **Recovery:** Verify systems are clean, restore email services.
- **Lessons Learned:** Enhance training, improve email filtering, update indicators.

---

## 3. Malware Infection
- **What it is:** Malicious software compromising system integrity.
- **How it occurs:** Through downloads, email attachments, or exploits.
- **Indicators of Compromise:** Unexpected system behavior, unusual network traffic, antivirus alerts.
- **Detection & Mitigation Tools:** Endpoint protection, EDR, sandbox analysis.

**SOC Response per IRP Stage:**
- **Preparation:** Maintain updated antivirus, EDR deployment, backups.
- **Identification:** Alerts from endpoint protection or abnormal behavior logs.
- **Containment:** Isolate infected systems.
- **Eradication:** Remove malware, apply patches, remediate vulnerabilities.
- **Recovery:** Restore files from backups.
- **Lessons Learned:** Review malware vector, improve detection and prevention.

---

## 4. Denial of Service (DoS/DDoS)
- **What it is:** Flooding systems or networks to make services unavailable.
- **How it occurs:** Botnets or scripts overwhelm resources.
- **Indicators of Compromise:** High traffic volume, system slowness, service outages.
- **Detection & Mitigation Tools:** Network monitoring, firewalls, rate limiting, anti-DDoS services.

**SOC Response per IRP Stage:**
- **Preparation:** Implement network monitoring, rate limits, and mitigation strategies.
- **Identification:** Detect abnormal traffic spikes.
- **Containment:** Block offending IPs or networks, enable DDoS protection.
- **Eradication:** Remove malicious traffic and close exploited vulnerabilities.
- **Recovery:** Restore normal service.
- **Lessons Learned:** Update monitoring, refine mitigation policies, review network capacity.

---

## 5. SQL Injection
- **What it is:** Exploiting vulnerable web applications to execute malicious SQL queries.
- **How it occurs:** Input fields are manipulated to access or modify the database.
- **Indicators of Compromise:** Unexpected database errors, unauthorized data access.
- **Detection & Mitigation Tools:** Web application firewalls (WAF), vulnerability scanning, input validation.

**SOC Response per IRP Stage:**
- **Preparation:** Secure coding practices, WAF deployment, regular scans.
- **Identification:** Detect unusual queries or application errors.
- **Containment:** Block malicious IPs, disable affected endpoints.
- **Eradication:** Patch application vulnerabilities, review database access.
- **Recovery:** Restore affected data.
- **Lessons Learned:** Train developers, enhance input validation, update security policies.

---

## 6. Man-in-the-Middle (MITM) Attack
- **What it is:** Intercepting communications between parties to steal or alter information.
- **How it occurs:** Network sniffing, rogue access points, ARP spoofing.
- **Indicators of Compromise:** Suspicious network traffic, certificate warnings, unexpected system behavior.
- **Detection & Mitigation Tools:** Encrypted communication (TLS/SSL), IDS/IPS, network monitoring.

**SOC Response per IRP Stage:**
- **Preparation:** Enforce encryption, VPN use, monitor networks.
- **Identification:** Detect ARP anomalies, unexpected packet captures.
- **Containment:** Isolate compromised network segments.
- **Eradication:** Remove rogue devices, correct network configurations.
- **Recovery:** Resume normal communication.
- **Lessons Learned:** Strengthen network encryption and monitoring.

---

## 7. Ransomware
- **What it is:** Malware encrypting files and demanding ransom for decryption.
- **How it occurs:** Delivered via phishing, malicious downloads, or vulnerabilities.
- **Indicators of Compromise:** File encryption alerts, ransom notes, abnormal CPU usage.
- **Detection & Mitigation Tools:** EDR, backups, anti-ransomware tools, SIEM alerts.

**SOC Response per IRP Stage:**
- **Preparation:** Maintain offline backups, deploy endpoint monitoring.
- **Identification:** Detect unusual file encryption or ransomware signatures.
- **Containment:** Isolate infected endpoints.
- **Eradication:** Remove ransomware, patch vulnerabilities.
- **Recovery:** Restore files from clean backups.
- **Lessons Learned:** Improve backup strategy, user training, and endpoint protection.

---

## 8. Cross-Site Scripting (XSS)
- **What it is:** Injecting malicious scripts into web pages viewed by users.
- **How it occurs:** Unsanitized input fields or vulnerable web applications.
- **Indicators of Compromise:** Unexpected pop-ups, stolen cookies, unusual browser behavior.
- **Detection & Mitigation Tools:** WAF, input validation, penetration testing.

**SOC Response per IRP Stage:**
- **Preparation:** Secure coding, regular vulnerability scanning.
- **Identification:** Detect malicious script execution or abnormal user behavior.
- **Containment:** Disable affected endpoints or inputs.
- **Eradication:** Patch web application, sanitize inputs.
- **Recovery:** Validate application functionality.
- **Lessons Learned:** Strengthen coding practices and user education.

---

## 9. Insider Threat
- **What it is:** Malicious or negligent actions by employees or contractors.
- **How it occurs:** Unauthorized access, data exfiltration, sabotage.
- **Indicators of Compromise:** Unusual file access, privilege abuse, abnormal login times.
- **Detection & Mitigation Tools:** UEBA (User and Entity Behavior Analytics), DLP, SIEM monitoring.

**SOC Response per IRP Stage:**
- **Preparation:** Implement access controls, monitoring, and awareness programs.
- **Identification:** Detect anomalies in user behavior or access patterns.
- **Containment:** Restrict or revoke access of suspicious users.
- **Eradication:** Remove malicious files, terminate malicious sessions.
- **Recovery:** Restore systems and audit user activity.
- **Lessons Learned:** Revise access policies, improve monitoring, and conduct training.

---

## 10. Advanced Persistent Threat (APT)
- **What it is:** Stealthy, targeted attacks aiming for long-term access.
- **How it occurs:** Spear-phishing, malware implants, exploitation of vulnerabilities.
- **Indicators of Compromise:** Unusual network traffic, long-term unauthorized access, lateral movement.
- **Detection & Mitigation Tools:** Threat intelligence, EDR, network monitoring, anomaly detection.

**SOC Response per IRP Stage:**
- **Preparation:** Threat intelligence integration, advanced monitoring, patch management.
- **Identification:** Detect persistent anomalies or malicious activity.
- **Containment:** Isolate affected systems, restrict network access.
- **Eradication:** Remove malware, patch systems, eliminate persistence mechanisms.
- **Recovery:** Restore services securely and monitor for recurrence.
- **Lessons Learned:** Update threat detection, refine incident response playbooks, share intelligence.

---

**Summary:**  
This guide provides structured details for **10 common cyberattacks**, including detection, mitigation, and SOC incident response. Following the **IRP stages (Preparation → Lessons Learned)** ensures incidents are handled systematically, improving security posture and reducing risk.

