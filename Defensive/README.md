# Defensive Phase

## Overview

This phase focuses on collecting and detecting security telemetry generated during the offensive simulation.

Windows 10 acts as the telemetry source, while the Ubuntu Server hosts the ELK Stack for centralized log ingestion, investigation, and alerting.

## Lab Flow

```text
Windows 10
    │
    │ Windows Event Logs
    ▼
Ubuntu Server
    │
    ├── Logstash
    ├── Elasticsearch
    └── Kibana
            │
            ▼
      Detection & Alerting
```

## Defensive Environment

| Machine       | Role       |
| ------------- | ---------- |
| Windows 10    | Log Source |
| Ubuntu Server | SIEM / ELK |

## Log Collection

Security telemetry generated during the attack simulation is collected from the Windows 10 victim and forwarded to the ELK environment.

The collected data provides visibility into activities such as:

* PowerShell execution
* Process creation
* Command-line activity
* Credential-access related behavior
* Other relevant Windows security events

## Detection

The collected events are investigated through Kibana to identify suspicious activity.

The detection workflow is:

```text
Raw Logs
   │
   ▼
Log Ingestion
   │
   ▼
Event Analysis
   │
   ▼
Detection Rule
   │
   ▼
Alert
```

## Detection Rules

Custom detection logic is maintained in the `rules/` directory.

The rules focus on identifying suspicious PowerShell and credential-access related activity generated during the lab.

## Evidence

Screenshots documenting log collection, Kibana investigation, detection rules, and alerts are stored in this directory.

> This detection environment is intended for authorized security research and educational purposes.
