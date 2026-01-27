# SOC Incident Workflow: From Alert Detection to Closure

This document describes the **full SOC workflow** from alert detection to incident closure, including roles (L1, L2, L3), detailed steps, and a workflow diagram.

---

## a. Full Workflow Overview

The SOC workflow ensures **structured handling of security incidents**:

1. **Alert Detection** – Monitoring tools generate alerts for suspicious activity.  
2. **Alert Triage & Validation** – L1 analysts review alerts to confirm legitimacy.  
3. **Incident Creation** – Valid alerts are logged as incidents in the ticketing system.  
4. **Incident Assignment** – Incidents are assigned to the appropriate analyst/team based on severity.  
5. **Investigation & Analysis** – L2 analysts perform in-depth investigation and root cause analysis.  
6. **Containment & Mitigation** – Actions taken to prevent further impact.  
7. **Eradication** – Remove threats or vulnerabilities.  
8. **Recovery** – Restore systems and verify normal operations.  
9. **Lessons Learned & Closure** – Document findings, update playbooks, close the incident.

---

## b. Step-by-Step Details

### 1. Alert Detection
- **Action:** SIEM, IDS/IPS, EDR, or NTA tools generate alerts.
- **Documentation:** Capture alert details (source, type, timestamp, affected assets).
- **Role:** L1 monitors dashboards continuously.

### 2. Alert Triage & Validation
- **Action:** Validate whether alert is real or false positive.
- **Documentation:** Update ticket with validation notes.
- **Role:** L1 filters false positives and escalates confirmed threats.

### 3. Incident Creation
- **Action:** Convert confirmed alert into an incident in the ticketing system.
- **Documentation:** Include alert source, affected assets, severity, and initial observations.
- **Role:** L1 creates and logs the incident.

### 4. Incident Assignment
- **Action:** Assign incident to L2 analyst or relevant team for investigation.
- **Documentation:** Assign priority, expected SLA, and initial instructions.
- **Role:** SOC manager or L1 assigns based on type/severity.

### 5. Investigation & Analysis
- **Action:** Examine logs, endpoint data, network traffic; identify root cause and scope.
- **Documentation:** Record investigative steps, findings, and tools used.
- **Role:** L2 performs detailed analysis; may escalate complex threats to L3.

### 6. Containment & Mitigation
- **Action:** Isolate affected systems, block malicious IPs, disable compromised accounts.
- **Documentation:** Update ticket with containment steps and current system status.
- **Role:** L2 implements containment actions; L3 advises on complex incidents.

### 7. Eradication
- **Action:** Remove malware, close vulnerabilities, revoke malicious accounts.
- **Documentation:** Document eradication steps and confirm no residual threats.
- **Role:** L2 executes eradication; L3 may perform advanced remediation.

### 8. Recovery
- **Action:** Restore systems and services to normal operations.
- **Documentation:** Confirm functionality, restore from backups if needed, monitor post-incident.
- **Role:** L2 leads recovery; L3 validates integrity for complex incidents.

### 9. Lessons Learned & Closure
- **Action:** Review incident timeline, update playbooks, close the incident ticket.
- **Documentation:** Capture lessons learned, mitigation strategies, and recommendations.
- **Role:** L3 leads lessons learned review; L1/L2 update operational procedures.

---

## c. Roles in Workflow

| Workflow Stage                  | L1 Role                       | L2 Role                        | L3 Role                          |
|---------------------------------|-------------------------------|--------------------------------|----------------------------------|
| Alert Detection                  | Monitor dashboards            | Support detection escalation    | Refine detection rules            |
| Alert Triage & Validation        | Filter false positives        | Validate complex alerts        | Provide advanced analysis guidance|
| Incident Creation                | Create tickets                | Review ticket details          | Oversight if complex              |
| Incident Assignment              | Suggest assignments           | Receive assignment             | Allocate advanced cases           |
| Investigation & Analysis         | Provide alert context         | Conduct root cause analysis    | Analyze advanced or APT attacks  |
| Containment & Mitigation         | Support notifications         | Apply containment measures     | Advise on strategic response     |
| Eradication                      | Monitor remediation           | Execute threat removal         | Perform advanced remediation      |
| Recovery                          | Assist in verification        | Restore systems                | Validate integrity and continuity|
| Lessons Learned & Closure        | Provide notes                 | Contribute insights            | Lead review and update procedures|

---

## d. Workflow Diagram

```mermaid
flowchart TD
    A[Alert Detection (L1)] --> B[Alert Triage & Validation (L1)]
    B --> C[Incident Creation (L1)]
    C --> D[Incident Assignment (L2)]
    D --> E[Investigation & Analysis (L2)]
    E --> F[Containment & Mitigation (L2/L3)]
    F --> G[Eradication (L2/L3)]
    G --> H[Recovery (L2/L3)]
    H --> I[Lessons Learned & Closure (L3)]
