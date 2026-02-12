# Security Log Sources and Their Role in Attack Detection

## Introduction

Effective threat detection in a SOC depends on collecting and analyzing logs from multiple infrastructure layers. Each log source provides visibility into specific attack techniques and adversary behaviors. This document identifies key enterprise log sources and explains what types of attacks they help detect.

Covered log sources:

- Firewalls  
- IDS/IPS  
- Active Directory (AD)  
- Web Servers  
- VPN  
- Endpoints  

---

# Log Sources and Detection Capabilities

## Summary Table

| Log Source      | Example Log Types | Attack Types Detected | Detection Use Cases |
|---------------|-------------------|----------------------|--------------------|
| Firewall Logs | Traffic logs, NAT logs, connection logs, deny logs | Port scanning, C2 communication, data exfiltration, lateral movement | Blocked outbound connections to malicious IPs, unusual inbound traffic |
| IDS/IPS Logs | Signature alerts, anomaly alerts, protocol violations | Exploitation attempts, malware traffic, SQL injection, buffer overflow | Detection of known exploit signatures and suspicious network payloads |
| Active Directory Logs | Event IDs (4624, 4625, 4720, 4732, 4672) | Brute force, privilege escalation, account compromise, Kerberoasting | Multiple failed logins, abnormal admin account activity |
| Web Server Logs | Access logs, error logs, HTTP request logs | SQL injection, XSS, directory traversal, web shell activity | Suspicious URL patterns, abnormal HTTP methods |
| VPN Logs | Authentication logs, session logs, IP assignment logs | Credential stuffing, account takeover, suspicious remote access | Login from unusual geography, concurrent sessions |
| Endpoint Logs | Process logs, file integrity logs, registry changes, EDR alerts | Malware execution, ransomware, persistence mechanisms | Suspicious process spawning, file encryption patterns |

---

# Detailed Breakdown by Log Source

## 1. Firewall Logs

### Log Content

- Source and destination IP
- Port and protocol
- Action (allow/deny)
- Session duration
- NAT translations

### Attacks Detected

- Port scanning
- Command-and-Control (C2) communication
- Data exfiltration
- Unauthorized inbound access
- Lateral movement attempts

### Example Detection

- Multiple denied connections from one external IP to sequential ports indicates reconnaissance.
- Internal host communicating with known malicious IP indicates possible malware infection.

---

## 2. IDS/IPS Logs

### Log Content

- Signature match alerts
- Anomaly detection alerts
- Protocol violations
- Payload inspection details

### Attacks Detected

- Exploit attempts (e.g., CVE exploitation)
- SQL injection
- Cross-site scripting (XSS)
- Buffer overflow attempts
- Malware traffic patterns

### Example Detection

- IDS alert triggered by known exploit signature targeting Apache server.
- IPS blocking malicious payload in HTTP request.

---

## 3. Active Directory Logs

### Common Event IDs

- 4624: Successful logon
- 4625: Failed logon
- 4672: Special privileges assigned
- 4720: User account created
- 4732: User added to group

### Attacks Detected

- Brute force login attempts
- Credential stuffing
- Privilege escalation
- Account creation abuse
- Kerberoasting
- Pass-the-Hash attacks

### Example Detection

- Multiple failed logins followed by a successful login from same IP.
- Non-admin account added to Domain Admins group.

---

## 4. Web Server Logs

### Log Content

- Client IP
- HTTP method (GET, POST, PUT)
- URL requested
- Response code
- User agent

### Attacks Detected

- SQL injection
- Cross-site scripting (XSS)
- Directory traversal
- Web shell uploads
- Brute force login attempts

### Example Detection

- URL containing `' OR 1=1 --` indicates SQL injection attempt.
- Repeated 401 responses suggest brute force attempt.

---

## 5. VPN Logs

### Log Content

- User authentication attempts
- Source IP address
- Login success/failure
- Session start and end time
- Assigned internal IP

### Attacks Detected

- Credential compromise
- Account takeover
- Impossible travel scenario
- Suspicious remote access
- Brute force against VPN portal

### Example Detection

- Login from India followed by login from Europe within 10 minutes.
- Multiple failed VPN login attempts from single external IP.

---

## 6. Endpoint Logs

### Log Content

- Process creation events
- File modifications
- Registry changes
- Network connections from host
- EDR alerts

### Attacks Detected

- Malware execution
- Ransomware encryption behavior
- Persistence mechanisms
- Privilege escalation
- Lateral movement

### Example Detection

- Suspicious PowerShell execution spawning cmd.exe.
- Large number of file modifications within short timeframe indicates ransomware.

---

# Cross-Correlation Importance

No single log source provides complete visibility. Effective detection requires correlating multiple logs:

Example Scenario:

1. Firewall logs show outbound traffic to malicious IP.
2. Endpoint logs show suspicious PowerShell execution.
3. AD logs show privilege escalation event.

Combined analysis confirms a compromise and lateral movement.

---

# Conclusion

Each log source contributes unique visibility:

- Firewalls provide network boundary visibility.
- IDS/IPS detects known exploit patterns.
- Active Directory logs reveal authentication and privilege abuse.
- Web server logs detect application-layer attacks.
- VPN logs expose remote access abuse.
- Endpoint logs reveal host-level compromise.

A mature SOC integrates all these log sources into a SIEM to enable comprehensive detection, correlation, and rapid incident response.
