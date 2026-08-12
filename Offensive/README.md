# Offensive Phase

## Overview

This phase simulates the offensive side of the lab using Kali Linux against a Windows 10 victim machine.

The objective is to generate realistic security telemetry associated with PowerShell execution and credential-access activity for subsequent defensive analysis.

## Lab Flow

```text
Kali Linux
    │
    │ Attack Simulation
    ▼
Windows 10
    │
    ▼
PowerShell Activity
    │
    ▼
Invoke-Mimikatz
    │
    ▼
Credential Access
```

## Attack Environment

| Machine    | Role     |
| ---------- | -------- |
| Kali Linux | Attacker |
| Windows 10 | Victim   |

## Attack Scenario

The offensive phase consists of:

1. Establishing access to the Windows 10 victim in the isolated lab environment.
2. Executing PowerShell-based activity.
3. Simulating credential-access activity using Invoke-Mimikatz.
4. Generating Windows telemetry that can be investigated from the defensive side.

## Evidence

Screenshots documenting the offensive phase are stored in this directory.

> All activities are performed in an isolated and authorized laboratory environment.

