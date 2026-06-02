# Module 1 — Introduction to Microsoft Sentinel

## Microsoft SC-200: Security Operations Analyst
---

# Module Overview

This module introduces Microsoft Sentinel, Microsoft's cloud-native Security Information and Event Management (SIEM) and Security Orchestration, Automation and Response (SOAR) platform.

Microsoft Sentinel enables organizations to:

* Collect security telemetry
* Detect threats
* Investigate incidents
* Automate response actions
* Perform threat hunting
* Centralize security operations

Unlike traditional SIEM platforms that require on-premises infrastructure, Sentinel is delivered as a fully managed cloud service through Microsoft Azure.

---

# 1. What is Microsoft Sentinel?

## Definition

Microsoft Sentinel is Microsoft's cloud-native SIEM and SOAR platform designed to provide end-to-end security operations capabilities.

Sentinel allows security teams to:

```text
Collect Data
      ↓
Detect Threats
      ↓
Investigate Incidents
      ↓
Respond to Attacks
      ↓
Automate Security Workflows
```

---

# Why Sentinel Exists

Modern organizations generate massive amounts of security telemetry from:

* Endpoints
* Servers
* Identity Systems
* Network Devices
* Cloud Platforms
* Security Tools

Without centralized visibility, security teams struggle to:

* Detect threats quickly
* Correlate events
* Investigate incidents
* Respond effectively

Microsoft Sentinel addresses these challenges through centralized cloud-based security operations.

---

# 2. SIEM Capabilities

## What is SIEM?

SIEM stands for:

> Security Information and Event Management

A SIEM platform collects, analyzes, and correlates security events across an organization.

---

# Core SIEM Functions

| Function          | Purpose                    |
| ----------------- | -------------------------- |
| Log Collection    | Gather security data       |
| Event Correlation | Connect related events     |
| Alerting          | Detect suspicious activity |
| Investigation     | Support analyst workflows  |
| Reporting         | Provide visibility         |
| Threat Detection  | Identify attacks           |

---

# Data Sources Supported by Sentinel

Microsoft Sentinel can ingest data from:

### Microsoft Ecosystem

* Microsoft Defender XDR
* Microsoft Entra ID
* Microsoft 365
* Azure Resources
* Microsoft Defender Products

### Third-Party Sources

* Firewalls
* IDS/IPS Solutions
* EDR Platforms
* Linux Systems
* Windows Servers
* Security Appliances

### Multi-Cloud Sources

* AWS
* Google Cloud Platform (GCP)
* Azure

---

# SOC Perspective

Sentinel acts as a:

> Central Security Data Hub

allowing analysts to investigate threats across multiple environments from a single platform.

---

# 3. SOAR Capabilities

## What is SOAR?

SOAR stands for:

> Security Orchestration, Automation and Response

SOAR helps security teams automate repetitive tasks and improve response speed.

---

# Typical SOAR Activities

* Alert enrichment
* Automated investigations
* Ticket creation
* Notification workflows
* Threat intelligence lookups
* Response actions

---

# Operational Workflow

```text
Alert Generated
       ↓
Automated Enrichment
       ↓
Context Collection
       ↓
Response Workflow
       ↓
Analyst Review
```

---

# Why SOAR Matters

Benefits include:

* Faster investigations
* Reduced analyst workload
* Improved consistency
* Reduced response time
* Better operational efficiency

---

# 4. Playbooks

One of the most important SC-200 concepts.

---

# What is a Playbook?

A Playbook is an automated workflow used to perform predefined security actions.

Playbooks are Microsoft's implementation of SOAR automation.

---

# Important Exam Fact

> Microsoft Sentinel Playbooks are built using Azure Logic Apps.

---

# Common Playbook Use Cases

| Use Case      | Example                   |
| ------------- | ------------------------- |
| Notifications | Send Teams/Email alerts   |
| Ticketing     | Create ServiceNow ticket  |
| Containment   | Block malicious IP        |
| Enrichment    | Query threat intelligence |
| Investigation | Gather additional context |

---

# Example Workflow

```text
Suspicious Login
        ↓
Playbook Triggered
        ↓
Threat Intelligence Lookup
        ↓
Notify SOC Team
        ↓
Create Incident Ticket
```

---

# Exam Shortcut

```text
SOAR
  ↓
Playbook
  ↓
Azure Logic Apps
```

Memorize this relationship.

---

# 5. Log Analytics Workspace

One of the most heavily tested concepts in SC-200.

---

# What is Log Analytics Workspace?

A Log Analytics Workspace is the underlying data storage platform used by Microsoft Sentinel.

---

# Relationship Between Sentinel and Log Analytics

```text
Data Sources
       ↓
Log Analytics Workspace
       ↓
Microsoft Sentinel
       ↓
Detection / Investigation / Hunting
```

---

# Workspace Responsibilities

The workspace handles:

* Data storage
* Data retention
* Query execution
* Log management
* Analytics processing

---

# Sentinel Responsibilities

Sentinel provides:

* Threat detection
* Incident management
* Threat hunting
* Security investigations
* Automation

---

# Easy Memory Trick

```text
Log Analytics Workspace
=
Storage Layer

Microsoft Sentinel
=
Security Operations Layer
```

---

# 6. Kusto Query Language (KQL)

One of the MOST IMPORTANT topics in the entire SC-200 certification.

---

# What is KQL?

Kusto Query Language (KQL) is Microsoft's query language used to search and analyze data.

---

# KQL Use Cases

Security analysts use KQL for:

* Log searching
* Threat hunting
* Incident investigation
* Data analysis
* Alert validation
* Detection creation

---

# Example KQL Query

```kql
SecurityEvent
| where EventID == 4625
```

Purpose:

Find failed login events.

---

# Why KQL Matters

Nearly every major Sentinel activity relies on KQL:

* Hunting
* Investigations
* Workbooks
* Analytics Rules
* Detection Engineering

Strong KQL skills are essential for both the exam and real-world SOC work.

---

# 7. Benefits of Microsoft Sentinel

Organizations adopt Sentinel because it provides:

### Cloud-Native Architecture

* No on-prem SIEM infrastructure
* Reduced maintenance
* Faster deployment

### Scalability

* Handles large telemetry volumes
* Supports enterprise environments

### Integration

* Deep Microsoft ecosystem integration
* Third-party connector support

### Automation

* Built-in SOAR capabilities
* Playbook automation

### Threat Detection

* Advanced analytics
* Threat intelligence integration
* Behavioral detections

---

# SOC Analyst Perspective

Sentinel allows analysts to:

* Monitor environments
* Investigate incidents
* Correlate events
* Hunt threats
* Automate responses

from a single platform.

---

# Real Enterprise Relevance

Microsoft Sentinel is commonly used for:

* SOC Operations
* Cloud Security Monitoring
* Detection Engineering
* Incident Response
* Threat Hunting
* Security Analytics

Many enterprise SOC teams use Sentinel as their primary SIEM platform.

---

# Interview-Level Questions

## Q1. What is Microsoft Sentinel?

A cloud-native SIEM and SOAR platform used for threat detection, investigation, response, and automation.

---

## Q2. Where is Sentinel data stored?

In an Azure Log Analytics Workspace.

---

## Q3. What powers Sentinel Playbooks?

Azure Logic Apps.

---

## Q4. What language is used to query Sentinel data?

Kusto Query Language (KQL).

---

## Q5. What is the difference between SIEM and SOAR?

| SIEM                       | SOAR                         |
| -------------------------- | ---------------------------- |
| Collects and analyzes data | Automates response workflows |
| Detects threats            | Responds to threats          |
| Generates alerts           | Executes actions             |

---

# Important Revision Sheet

| Concept                 | Meaning                                       |
| ----------------------- | --------------------------------------------- |
| Sentinel                | Microsoft's SIEM + SOAR                       |
| SIEM                    | Security Information & Event Management       |
| SOAR                    | Security Orchestration, Automation & Response |
| Playbook                | Automated workflow                            |
| Logic Apps              | Platform powering Playbooks                   |
| Log Analytics Workspace | Data storage layer                            |
| KQL                     | Query language for Sentinel                   |

---

# Analyst Takeaways

* Microsoft Sentinel combines SIEM and SOAR capabilities into a single platform.
* Security telemetry is stored within a Log Analytics Workspace.
* Playbooks automate security operations using Azure Logic Apps.
* KQL is the core language used for hunting, investigations, and analytics.
* Sentinel enables centralized cloud-native security operations.

---

# MOST IMPORTANT EXAM FACTS

✅ Sentinel = SIEM + SOAR

✅ Data resides in Log Analytics Workspace

✅ Playbooks use Azure Logic Apps

✅ KQL is used throughout Sentinel

✅ Sentinel is Microsoft's cloud-native security operations platform

---

# Next Module Focus

* Sentinel Architecture
* Data Connectors
* Data Ingestion
* Microsoft Security Ecosystem Integration
* Log Collection Workflows

---
