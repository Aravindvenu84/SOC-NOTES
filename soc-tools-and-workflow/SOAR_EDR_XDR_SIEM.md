🔹 1. SIEM (Security Information and Event Management)

SIEM is the central log collection and analysis system of a SOC.

It gathers logs from:

Servers

Firewalls

Endpoints

Network devices

Cloud services

Applications

The SIEM then correlates events and detects suspicious behavior using rules and analytics.

What SIEM does:

Collects logs from all systems

Stores and indexes data

Runs detection rules

Generates alerts

Supports investigations and compliance

Example tools: Splunk, IBM QRadar, Elastic SIEM, Microsoft Sentinel

Think of SIEM as the brain of the SOC.

🔹 2. SOAR (Security Orchestration, Automation and Response)

SOAR is used after an alert is generated.
It automates how analysts respond to incidents.

Instead of manually:

Blocking IPs

Disabling users

Sending emails

Creating tickets

SOAR does these automatically using playbooks.

What SOAR does:

Automates incident response

Connects multiple security tools

Runs workflows

Reduces analyst workload

Speeds up containment

Example tools: Splunk SOAR, Palo Alto XSOAR, Tines

Think of SOAR as the SOC’s autopilot.

🔹 3. EDR (Endpoint Detection and Response)

EDR protects and monitors individual devices like:

Laptops

Servers

Workstations

It watches:

Running processes

File changes

Registry edits

Network activity

EDR can detect malware, ransomware, and suspicious behavior on a single machine.

What EDR does:

Monitors endpoints

Detects attacks

Allows isolation of infected machines

Provides forensic data

Example tools: CrowdStrike Falcon, Microsoft Defender for Endpoint, SentinelOne

Think of EDR as a security camera on each computer.

🔹 4. XDR (Extended Detection and Response)

XDR is an evolution of EDR.
It collects and correlates data from:

Endpoints

Network

Email

Cloud

Firewalls

Identity systems

XDR gives a full attack story instead of isolated alerts.

What XDR does:

Correlates data from many sources

Detects complex attacks

Provides one unified view

Reduces alert noise

Example tools: Palo Alto Cortex XDR, Microsoft Defender XDR

Think of XDR as EDR + SIEM combined with intelligence.

🧠 How They Work Together in a SOC

EDR/XDR detect activity on systems

SIEM collects logs and creates alerts

SOAR automatically responds

Together they form a complete security workflow.

📊 Comparison Table

| Feature             | SIEM                     | SOAR               | EDR                 | XDR                         |
| ------------------- | ------------------------ | ------------------ | ------------------- | --------------------------- |
| Main Role           | Log analysis & detection | Automated response | Endpoint protection | Unified detection           |
| Data Source         | Logs from all systems    | Alerts & tools     | Endpoints           | Endpoints + Network + Cloud |
| Detects Attacks     | Yes                      | No                 | Yes                 | Yes                         |
| Responds to Attacks | No (manual)              | Yes (automated)    | Yes (on endpoint)   | Yes (across systems)        |
| Automation          | Low                      | High               | Medium              | High                        |
| Scope               | Organization-wide        | SOC operations     | Single devices      | Entire infrastructure       |


🧾 Summary

SIEM finds threats by analyzing logs

SOAR responds to threats automatically

EDR protects individual computers

XDR provides full visibility across the entire environment

A modern SOC uses all four together to achieve fast, accurate, and automated security.
