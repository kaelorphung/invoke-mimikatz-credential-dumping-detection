# Invoke-Mimikatz Credential Dumping Detection

> Purple Team lab demonstrating credential dumping with Invoke-Mimikatz on Windows 10 and the detection, analysis, and alerting of related activity using the ELK Stack.

## Overview

This project is an end-to-end **Purple Team / Detection Engineering lab** designed to simulate a credential access scenario against a Windows 10 victim machine and investigate the resulting security telemetry through a centralized SIEM environment.

The lab combines an **offensive simulation** with a **defensive detection workflow**:

```text
Kali Linux (Attacker)
        │
        │ Attack Simulation
        ▼
Windows 10 (Victim)
        │
        │ Windows Security / PowerShell Logs
        ▼
Ubuntu Server
        │
        ├── Elasticsearch
        ├── Logstash
        └── Kibana
                │
                ▼
        Log Analysis & Detection
                │
                ▼
             Alerting
```

## Lab Objectives

- Simulate credential dumping activity using Invoke-Mimikatz.
- Generate and collect relevant Windows security telemetry.
- Forward Windows logs to a centralized ELK environment.
- Analyze attacker activity through Kibana.
- Develop detection logic for suspicious PowerShell and credential-access behavior.
- Generate alerts from detected activity.
- Map observed behaviors to the MITRE ATT&CK framework.

## Lab Environment

| Machine | Role | Purpose |
|---|---|---|
| Kali Linux | Attacker | Attack simulation |
| Windows 10 | Victim | Target system and telemetry source |
| Ubuntu Server | SIEM | ELK Stack and log analysis |

### Components

- **Kali Linux**
- **Windows 10**
- **Ubuntu Server**
- **PowerShell**
- **Invoke-Mimikatz**
- **Elasticsearch**
- **Logstash**
- **Kibana**
- Windows Event Logs

## Attack Scenario

The simulated attack follows this high-level workflow:

```text
Initial Access
      │
      ▼
Command Execution
      │
      ▼
PowerShell Activity
      │
      ▼
Invoke-Mimikatz
      │
      ▼
Credential Dumping
      │
      ▼
Windows Telemetry
```

The objective of the offensive phase is to generate realistic telemetry that can subsequently be investigated from the defensive side.

> **Note:** This project is intended for authorized lab environments and security research only.

## Detection & Monitoring

The defensive side of the lab focuses on identifying suspicious activity from Windows telemetry.

### Detection workflow

```text
Windows Event Logs
        │
        ▼
Log Collection
        │
        ▼
Logstash
        │
        ▼
Elasticsearch
        │
        ▼
Kibana
        │
        ├── Search & Investigation
        ├── Detection Rules
        └── Alerting
```

The investigation focuses on indicators such as:

- Suspicious PowerShell execution
- Encoded or obfuscated PowerShell activity
- Unusual command-line behavior
- Credential-access related events
- Suspicious process execution
- Correlation between multiple Windows events

## MITRE ATT&CK Mapping

The lab can be mapped to relevant MITRE ATT&CK techniques, including:

| Technique | ID | Description |
|---|---|---|
| PowerShell | T1059.001 | Command and Scripting Interpreter: PowerShell |
| OS Credential Dumping | T1003 | Credential access through operating system credential stores |
| LSASS Memory | T1003.001 | Credential dumping from LSASS memory, where applicable |

The exact mapping depends on the telemetry and execution method observed during the lab.

## Detection Engineering

The detection phase demonstrates the transition from raw security telemetry to actionable security alerts:

```text
Raw Events
    │
    ▼
Event Analysis
    │
    ▼
Identify Suspicious Patterns
    │
    ▼
Detection Rule
    │
    ▼
Alert
    │
    ▼
Security Investigation
```

Detection rules are designed to reduce noisy events and identify activity that is more strongly associated with credential-access behavior.

## Screenshots

Screenshots and Kibana dashboards can be added here to demonstrate:

- Windows event collection
- PowerShell activity
- Elasticsearch ingestion
- Kibana searches
- Detection rules
- Triggered alerts
- Investigation timeline

## Project Structure

```text
invoke-mimikatz-credential-dumping-detection/
│
├── README.md
├── LICENSE
│
├── detection-rules/
│   └── ...
│
├── elk/
│   ├── elasticsearch/
│   ├── logstash/
│   └── kibana/
│
├── screenshots/
│   └── ...
│
└── docs/
    └── ...
```

## Skills Demonstrated

- Purple Team methodology
- Windows security monitoring
- PowerShell security analysis
- Credential Access detection
- SIEM implementation
- ELK Stack
- Log analysis
- Detection engineering
- Security alerting
- MITRE ATT&CK mapping
- Incident investigation

## Disclaimer

This project was developed for **educational purposes, authorized security testing, and isolated laboratory environments**.

Do not use the techniques demonstrated in this repository against systems without explicit authorization.

## License

This project is licensed under the **MIT License**. See [LICENSE](LICENSE) for details.
