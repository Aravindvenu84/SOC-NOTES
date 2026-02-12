# Log Sources and Log Integration in a SOC

## Introduction
Logs are the foundation of any Security Operations Center (SOC). They provide visibility into what is happening across the organization’s infrastructure. By collecting and analyzing logs from different systems, SOC teams can detect security incidents, investigate threats, and respond effectively.

---

## Types of Log Sources

### Firewalls
Firewalls generate logs about allowed and blocked network traffic. These logs help detect suspicious connections, malware communication, and unauthorized access attempts.

### Endpoints
Endpoints such as laptops, servers, and workstations generate logs related to processes, file activity, logins, and system changes. These logs help detect malware, insider threats, and compromised systems.

### Servers
Servers generate logs related to operating systems, applications, databases, and authentication. These logs are useful for detecting attacks, system misuse, and service failures.

---

## Log Integration Methods

### Syslog
Syslog is a standard protocol used to send logs from network devices, Linux servers, and security tools to a central log server or SIEM.

Used for:
- Firewalls  
- Routers  
- Linux servers  
- Network devices  

### Agent-Based Integration
In this method, a software agent is installed on the system to collect and forward logs to the SIEM.

Used for:
- Windows systems  
- Endpoints  
- Application servers  

Examples: Splunk Universal Forwarder, Beats Agent

### API-Based Integration
APIs are used to pull logs from cloud services, SaaS applications, and security tools.

Used for:
- Cloud platforms (AWS, Azure)  
- Email systems  
- Security tools  
- Web applications  

---

## Log Parsing and Normalization
Before logs can be analyzed, they must be converted into a standard format.

### Parsing
Parsing extracts important fields from raw logs such as:
- Timestamp  
- IP address  
- Username  
- Action  
- Event type  

### Normalization
Normalization converts logs from different sources into a common structure so they can be searched and correlated easily in a SIEM.

This allows analysts to compare events from firewalls, servers, and endpoints using the same field names.

---

## Step-by-Step Log Integration Workflow

1. A device (firewall, server, or endpoint) generates a log  
2. The log is sent using Syslog, Agent, or API  
3. The SIEM receives the raw log  
4. The log is parsed to extract useful fields  
5. The log is normalized into a common format  
6. The SIEM stores and indexes the log  
7. Detection rules analyze the log  
8. Alerts are generated if suspicious activity is found  

---

## Summary
Firewalls, endpoints, and servers generate different types of logs. These logs are collected using Syslog, agents, or APIs. Before analysis, logs are parsed and normalized so they can be easily searched and correlated. This log integration process allows SOC teams to detect threats and respond quickly.
