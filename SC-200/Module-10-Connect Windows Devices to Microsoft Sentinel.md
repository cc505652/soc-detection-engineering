# Module 10 — Connect Windows Devices to Microsoft Sentinel

## Microsoft SC-200: Security Operations Analyst
---

# Module Overview

Microsoft Sentinel can collect security telemetry from Windows systems across:

* Azure Virtual Machines
* On-Premises Servers
* Hybrid Environments
* Non-Azure Virtual Machines

This telemetry is used for:

* Threat Detection
* Incident Investigation
* Threat Hunting
* Detection Engineering
* Security Monitoring

Windows systems generate some of the most valuable security data available to SOC analysts.

This module introduces:

* Azure Monitor Agent (AMA)
* Data Collection Rules (DCR)
* Sysmon
* Windows Security Events
* Windows Data Collection Architecture

---

# Why Connect Windows Devices?

Most enterprise attacks eventually touch Windows systems.

Attackers frequently perform:

* Credential Theft
* Privilege Escalation
* Lateral Movement
* Malware Execution
* Persistence Creation

Windows logs often contain evidence of these activities.

---

# Common Windows Security Events

Examples include:

### Authentication Events

* Successful Logins
* Failed Logins
* Account Lockouts

---

### Privilege Events

* Administrator Assignment
* Privilege Escalation

---

### Process Events

* PowerShell Execution
* Script Execution
* Malware Launch

---

### Service Events

* Service Creation
* Service Modification

---

### Security Auditing Events

* Policy Changes
* Security Configuration Changes

---

# SOC Perspective

Many investigations begin with:

```text
Who logged in?

What process executed?

What changed on the system?
```

Windows telemetry provides those answers.

---

# Windows Data Collection Architecture

Understanding this architecture is critical.

---

# Data Flow

```text
Windows Host
      ↓
Azure Monitor Agent (AMA)
      ↓
Data Collection Rule (DCR)
      ↓
Log Analytics Workspace
      ↓
Sentinel Tables
      ↓
KQL Queries
      ↓
Detection & Investigation
```

---

# Easy Memory Trick

```text
AMA
=
Collects Data

DCR
=
Controls Data

Workspace
=
Stores Data

Sentinel
=
Analyzes Data
```

---

# 1. Azure Windows Virtual Machines

Microsoft Sentinel can directly monitor Windows systems hosted in Azure.

---

# Benefits

* Native Azure Integration
* Simplified Deployment
* Centralized Monitoring
* Cloud-Based Management

---

# Architecture

```text
Azure Windows VM
        ↓
Azure Monitor Agent
        ↓
Data Collection Rule
        ↓
Log Analytics Workspace
        ↓
Microsoft Sentinel
```

---

# Why This Matters

Azure-native deployments require significantly less infrastructure management.

---

# SOC Perspective

Cloud-hosted Windows systems can be monitored at enterprise scale through Sentinel.

---

# 2. Non-Azure Windows Systems

Microsoft Sentinel is not limited to Azure.

It can also monitor:

* Physical Servers
* On-Premises Systems
* Hybrid Infrastructure
* VMware Environments
* Non-Azure Cloud VMs

---

# Architecture

```text
On-Prem Windows Host
          ↓
Azure Monitor Agent
          ↓
Log Analytics Workspace
          ↓
Microsoft Sentinel
```

---

# Why This Matters

Most organizations operate mixed environments.

Sentinel supports:

```text
Cloud
+
On-Premises
+
Hybrid
```

security monitoring.

---

# SOC Perspective

Attackers do not care where systems reside.

Visibility must exist everywhere.

---

# 3. Azure Monitor Agent (AMA)

One of the MOST IMPORTANT SC-200 topics.

---

# What is AMA?

AMA stands for:

> Azure Monitor Agent

---

# Purpose

Collect telemetry from systems and send it to Azure.

---

# Responsibilities

* Collect Logs
* Collect Security Events
* Collect Performance Data
* Send Telemetry to Azure

---

# Why Microsoft Uses AMA

Microsoft is modernizing its monitoring architecture.

AMA provides:

✅ Better Performance

✅ Greater Flexibility

✅ Centralized Configuration

✅ DCR Integration

---

# IMPORTANT EXAM FACT

Microsoft is moving toward:

```text
Azure Monitor Agent (AMA)
```

as the preferred monitoring agent.

---

# Think

```text
AMA
=
Modern Data Collection Agent
```

---

# SOC Perspective

AMA is becoming the standard mechanism for Windows telemetry collection.

---

# 4. Data Collection Rules (DCR)

Another extremely important SC-200 concept.

---

# What is a DCR?

DCR stands for:

> Data Collection Rule

---

# Purpose

Controls:

* What data is collected
* Which systems send data
* Where data is sent

---

# Think

```text
DCR
=
Filtering + Routing Logic
```

---

# Why DCRs Exist

Without DCRs:

* Excessive data collection
* Higher costs
* Lower signal quality

---

# Example Rules

Collect:

✅ Security Events

✅ Sysmon Logs

✅ Application Logs

---

Ignore:

❌ Unnecessary Telemetry

❌ Low-Value Events

---

# Benefits

* Cost Control
* Better Data Quality
* Reduced Noise
* Improved Efficiency

---

# Architecture View

```text
Windows Device
       ↓
DCR Determines
       ↓
What Gets Collected
       ↓
What Gets Ignored
```

---

# IMPORTANT EXAM FACT

If asked:

> Which component determines what telemetry is collected?

Answer:

```text
Data Collection Rule (DCR)
```

---

# 5. Sysmon

One of the most valuable tools for threat hunting.

---

# What is Sysmon?

Sysmon stands for:

> System Monitor

Part of:

> Microsoft Sysinternals

---

# Purpose

Provides enhanced visibility beyond standard Windows Event Logs.

---

# Data Collected

### Process Creation

```text
powershell.exe
cmd.exe
rundll32.exe
```

---

### Network Connections

Outbound and inbound communication.

---

### Registry Activity

Persistence mechanisms.

---

### Driver Loading

Kernel-level activity.

---

### File Activity

File creation and modification.

---

# Think

```text
Windows Logs
      +
Sysmon
      =
Better Visibility
```

---

# Why Sysmon Matters

Default Windows logging often lacks:

* Process Context
* Detailed Activity
* Attacker Visibility

Sysmon fills these gaps.

---

# Common Threat Hunting Use Cases

### Suspicious PowerShell

```text
Encoded Commands
Download Cradles
Execution Activity
```

---

### Credential Dumping

```text
Mimikatz Activity
LSASS Access
```

---

### Malware Analysis

```text
Process Trees
Network Activity
File Changes
```

---

### Lateral Movement

```text
Remote Execution
Authentication Activity
```

---

# SOC Perspective

Many detection engineers build rules specifically around Sysmon telemetry.

---

# 6. Security Monitoring Workflow

A common real-world architecture.

---

# Investigation Flow

```text
Windows Device
        ↓
Security Event
        ↓
AMA
        ↓
Log Analytics Workspace
        ↓
SecurityEvent Table
        ↓
KQL Query
        ↓
Alert / Investigation
```

---

# Why This Matters

This workflow powers:

* Security Monitoring
* Threat Hunting
* Incident Response
* Detection Engineering

---

# Real Enterprise Relevance

Windows telemetry supports:

* SOC Operations
* Threat Hunting
* Malware Investigations
* Incident Response
* Detection Engineering
* Security Analytics

Most enterprise SOCs rely heavily on:

* Windows Event Logs
* Sysmon Data
* AMA Collection
* DCR Configuration

for day-to-day investigations.

---

# Interview-Level Questions

## Q1. What is Microsoft's preferred monitoring agent?

Azure Monitor Agent (AMA).

---

## Q2. What determines what telemetry is collected?

Data Collection Rules (DCRs).

---

## Q3. What is Sysmon?

A Sysinternals tool that provides enhanced Windows telemetry.

---

## Q4. Why use Sysmon?

To gain greater visibility than standard Windows Event Logs provide.

---

## Q5. Can Sentinel monitor non-Azure Windows systems?

Yes.

Through agent-based collection.

---

# Important Revision Sheet

| Concept       | Purpose               |
| ------------- | --------------------- |
| AMA           | Collects Telemetry    |
| DCR           | Controls Collection   |
| Sysmon        | Enhanced Visibility   |
| Workspace     | Stores Data           |
| Sentinel      | Investigates Data     |
| SecurityEvent | Windows Security Logs |

---

# Quick Recall Sheet

```text
Windows Host
↓
AMA
↓
DCR
↓
Workspace
↓
Sentinel

AMA
→ Collects Data

DCR
→ Controls Data

Sysmon
→ Enhanced Visibility
```

---

# MOST IMPORTANT EXAM FACTS

✅ Azure Monitor Agent (AMA) is Microsoft's preferred monitoring agent.

✅ Data Collection Rules (DCRs) determine what telemetry is collected.

✅ Sysmon provides enhanced Windows visibility beyond standard event logs.

✅ Sentinel can monitor Azure, on-premises, and hybrid Windows systems.

✅ Sysmon is part of Microsoft Sysinternals.

---

# Analyst Takeaways

* Windows systems provide critical telemetry for security investigations.
* AMA is the modern Microsoft monitoring agent.
* DCRs control data collection and cost optimization.
* Sysmon greatly enhances threat hunting capabilities.
* Understanding the Windows telemetry pipeline is essential for both Sentinel operations and the SC-200 exam.

---

# Next Module Focus

* Windows Security Event Collection
* Security Event Tables
* Event IDs
* Data Collection Strategies
* KQL-Based Investigations

---
