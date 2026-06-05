# Module 8 — Connect Microsoft 365 and Azure Services

## Microsoft SC-200: Security Operations Analyst
---

# Module Overview

Microsoft Sentinel includes native integrations with Microsoft security products and Azure services.

These built-in connectors allow organizations to ingest:

* Security Alerts
* Security Events
* Authentication Activity
* Endpoint Telemetry
* Cloud Security Data
* Administrative Activity

into Microsoft Sentinel.

Because these products are part of the Microsoft security ecosystem, integration is often simpler and more feature-rich than many third-party connectors.

---

# 1. Why Microsoft Connectors Matter

Microsoft Sentinel is designed to act as a centralized security operations platform.

To achieve this, Sentinel must collect data from:

* Endpoints
* Identity Systems
* Email Platforms
* Cloud Applications
* Azure Resources

---

# Security Operations Flow

```text id="m7y4np"
Microsoft Service
        ↓
Data Connector
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

# SOC Perspective

Microsoft security products often generate some of the highest-value telemetry available to analysts.

Examples:

* Authentication Activity
* Endpoint Alerts
* Email Threats
* Cloud App Activity

Without connectors, Sentinel cannot access this information.

---

# Think

```text id="g8t1vq"
No Connector
      =
No Visibility
```

---

# 2. Microsoft Defender for Endpoint Connector

One of the most important Sentinel integrations.

---

# Purpose

Provides visibility into endpoint activity.

---

# Data Collected

* Endpoint Telemetry
* Device Events
* Security Alerts
* Malware Activity
* Process Activity
* Endpoint Threat Intelligence

---

# Common Use Cases

* Malware Investigations
* Threat Hunting
* Incident Response
* Endpoint Security Monitoring

---

# SOC Perspective

Defender for Endpoint provides many of the tables used during endpoint investigations, including:

```text id="q3n6wk"
DeviceEvents

DeviceLogonEvents
```

---

# Security Value

Provides deep visibility into attacker activity occurring on endpoints.

---

# 3. Microsoft Defender for Identity Connector

Provides visibility into identity-related security events.

---

# Data Collected

* Authentication Activity
* Identity Alerts
* Suspicious Sign-ins
* Privileged Account Activity

---

# Common Use Cases

* Identity Investigations
* Credential Theft Detection
* Lateral Movement Analysis
* Authentication Monitoring

---

# SOC Perspective

Identity is frequently the primary target during attacks.

Monitoring identity telemetry is critical.

---

# Think

```text id="r2w7oe"
Defender for Identity
=
Identity Visibility
```

---

# 4. Microsoft Defender for Office 365 Connector

Provides email security telemetry.

---

# Data Collected

* Email Security Alerts
* Phishing Activity
* Malware Attachments
* Suspicious URLs
* Email Threat Intelligence

---

# Common Use Cases

* Phishing Investigations
* Email Threat Hunting
* User Awareness Analysis
* Business Email Compromise (BEC)

---

# Security Insight

Email remains one of the most common attack vectors.

This connector helps security teams identify:

* phishing attempts
* malicious attachments
* suspicious email activity

---

# Think

```text id="x4c2kb"
Defender for Office 365
=
Email Security
```

---

# 5. Microsoft Defender for Cloud Apps Connector

Provides cloud application visibility.

---

# Data Collected

* SaaS Activity
* User Behavior
* Cloud Application Events
* Security Alerts

---

# Common Use Cases

* Shadow IT Discovery
* SaaS Monitoring
* Cloud Threat Detection
* User Activity Monitoring

---

# Think

```text id="p5z9hm"
Defender for Cloud Apps
=
Cloud Visibility
```

---

# Why It Matters

Modern organizations increasingly rely on:

* Microsoft 365
* SaaS Platforms
* Cloud Applications

making cloud telemetry critical.

---

# 6. Azure Service Connectors

Sentinel also integrates directly with Azure services.

---

# Common Azure Connectors

### Azure Activity Logs

Tracks:

* Administrative Actions
* Resource Changes
* Subscription Activity

---

### Azure Resource Logs

Tracks:

* Resource-Level Events
* Operational Activity
* Service Activity

---

### Azure Security Services

Examples:

* Microsoft Defender for Cloud
* Azure Security Monitoring

---

# SOC Perspective

Azure telemetry provides visibility into cloud infrastructure and administrative actions.

---

# Think

```text id="u7f1za"
Azure Connectors
=
Cloud Infrastructure Visibility
```

---

# 7. Connector Workflow

A key exam concept.

---

# Data Flow

```text id="c6j9et"
Microsoft Service
       ↓
Data Connector
       ↓
Log Analytics Workspace
       ↓
Sentinel Table
       ↓
KQL Query
       ↓
Detection
```

---

# Why This Matters

Every Sentinel activity depends on this pipeline:

* Threat Hunting
* Investigations
* Analytics Rules
* Security Monitoring

---

# EXAM FACT

Connectors ingest data.

They do NOT:

❌ Store incidents

❌ Create watchlists

❌ Replace analytics rules

---

# Think

```text id="y4x7pr"
Connector
=
Data Ingestion
```

---

# 8. Automatic Incident Creation

One of the most important concepts in this module.

---

# How It Works

Certain Microsoft security products generate alerts.

These alerts can be imported into Sentinel.

Sentinel can then automatically create incidents.

---

# Example Workflow

```text id="d8n5lf"
Defender for Endpoint
          ↓
Security Alert
          ↓
Connector
          ↓
Sentinel
          ↓
Incident Created
```

---

# Why This Matters

Analysts can investigate incidents without manually creating them.

---

# SOC Benefit

Automatic incident creation:

* Improves efficiency
* Reduces manual work
* Accelerates response

---

# Security Operations Perspective

Many enterprise SOC teams rely heavily on:

```text id="h3m8bo"
Defender Alert
       ↓
Sentinel Incident
```

workflows.

---

# Real Enterprise Relevance

Microsoft connectors are commonly used for:

* SOC Operations
* Incident Response
* Threat Hunting
* Endpoint Security
* Identity Protection
* Cloud Security Monitoring

Most organizations using Sentinel integrate multiple Microsoft security products.

---

# Interview-Level Questions

## Q1. What is the purpose of a Sentinel connector?

To ingest telemetry, alerts, and security data into Microsoft Sentinel.

---

## Q2. What does Defender for Endpoint provide?

Endpoint telemetry, alerts, and device activity.

---

## Q3. What does Defender for Identity provide?

Identity-related alerts and authentication telemetry.

---

## Q4. Can connectors automatically create incidents?

Some Microsoft security products can generate alerts that create Sentinel incidents.

---

## Q5. Do connectors store incidents?

No.

Connectors ingest data.

---

# Important Revision Sheet

| Connector               | Primary Purpose               |
| ----------------------- | ----------------------------- |
| Defender for Endpoint   | Endpoint Visibility           |
| Defender for Identity   | Identity Visibility           |
| Defender for Office 365 | Email Security                |
| Defender for Cloud Apps | Cloud Application Monitoring  |
| Azure Activity Logs     | Administrative Activity       |
| Azure Resource Logs     | Cloud Infrastructure Activity |

---

# Quick Recall Sheet

```text id="z2q8dw"
Defender for Endpoint
→ Endpoint Telemetry

Defender for Identity
→ Identity Activity

Defender for Office 365
→ Email Security

Defender for Cloud Apps
→ Cloud Monitoring

Azure Activity Logs
→ Administrative Actions

Connector
→ Data Ingestion
```

---

# MOST IMPORTANT EXAM FACTS

✅ Connectors ingest telemetry into Sentinel.

✅ Connectors do NOT store incidents.

✅ Connectors do NOT create watchlists.

✅ Defender for Endpoint = Endpoint Visibility.

✅ Defender for Identity = Identity Visibility.

✅ Defender for Office 365 = Email Security.

✅ Some Microsoft alerts can automatically create Sentinel incidents.

---

# Analyst Takeaways

* Microsoft provides native Sentinel integrations for major security products.
* Connectors enable visibility into endpoints, identities, email, and cloud services.
* Data connectors are responsible for ingestion, not storage or detection.
* Some Microsoft security alerts can automatically create Sentinel incidents.
* Understanding connector functionality is critical for Sentinel architecture and SC-200 success.

---

# Next Module Focus

* Microsoft Security Data Sources
* Connector Configuration
* Data Collection Strategies
* Sentinel Integration Architecture
* Security Monitoring Workflows

---
