

## a. How SOC Teams Analyze, Document, and Close Incidents

### Analyze
- Validate alerts from SIEM, IDS/IPS, endpoint detection, and threat intelligence feeds.
- Correlate events across multiple sources to confirm if an incident is genuine or a false positive.
- Assess severity and impact; prioritize incidents based on business risk.
- **Triage Workflow:** Categorize incidents (e.g., malware, phishing, DDoS, unauthorized access) and assign to the appropriate analyst/team.

### Document
- Log all investigation steps in a ticketing system (ServiceNow, Jira, TheHive).
- **Key Details:** Incident timeline, affected assets, alert sources, investigative steps, tools used, analyst observations.
- Documentation ensures accountability, audit readiness, and knowledge sharing.

### Close
- Update tickets with root cause, mitigation actions, and preventive measures.
- Verify and validate that threats are fully neutralized.
- Include lessons learned to improve detection rules, policies, and staff awareness.

---

## b. Steps for Log Analysis, Root Cause Identification, and Resolution

### 1. Log Analysis
- Collect logs from endpoints, servers, firewalls, routers, IDS/IPS, and cloud services.
- Normalize and correlate logs to detect unusual patterns (e.g., failed logins, unusual outbound connections, privilege escalation).
- Use search queries, filters, and dashboards to focus on relevant events.
- Verify alerts by checking timestamps, source/destination IPs, user activity, and file hashes.

### 2. Root Cause Identification
- Identify the initial vector of compromise (e.g., phishing email, vulnerable app, misconfiguration).
- Trace affected systems and user accounts.
- Determine attack progression—lateral movement, accessed data, and failed security controls.

### 3. Resolution
- **Immediate Containment:** Isolate affected systems and block malicious traffic.
- **Eradication:** Remove malware, disable compromised accounts, patch vulnerabilities, update firewall/IPS rules.
- **Recovery:** Restore systems from clean backups and resume normal services.
- **Verification:** Monitor for recurring suspicious activity.
- **Prevention:** Implement proactive measures like security awareness training, configuration hardening, and detection rule updates.

---

## c. Example Ticket Closure Documentation

```text
Ticket ID: INC-2026-001
Incident Type: Malware Infection (Ransomware Variant)
Reported By: Endpoint Detection System

Analysis Summary:
- Initial alert: unusual file encryption activity.
- Correlated with email gateway logs: phishing email with malicious attachment.
- Malware executed, attempted lateral movement to shared drives.

Root Cause:
- User opened malicious attachment; endpoint antivirus lacked signature for this variant.

Actions Taken:
1. Isolated infected system from network.
2. Terminated malicious processes.
3. Removed malware and restored files from clean backup.
4. Updated endpoint protection signatures.
5. Blocked phishing email source in email gateway.

Lessons Learned:
- Conduct phishing awareness training.
- Implement stricter attachment policies and email filtering.
- Enhance endpoint monitoring for anomalous file activity.

Status: Closed
Time to Resolve: 4 hours
MTTR Impact: Monitored for recurrence; metrics updated in SOC reporting dashboard.
