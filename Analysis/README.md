# Analysis Phase

## Overview

This phase analyzes the telemetry generated during the offensive simulation and the alerts produced by the defensive environment.

The goal is to connect the observed attacker behavior with the corresponding Windows events and detection results.

## Investigation Flow

```text
Attack Activity
      │
      ▼
Windows Telemetry
      │
      ▼
ELK / Kibana
      │
      ▼
Detection Rule
      │
      ▼
Alert
      │
      ▼
Security Analysis
```

## Investigation

The analysis focuses on identifying:

* What activity occurred on the Windows 10 victim.
* Which Windows events were generated.
* What indicators were visible in the collected telemetry.
* Which detection rule identified the suspicious activity.
* How the alert relates to the simulated attack.

## MITRE ATT&CK Mapping

Relevant behaviors observed during the lab can be mapped to MITRE ATT&CK techniques.

| Technique             | ID        | Description                                                  |
| --------------------- | --------- | ------------------------------------------------------------ |
| PowerShell            | T1059.001 | Command and Scripting Interpreter: PowerShell                |
| OS Credential Dumping | T1003     | Credential access through operating system credential stores |
| LSASS Memory          | T1003.001 | Credential dumping from LSASS memory, where applicable       |

The exact mapping depends on the execution method and telemetry observed in the lab.

## Findings

This section documents the main findings from the investigation, including:

* Relevant event IDs and log sources.
* Suspicious processes or command-line activity.
* Detection rule matches.
* Triggered alerts.
* Any detection gaps or limitations.

## Conclusion

The lab demonstrates the complete workflow from simulated offensive activity to defensive detection and security analysis.

```text
Offensive Activity
       ↓
Telemetry Generation
       ↓
Log Collection
       ↓
SIEM Investigation
       ↓
Detection
       ↓
Alert
       ↓
Analysis
```

> All findings are based on activity performed within the isolated laboratory environment.
