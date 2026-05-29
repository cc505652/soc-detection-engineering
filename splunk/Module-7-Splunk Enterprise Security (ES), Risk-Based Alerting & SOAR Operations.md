# Module 7 — Splunk Enterprise Security (ES), Risk-Based Alerting & SOAR Operations

## Cisco Cybersecurity Defense Analyst (Splunk)
---

This module introduces the operational capabilities of:

> Splunk Enterprise Security (ES) and Splunk SOAR.

Up until now, the focus has been on:

- cybersecurity foundations
- attack frameworks
- SOC operations
- SPL querying
- threat intelligence
- SIEM concepts

This module moves into:

- Enterprise Security workflows
- Risk-Based Alerting (RBA)
- Threat Intelligence integration
- Detection management
- Security automation
- SOC investigations

This is where Splunk evolves from:

> "log analysis"

into:

> "enterprise-scale security operations."

VERY high-value module.

---

# 1. Splunk Enterprise Security (ES)

## Definition

Splunk Enterprise Security (ES) is:

> Splunk's enterprise-grade SIEM platform designed for threat detection, investigation, monitoring, and response.

---

# Core Enterprise Security Capabilities

| Capability | Purpose |
|---|---|
| Threat Detection | Identify suspicious activity |
| Investigations | Analyze security events |
| Correlation Searches | Link related events |
| Risk-Based Alerting | Prioritize threats |
| Threat Intelligence | IOC enrichment |
| Dashboards | Operational visibility |
| Incident Management | SOC investigations |

---

# Enterprise SOC Relevance

Splunk ES is commonly used by:

- SOC Analysts
- Detection Engineers
- Threat Hunters
- Security Engineers
- Incident Responders

for day-to-day security operations.

---

# 2. Common Information Model (CIM)

One of the MOST important Splunk concepts.

---

# What is CIM?

The Common Information Model (CIM) provides:

> standardized field mappings across different data sources.

---

# Example

Different products may log usernames differently:

```text
username
user
account
login_name
```

CIM normalizes them into:

```text
user
```

---

# Why CIM Matters

CIM enables:

- consistent investigations
- scalable detections
- faster searches
- reusable content
- cross-platform visibility

---

# Detection Engineering Relevance

Most enterprise detections rely heavily on:

- CIM normalization
- standardized telemetry
- consistent field structures

Without CIM:

- correlations become difficult
- detections become inconsistent
- investigations become slower

---

# 3. Data Models

## Definition

Data Models organize normalized CIM data into structured datasets.

---

# Purpose

Data Models improve:

- analytics
- reporting
- dashboards
- correlation searches
- investigations

---

# Example Data Models

| Data Model | Purpose |
|---|---|
| Authentication | Login activity |
| Endpoint | Endpoint telemetry |
| Network Traffic | Network visibility |
| Malware | Malicious activity |
| Change Analysis | System modifications |

---

# SOC Relevance

Data Models provide:

- structured searching
- efficient analytics
- faster investigations

---

# 4. Data Model Acceleration

VERY important enterprise optimization concept.

---

# Why It Exists

Enterprise environments generate:

- millions of logs
- large datasets
- high-volume telemetry

Searching raw data repeatedly becomes expensive.

---

# Acceleration Purpose

Data Model Acceleration provides:

✅ faster searches

✅ faster dashboards

✅ improved analytics

✅ better SOC responsiveness

---

# Operational Security Insight

Performance directly affects:

- investigation speed
- detection efficiency
- analyst productivity
- SOC effectiveness

---

# 5. Asset & Identity Framework

One of the most valuable investigation features in ES.

---

# Purpose

Provides context around:

- systems
- devices
- users
- service accounts

---

# Asset Examples

| Asset Type | Example |
|---|---|
| Workstation | Employee laptop |
| Server | Domain controller |
| Cloud Resource | AWS EC2 instance |
| Database Server | Production database |

---

# Identity Examples

| Identity Type | Example |
|---|---|
| Employee | Standard user |
| Administrator | Privileged account |
| Service Account | Automated processes |

---

# Why This Matters

Instead of seeing:

```text
10.10.1.25
```

Analysts can see:

```text
Finance Domain Controller
Critical Asset
```

This greatly improves:

- investigations
- prioritization
- risk assessment

---

# 6. Threat Intelligence Framework

VERY important SOC capability.

---

# Purpose

Integrates external threat intelligence into investigations.

---

# Common Threat Intelligence Sources

| Source | Purpose |
|---|---|
| Malicious IP Feeds | IOC matching |
| Domain Feeds | Phishing detection |
| URL Intelligence | Threat validation |
| Hash Feeds | Malware identification |

---

# IOC Workflow

```text
Alert
    ↓
IOC Extraction
    ↓
Threat Intel Lookup
    ↓
Context Enrichment
    ↓
Risk Assessment
```

---

# Why Threat Intelligence Matters

Threat intelligence helps analysts:

- validate alerts
- enrich investigations
- identify known threats
- prioritize incidents

---

# Operational Insight

Threat intelligence provides:

> context

rather than simply:

> raw indicators.

---

# 7. Detections in Enterprise Security

One of the MOST important concepts.

---

# What are Detections?

Detections identify:

> suspicious or malicious behavior.

---

# Detection Sources

Detections may use:

- correlation searches
- behavioral analytics
- ATT&CK techniques
- threat intelligence
- risk scoring

---

# Detection Workflow

```text
Telemetry
     ↓
Detection Logic
     ↓
Finding
     ↓
Risk Event
     ↓
Investigation
```

---

# Detection Engineering Relevance

Detection Engineers focus on:

- building detections
- tuning detections
- reducing false positives
- improving visibility

This is a highly valuable cybersecurity specialization.

---

# 8. Findings & Intermediate Findings

Enterprise Security introduces the concept of:

## Findings

A finding is:

> suspicious activity identified by a detection.

---

# Example

```text
Multiple Failed Logins
```

may generate:

```text
Finding
```

before becoming a full incident.

---

# Intermediate Findings

Intermediate findings provide:

- supporting evidence
- additional context
- investigation enrichment

before escalating into higher-risk events.

---

# Why Findings Matter

Findings allow analysts to:

- correlate events
- build risk context
- reduce false positives
- improve investigations

---

# 9. Entities

## Definition

Entities represent:

- users
- systems
- devices
- assets

inside investigations.

---

# Examples

| Entity Type | Example |
|---|---|
| User | jsmith |
| Host | HR-Laptop-01 |
| Server | DC01 |
| Cloud Asset | AWS Instance |

---

# SOC Relevance

Entities help analysts understand:

- who
- what
- where

during investigations.

---

# 10. Risk-Based Alerting (RBA)

One of the MOST valuable modern detection concepts.

---

# Traditional Alerting

```text
Event
   ↓
Alert
```

---

# Risk-Based Alerting

```text
Suspicious Activity
        ↓
Risk Score
        ↓
Additional Activity
        ↓
More Risk
        ↓
Threshold Reached
        ↓
Alert Generated
```

---

# Benefits

Risk-Based Alerting:

- reduces false positives
- improves prioritization
- increases detection fidelity
- improves SOC efficiency

---

# Why RBA Matters

Modern attackers often generate:

- low-signal activity
- weak indicators
- distributed behavior

Risk scoring helps combine multiple signals into meaningful alerts.

---

# 11. Adaptive Response Actions

Adaptive Response Actions are:

> automated actions triggered by detections.

---

# Examples

| Action | Purpose |
|---|---|
| Create Ticket | Case management |
| Send Notification | Analyst awareness |
| Run Playbook | Automation |
| IOC Enrichment | Additional context |
| Endpoint Isolation | Threat containment |

---

# Operational Security Insight

Automation helps:

- reduce analyst workload
- improve response speed
- improve SOC efficiency

---

# 12. Splunk SOAR

SOAR stands for:

> Security Orchestration, Automation and Response.

---

# Purpose

SOAR automates repetitive security tasks.

---

# Benefits

SOAR helps:

- automate investigations
- enrich alerts
- reduce manual effort
- accelerate response
- improve consistency

---

# 13. Playbooks

Playbooks are:

> automated workflows used by SOAR.

---

# Example Playbook

```text
Alert Trigger
      ↓
IOC Lookup
      ↓
Threat Intelligence Check
      ↓
Create Ticket
      ↓
Notify Analyst
```

---

# Playbook Triggers

Playbooks can be triggered by:

- detections
- notable events
- manual analyst actions
- risk events

---

# Why Playbooks Matter

Playbooks improve:

- operational efficiency
- investigation speed
- response consistency

---

# 14. Enterprise Investigation Workflow

Typical ES Investigation Process

```text
Alert
    ↓
Triage
    ↓
Review Findings
    ↓
Review Entities
    ↓
Threat Intelligence Validation
    ↓
Risk Assessment
    ↓
Investigation
    ↓
Response
```

---

# SOC Analyst Perspective

This module teaches:

> enterprise-scale security operations.

Analysts must:

- investigate efficiently
- correlate evidence
- understand risk
- leverage automation
- prioritize incidents

---

# Real Enterprise Relevance

This module directly connects to:

- Enterprise SOC Operations
- Detection Engineering
- Threat Hunting
- SIEM Engineering
- Security Automation
- Incident Response
- Cloud Security Monitoring

---

# Interview-Level Questions

## Q1. What is CIM?

A normalization framework that standardizes log data across sources.

---

## Q2. What is Risk-Based Alerting?

A detection methodology that accumulates risk scores before generating alerts.

---

## Q3. What is a Finding?

Suspicious activity identified by a detection.

---

## Q4. What is Splunk SOAR?

Security Orchestration, Automation and Response platform used to automate security workflows.

---

## Q5. Why is the Asset & Identity Framework useful?

It provides business and operational context for investigations.

---

# Important Revision Sheet

| Concept | Meaning |
|---|---|
| CIM | Common Information Model |
| Data Model | Structured normalized dataset |
| Asset Framework | System context |
| Identity Framework | User context |
| Finding | Suspicious activity |
| Entity | User/system under investigation |
| RBA | Risk-Based Alerting |
| SOAR | Security automation platform |
| Playbook | Automated workflow |

---

# Analyst Takeaways

- Enterprise Security extends Splunk into a full SIEM platform
- CIM normalization is critical for scalable detections
- Threat Intelligence provides valuable investigation context
- Risk-Based Alerting improves detection quality
- SOAR automation reduces analyst workload
- Asset & Identity Frameworks improve investigative context

---

# SOC / Splunk Relevance

Splunk ES enables analysts to:

- investigate alerts
- correlate events
- enrich findings
- prioritize risk
- automate workflows
- improve operational visibility

This module directly influences:

- Detection Engineering
- Threat Hunting
- Security Automation
- SOC Operations
- SIEM Engineering

---

# Real-World Security Connections

- Modern SOCs increasingly rely on Risk-Based Alerting
- Enterprise detections depend heavily on CIM normalization
- Threat Intelligence enrichment improves investigation quality
- SOAR automation reduces alert fatigue and analyst workload
- Detection Engineering teams frequently build ATT&CK-aligned detections

---

# Potential Detection Opportunities

Possible SOC detections related to this module:

- repeated authentication failures
- suspicious privilege escalation
- impossible travel logins
- known malicious IOC matches
- unusual administrative activity
- ATT&CK-based behavioral detections
- high-risk entity activity

---

# MOST IMPORTANT TAKEAWAY

This module introduces:

> enterprise-scale security operations and automation.

You are now learning:

- Enterprise Security workflows
- Risk-Based Alerting
- Threat Intelligence integration
- Detection management
- SOAR automation
- Enterprise investigations

This is one of the most valuable modules in the entire course and closely aligns with real-world SOC and Detection Engineering operations.

---

# Next Module Focus

- Threat Hunting Methodology
- Behavioral Analytics
- Advanced Investigations
- ATT&CK-Based Hunting
- Proactive Detection Operations

---
