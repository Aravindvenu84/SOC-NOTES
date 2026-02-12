# Sigma Rules: Structure, Universal Detection Format, and SIEM Conversion

## Introduction

Sigma is an open-source, vendor-neutral rule format designed to describe log-based detection logic in a standardized and portable way. It allows security analysts to write detection rules once and convert them into queries compatible with multiple Security Information and Event Management (SIEM) platforms. Sigma plays a critical role in detection engineering, threat hunting, and SOC operations.

---

## Structure and Logical Design of Sigma Rules

Sigma rules are written in YAML format and follow a structured layout that separates metadata, log source definition, detection logic, and severity level.

### General Structure of a Sigma Rule

```yaml
title: Rule Title
id: unique-rule-id
status: experimental
description: Description of what the rule detects
author: Analyst Name
date: 2026-02-12
logsource:
  product: windows
  service: security
detection:
  selection:
    EventID: 4688
    CommandLine|contains: "powershell"
  condition: selection
level: high
```

### Core Components

**Metadata Section**

This section provides contextual information about the rule. Common fields include:

- `title`
- `id`
- `status`
- `description`
- `author`
- `date`
- `references`
- `tags`

The metadata ensures documentation, traceability, and rule management.

**Logsource Section**

The `logsource` field specifies where the log data originates. It defines the product, service, or category the rule applies to.

Examples:

- `product: windows`
- `service: security`
- `category: process_creation`

This ensures that the detection logic is applied only to relevant logs.

**Detection Section**

The `detection` block defines the matching logic.

Example:

```yaml
detection:
  selection:
    EventID: 4688
    CommandLine|contains: "powershell"
  condition: selection
```

The detection section typically contains:

- `selection` (matching criteria)
- `filter` (optional exclusion logic)
- `condition` (logical expression combining selections)

Supported operators include:

- `|contains`
- `|startswith`
- `|endswith`
- `|all`
- `|re`
- Boolean operators such as `and`, `or`, and `not`

**Level Field**

Defines the severity classification of the detection:

- low
- medium
- high
- critical

---

## Sigma as a Universal Detection Language

Sigma acts as a universal abstraction layer for detection logic. Instead of writing platform-specific queries, analysts define detection rules in Sigma’s standardized YAML format.

Without Sigma, separate queries must be written for:

- Splunk (SPL)
- Elastic (Query DSL)
- Microsoft Sentinel (KQL)
- IBM QRadar (AQL)

With Sigma, one rule can be converted into multiple SIEM-specific formats using automated conversion tools.

### Advantages of Universal Format

- Vendor neutrality
- Cross-platform portability
- Standardized detection sharing
- Faster integration of threat intelligence
- Centralized detection engineering

Sigma improves collaboration between security teams by providing a common detection language independent of SIEM vendor.

---

## Sample Sigma Rule with Explanation

### Example: Detection of Suspicious Encoded PowerShell Execution

```yaml
title: Suspicious PowerShell Encoded Command Execution
id: 123e4567-e89b-12d3-a456-426614174000
status: experimental
description: Detects PowerShell execution using encoded command parameter
author: MG 450Z
date: 2026-02-12
logsource:
  product: windows
  service: security
detection:
  selection:
    EventID: 4688
    NewProcessName|endswith: "powershell.exe"
    CommandLine|contains: "-enc"
  condition: selection
level: high
```

### Explanation of the Rule

This rule monitors Windows Security Event ID 4688, which corresponds to process creation events. It filters for processes where:

- The executable name ends with `powershell.exe`
- The command line contains the encoded execution flag

Encoded PowerShell commands are frequently used in malicious activities to obfuscate payload content. By correlating process creation with encoded execution behavior, this rule helps identify suspicious or potentially malicious activity.

The severity level is set to high due to the common association between encoded PowerShell commands and malware execution techniques.

---

## Conversion of Sigma Rules for Different SIEM Platforms

Sigma rules are converted into SIEM-specific queries using tools such as the Sigma CLI or `sigmac`. These tools translate the YAML-based rule into the query language of the target platform.

### Example Conversion Command

```bash
sigma convert -t splunk suspicious_powershell.yml
```

This command converts the Sigma rule into a Splunk SPL query.

### Supported Target Platforms

Sigma rules can be converted into:

- Splunk (SPL)
- Elastic (Elasticsearch DSL)
- Microsoft Sentinel (KQL)
- IBM QRadar (AQL)
- ArcSight
- Logpoint

### Conversion Workflow

1. Write detection logic in Sigma YAML format.
2. Use the Sigma conversion tool.
3. Specify the target SIEM platform.
4. Deploy the generated query into the SIEM.

This approach allows organizations to maintain a single detection standard while supporting multiple log management systems.

---

## Conclusion

Sigma provides a structured and standardized method for writing log-based detection rules. Its YAML-based format clearly separates metadata, log source definition, and detection logic. By acting as a universal detection language, Sigma enables cross-platform compatibility and simplifies detection engineering across different SIEM technologies. The ability to convert Sigma rules into platform-specific queries makes it an essential tool for modern SOC environments.

