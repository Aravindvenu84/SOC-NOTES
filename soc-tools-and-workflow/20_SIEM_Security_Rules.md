# SIEM Detection Rule Logics

## Introduction
This document contains common SIEM detection rule logics used in a Security Operations Center (SOC) to identify suspicious and malicious activities across endpoints, networks, and user accounts.

---

## Detection Rules

### 1. Brute Force Login
If a single IP generates more than 10 failed login attempts on the same user within 5 minutes, trigger an alert.

---

### 2. Password Spraying
If a single IP attempts to log in to more than 20 different user accounts within 10 minutes, generate an alert.

---

### 3. Multiple Account Lockouts
If 5 or more user accounts are locked out from the same IP address within 10 minutes, raise an alert.

---

### 4. Suspicious Login Time
If a user logs in outside normal business hours and has never logged in during that time before, trigger an alert.

---

### 5. Impossible Travel
If a user logs in from two different countries within 1 hour, generate an alert.

---

### 6. Admin Login from New IP
If an administrator account logs in from a new or unknown IP address, raise an alert.

---

### 7. Privilege Escalation
If a standard user account is added to the Administrator or Root group, trigger an alert.

---

### 8. New User Creation
If a new user account is created on a critical server, generate an alert.

---

### 9. Disabled Account Activity
If a disabled or terminated user account attempts to log in, raise an alert.

---

### 10. Malware Execution
If an endpoint runs a file that matches a known malicious hash, generate a high-severity alert.

---

### 11. Suspicious PowerShell Execution
If PowerShell is executed with base64-encoded or obfuscated commands, raise an alert.

---

### 12. Hacking Tool Detected
If tools such as Mimikatz, Nmap, or Metasploit are executed, trigger an alert.

---

### 13. Data Exfiltration
If a system uploads more than 1 GB of data to an external IP address within 10 minutes, raise an alert.

---

### 14. USB Data Copy
If sensitive files are copied to a removable USB device, trigger an alert.

---

### 15. Port Scanning
If a single IP connects to more than 50 ports on the same host within 2 minutes, generate an alert.

---

### 16. Lateral Movement
If a workstation connects to more than 10 internal systems using SMB or RDP within 5 minutes, raise an alert.

---

### 17. Ransomware Behavior
If a system rapidly renames or encrypts hundreds of files in a short period, generate an alert.

---

### 18. Firewall Attack Detection
If a firewall blocks more than 100 connection attempts from the same IP within 10 minutes, raise an alert.

---

### 19. Malicious Email Attachment
If an email attachment matches a known malware signature, trigger an alert.

---

### 20. Threat Intelligence Match
If any IP address, domain, or file hash matches a threat intelligence feed, generate a high-priority alert.

---

## Summary
These detection rule logics help SOC teams identify common cyberattacks such as brute force, malware infections, insider threats, and data exfiltration. Using these rules in a SIEM allows organizations to detect and respond to threats quickly and effectively.

# SOC Detection Rules – Brute Force, Phishing, Privilege Escalation & Malware

## Introduction
This document defines common SIEM detection rules used to identify real-world cyberattacks. Each rule includes its log source, detection condition, alert criteria, and purpose.

---

## 1. Brute Force Login Attack
**Log Source:** Windows Security Logs, Linux Auth Logs, AD Logs  

**Detection Condition:**  
If a single IP generates more than 10 failed login attempts on the same user within 5 minutes.

**Alert Criteria:**  
Trigger a high-severity alert when the threshold is reached.

**Purpose:**  
Detects password-guessing attacks attempting to break into user accounts.

---

## 2. Password Spraying
**Log Source:** Active Directory, VPN, Cloud Authentication Logs  

**Detection Condition:**  
If one IP attempts to log in to more than 20 different user accounts within 10 minutes.

**Alert Criteria:**  
Generate an alert when multiple accounts are targeted.

**Purpose:**  
Identifies attacks where one password is tested against many users.

---

## 3. Phishing Email Detected
**Log Source:** Email Security Gateway, Microsoft 365, Mail Server Logs  

**Detection Condition:**  
If an email contains a malicious URL or malware attachment.

**Alert Criteria:**  
Trigger alert when email reputation or hash matches a known threat.

**Purpose:**  
Detects phishing emails attempting to infect users or steal credentials.

---

## 4. Suspicious Link Click
**Log Source:** Web Proxy, Endpoint, Email Logs  

**Detection Condition:**  
If a user clicks a URL that matches a known phishing domain.

**Alert Criteria:**  
Generate an alert for user exposure.

**Purpose:**  
Detects users who interacted with phishing emails.

---

## 5. Privilege Escalation
**Log Source:** Active Directory, Windows Security Logs  

**Detection Condition:**  
If a standard user is added to an Administrator or Domain Admin group.

**Alert Criteria:**  
Raise a high-priority alert.

**Purpose:**  
Detects attackers gaining higher system privileges.

---

## 6. Unauthorized Admin Login
**Log Source:** AD Logs, VPN Logs  

**Detection Condition:**  
If an admin logs in from an unknown IP or new country.

**Alert Criteria:**  
Trigger alert on unusual admin activity.

**Purpose:**  
Detects possible admin account compromise.

---

## 7. Malware Execution
**Log Source:** EDR, Antivirus, Endpoint Logs  

**Detection Condition:**  
If a file executed matches a known malicious hash.

**Alert Criteria:**  
Generate critical alert.

**Purpose:**  
Detects active malware infections.

---

## 8. Suspicious PowerShell Command
**Log Source:** Windows Event Logs, EDR  

**Detection Condition:**  
If PowerShell runs base64-encoded or obfuscated commands.

**Alert Criteria:**  
Raise an alert.

**Purpose:**  
Detects malware and attacker scripts.

---

## 9. Malicious File Download
**Log Source:** Proxy Logs, EDR  

**Detection Condition:**  
If an executable file is downloaded from an untrusted domain.

**Alert Criteria:**  
Trigger alert.

**Purpose:**  
Detects malware delivery.

---

## 10. Lateral Movement
**Log Source:** Firewall, EDR, Windows Logs  

**Detection Condition:**  
If one system connects to more than 10 internal hosts via RDP or SMB within 5 minutes.

**Alert Criteria:**  
Raise an alert.

**Purpose:**  
Detects attackers spreading across the network.

---

## Summary
These detection rules cover common attacks such as brute force, phishing, privilege escalation, and malware. By monitoring logs from endpoints, email systems, and identity platforms, the SIEM can identify threats early and enable SOC teams to respond quickly.
