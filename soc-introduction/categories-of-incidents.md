# SOC Incident Categories and Response Actions

This document summarizes common types of security incidents, their characteristics, and appropriate SOC response actions.

---

## 1. Malware

- **Summary:** Malicious software designed to disrupt, damage, or gain unauthorized access to systems. Includes viruses, worms, ransomware, and spyware.
- **Response Actions:**
  - Containment: Isolate infected systems from the network.
  - Eradication: Remove malware, patch vulnerabilities.
  - Recovery: Restore systems from clean backups.
  - Lessons Learned: Update malware signatures, improve endpoint monitoring.

---

## 2. Phishing

- **Summary:** Fraudulent emails or messages that trick users into revealing credentials or clicking malicious links.
- **Response Actions:**
  - Containment: Quarantine suspicious emails, block malicious URLs.
  - Eradication: Reset compromised credentials, remove malware if clicked.
  - Recovery: Verify account integrity and resume normal use.
  - Lessons Learned: Conduct user awareness training and update email filters.

---

## 3. Insider Threat

- **Summary:** Malicious or negligent actions by employees, contractors, or partners that compromise security.
- **Response Actions:**
  - Containment: Revoke access or disable accounts of suspicious users.
  - Investigation: Review logs, file access, and abnormal behavior.
  - Recovery: Restore affected systems and ensure no further access.
  - Lessons Learned: Update access controls, monitor for unusual activity, and provide training.

---

## 4. Brute Force Attack

- **Summary:** Repeated attempts to guess passwords or credentials to gain unauthorized access.
- **Response Actions:**
  - Containment: Lock targeted accounts, block offending IP addresses.
  - Eradication: Reset passwords and verify account security.
  - Recovery: Restore normal access with stronger credentials or MFA.
  - Lessons Learned: Strengthen password policies, configure alerts for failed login attempts.

---

## 5. Denial of Service (DoS/DDoS)

- **Summary:** Flooding of a system or network to render services unavailable.
- **Response Actions:**
  - Containment: Block malicious traffic using firewalls or anti-DDoS services.
  - Eradication: Remove offending IPs or botnet connections.
  - Recovery: Restore services and monitor network stability.
  - Lessons Learned: Update mitigation strategies and refine monitoring thresholds.

---

## 6. Data Breach

- **Summary:** Unauthorized access to sensitive or confidential information.
- **Response Actions:**
  - Containment: Disable compromised accounts, restrict access to sensitive data.
  - Investigation: Determine scope of breach and identify compromised data.
  - Recovery: Restore systems, change credentials, and monitor for further access.
  - Lessons Learned: Improve access controls, encryption, and monitoring policies.

---

## 7. Advanced Persistent Threat (APT)

- **Summary:** Sophisticated, targeted attacks designed to maintain long-term access to systems without detection.
- **Response Actions:**
  - Containment: Isolate affected systems and networks.
  - Investigation: Perform deep forensic analysis to determine attack vectors.
  - Eradication: Remove malware and close persistence mechanisms.
  - Recovery: Restore clean systems and validate integrity.
  - Lessons Learned: Update threat intelligence, detection rules, and SOC playbooks.

---

**Summary:**  
Each incident type requires **tiered SOC response actions** across **containment, eradication, recovery, and lessons learned**. Proper categorization ensures incidents are handled efficiently and mitigates impact on the organization.
