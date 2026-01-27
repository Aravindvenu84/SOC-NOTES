# Security Incident IRP Documentation

This document outlines **five common security incidents** and demonstrates how the **six IRP stages** (Preparation, Identification, Containment, Eradication, Recovery, Lessons Learned) are applied, with detailed documentation for each stage.

---

## 1. Phishing Attack

**Incident Summary:** A user received a malicious email containing a link to a credential-stealing website.

### IRP Stages & Documentation

1. **Preparation**
   - Policies: Anti-phishing awareness training completed; email filtering enabled.
   - Tools: Email gateway filters, SIEM alerts, endpoint protection.
   - **Documentation:** "SOC pre-configured phishing detection rules and trained users monthly."

2. **Identification**
   - Detection: User reported suspicious email; SIEM flagged unusual link clicks.
   - Verification: Cross-referenced email headers, URL reputation, and threat intelligence.
   - **Documentation:** "Ticket created: PH-001; source email flagged by Gateway; URL linked to known phishing domain."

3. **Containment**
   - Actions: Quarantine email, block malicious domain, notify impacted user to avoid clicking links.
   - **Documentation:** "PH-001 updated: Malicious email quarantined, domain blocked, user advised."

4. **Eradication**
   - Actions: Remove malware from endpoint (if clicked), reset user credentials.
   - **Documentation:** "User endpoint scanned; no malware found. Password reset enforced."

5. **Recovery**
   - Actions: Verify email functionality, ensure no further compromise.
   - **Documentation:** "User account restored; email service verified; monitoring enabled."

6. **Lessons Learned**
   - Actions: Update filters, improve user awareness campaigns.
   - **Documentation:** "PH-001 closed. Recommended additional phishing training; updated detection rules."

---

## 2. DDoS Attack

**Incident Summary:** Web application overwhelmed by a flood of traffic from multiple IPs.

### IRP Stages & Documentation

1. **Preparation**
   - Policies: DDoS mitigation plan in place, rate limits, and network monitoring enabled.
   - Tools: Firewall, IDS/IPS, CDN with DDoS protection.
   - **Documentation:** "SOC prepared with anti-DDoS services and alert thresholds."

2. **Identification**
   - Detection: Spike in traffic; IDS alerts on abnormal requests.
   - Verification: Check traffic origin, patterns, and affected services.
   - **Documentation:** "Ticket DD-001 opened: 10x traffic surge from multiple regions detected."

3. **Containment**
   - Actions: Enable rate limiting, block offending IPs, redirect traffic via CDN.
   - **Documentation:** "Traffic mitigated using CDN WAF and IP blocking."

4. **Eradication**
   - Actions: Remove malicious traffic, close exploited endpoints.
   - **Documentation:** "Blocked IPs removed; vulnerable API endpoint disabled."

5. **Recovery**
   - Actions: Restore services to normal traffic; monitor for recurrence.
   - **Documentation:** "Web services fully operational; traffic normalized."

6. **Lessons Learned**
   - Actions: Update mitigation thresholds, add monitoring dashboards.
   - **Documentation:** "DD-001 closed. Added automated detection alerts for traffic spikes."

---

## 3. Ransomware Infection

**Incident Summary:** Malware encrypted critical files on a user workstation.

### IRP Stages & Documentation

1. **Preparation**
   - Policies: Regular backups, endpoint protection installed.
   - Tools: EDR, antivirus, offline backup systems.
   - **Documentation:** "Backups tested weekly; ransomware detection rules active."

2. **Identification**
   - Detection: EDR triggered alert on unusual file encryption activity.
   - Verification: Confirmed malicious process via sandbox analysis.
   - **Documentation:** "Ticket RW-001 opened; encryption activity confirmed on C:\Users\Finance."

3. **Containment**
   - Actions: Isolate affected workstation from the network.
   - **Documentation:** "RW-001 updated: Endpoint disconnected; lateral movement prevented."

4. **Eradication**
   - Actions: Remove ransomware, patch exploited vulnerability.
   - **Documentation:** "Malware removed; endpoint patched and reimaged."

5. **Recovery**
   - Actions: Restore files from clean backup, verify functionality.
   - **Documentation:** "Files restored from backup; verified integrity; endpoint reconnected."

6. **Lessons Learned**
   - Actions: Improve detection, employee training, apply enhanced filtering.
   - **Documentation:** "RW-001 closed. Updated anti-malware rules; recommended phishing training."

---

## 4. Data Breach

**Incident Summary:** Unauthorized access to sensitive customer data.

### IRP Stages & Documentation

1. **Preparation**
   - Policies: Access control policies, encryption, data monitoring enabled.
   - Tools: DLP, SIEM, identity management system.
   - **Documentation:** "Access audits conducted; data encryption enforced."

2. **Identification**
   - Detection: SIEM flagged unusual data access patterns.
   - Verification: Logs confirmed unauthorized access to customer database.
   - **Documentation:** "DB-001 opened: Access from unusual IP detected."

3. **Containment**
   - Actions: Disable compromised accounts, restrict network access.
   - **Documentation:** "DB-001 updated: User accounts locked; database access restricted."

4. **Eradication**
   - Actions: Remove unauthorized access credentials, patch system vulnerabilities.
   - **Documentation:** "Access credentials revoked; system patched."

5. **Recovery**
   - Actions: Restore affected systems, verify data integrity.
   - **Documentation:** "Database access restored; monitoring intensified."

6. **Lessons Learned**
   - Actions: Update access controls, conduct training, refine monitoring.
   - **Documentation:** "DB-001 closed. Policies updated; added real-time anomaly alerts."

---

## 5. Brute Force Attack

**Incident Summary:** Attackers attempting multiple password guesses to compromise accounts.

### IRP Stages & Documentation

1. **Preparation**
   - Policies: Password complexity requirements, MFA enforced.
   - Tools: SIEM, authentication logs, account lockout policies.
   - **Documentation:** "Account policies enforced; monitoring rules active."

2. **Identification**
   - Detection: SIEM alerts on repeated failed login attempts.
   - Verification: Cross-check logs for source IP and target accounts.
   - **Documentation:** "BF-001 opened: 50 failed logins detected on finance portal."

3. **Containment**
   - Actions: Lock targeted accounts, block IP addresses.
   - **Documentation:** "Accounts locked; source IPs blocked in firewall."

4. **Eradication**
   - Actions: Reset passwords, investigate compromised accounts.
   - **Documentation:** "Compromised credentials reset; accounts verified clean."

5. **Recovery**
   - Actions: Restore normal user access, monitor authentication systems.
   - **Documentation:** "All accounts restored; MFA reinforced."

6. **Lessons Learned**
   - Actions: Adjust detection thresholds, improve alerting, conduct user awareness.
   - **Documentation:** "BF-001 closed. Added SIEM correlation rules; user training updated."

---

**Summary:**  
Applying all six IRP stages ensures **structured incident management** across all types of security events. Detailed documentation at each stage helps SOC teams maintain **audit trails, accountability, and continuous improvement**.
