# Module 7 — Connect Logs to Microsoft Sentinel: Data Connectors

## Microsoft SC-200: Security Operations Analyst
---

# Module Overview

Microsoft Sentinel relies entirely on security telemetry to perform:

* Threat Detection
* Incident Investigation
* Threat Hunting
* Security Monitoring
* Analytics
* Incident Response

Without data, Sentinel cannot detect threats or generate security insights.

This module introduces:

* Data Connectors
* Data Collection Architecture
* Content Hub
* Common Event Format (CEF)
* Syslog
* Connector Providers

Understanding data ingestion is fundamental to every Sentinel deployment.

---

# 1. Why Data Connectors Matter

## The Foundation of Sentinel

Microsoft Sentinel is a SIEM platform.

A SIEM is only as effective as the data it receives.

---

# Security Reality

Without logs:

❌ No alerts

❌ No investigations

❌ No threat hunting

❌ No detections

❌ No incident response

---

# Data Collection Pipeline

```text id="d0o9vz"
Data Source
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

# Think

```text id="b2v6kq"
No Data
   =
No Security Visibility
```

---

# SOC Perspective

One of the first questions analysts ask when troubleshooting Sentinel:

```text id="h0a8me"
Are the logs actually arriving?
```

because detection depends entirely on data ingestion.

---

# 2. What is a Data Connector?

## Definition

A Data Connector is a mechanism used to ingest telemetry from external systems into Microsoft Sentinel.

---

# Purpose

Data Connectors enable Sentinel to collect information from:

* Cloud Platforms
* Security Products
* Servers
* Endpoints
* Firewalls
* Identity Systems

---

# Architecture Flow

```text id="u3z2oi"
External Source
        ↓
Data Connector
        ↓
Log Analytics Workspace
        ↓
Sentinel Table
        ↓
KQL Query
```

---

# Why Connectors Matter

Data Connectors transform:

```text id="9x6nqd"
Raw Security Data
```

into:

```text id="f8v2dr"
Searchable Security Telemetry
```

inside Sentinel.

---

# 3. Data Connector Providers

Microsoft Sentinel supports a wide variety of data sources.

---

# Microsoft 365 Services

One of the most common connector categories.

---

# Examples

### Microsoft Defender for Endpoint

Provides:

* Endpoint Telemetry
* Device Events
* Security Alerts

---

### Microsoft Defender for Identity

Provides:

* Identity Activity
* Authentication Events
* Domain Controller Visibility

---

### Microsoft Defender for Office 365

Provides:

* Email Security Events
* Phishing Activity
* Mail Flow Data

---

### Microsoft Defender for Cloud Apps

Provides:

* SaaS Visibility
* User Activity
* Cloud Application Monitoring

---

# Think

```text id="a4m1sj"
Microsoft Security Products
         ↓
Native Sentinel Integration
```

---

# Azure Services

Another major data source category.

---

# Examples

### Azure Activity Logs

Tracks:

* Resource Changes
* Administrative Actions
* Subscription Activity

---

### Azure Resources

Provides:

* Resource Telemetry
* Operational Data

---

### Azure Security Services

Examples:

* Microsoft Defender for Cloud
* Azure Security Center Data

---

# SOC Perspective

Azure connectors provide visibility into cloud infrastructure activity.

---

# Third-Party Sources

Microsoft Sentinel also supports non-Microsoft products.

---

# Examples

* Cisco
* Palo Alto Networks
* Fortinet
* Check Point
* Linux Servers
* Unix Systems

---

# Why This Matters

Many organizations operate:

```text id="x2n8vf"
Multi-Vendor Security Environments
```

Sentinel can aggregate telemetry across these environments.

---

# 4. Installing Data Connectors

Most connectors are deployed through Content Hub.

---

# What is Content Hub?

Content Hub is Microsoft's repository for:

* Solutions
* Connectors
* Analytics Rules
* Workbooks
* Hunting Queries

---

# Installation Process

```text id="m7k4hr"
Open Sentinel
      ↓
Navigate to Content Hub
      ↓
Search Solution
      ↓
Install
      ↓
Configure Connector
      ↓
Begin Data Collection
```

---

# Benefits

✅ Simplified deployment

✅ Standardized integrations

✅ Faster onboarding

---

# EXAM FACT

Many Sentinel connectors are installed through:

> Content Hub

---

# 5. Common Event Format (CEF)

One of the most heavily tested topics in this module.

---

# What is CEF?

CEF stands for:

> Common Event Format

---

# Purpose

CEF provides a standardized structure for security events.

---

# Why It Exists

Different security vendors generate logs differently.

CEF creates consistency.

---

# Example Concept

Without CEF:

```text id="z6x9fw"
Vendor A Log
Vendor B Log
Vendor C Log
```

all use different formats.

---

# With CEF

```text id="4h3npo"
Standardized Structure
```

making ingestion and analysis easier.

---

# Benefits

* Consistent Fields
* Easier Parsing
* Better Correlation
* Improved Interoperability

---

# Think

```text id="n7p4ku"
CEF
=
How Logs Are Structured
```

---

# SOC Perspective

CEF makes it easier for analysts to work with logs from multiple vendors.

---

# 6. Syslog

Another extremely important SC-200 concept.

---

# What is Syslog?

Syslog is a standard protocol used to transport log messages.

---

# Common Sources

* Linux Systems
* Unix Systems
* Firewalls
* Routers
* Switches
* Security Appliances

---

# Purpose

Syslog is responsible for:

> Moving Logs

from one system to another.

---

# Think

```text id="w4t0ny"
Syslog
=
Log Transport Mechanism
```

---

# Why It Matters

Many third-party products send logs to Sentinel using Syslog.

---

# 7. CEF vs Syslog

One of Microsoft's favorite exam distinctions.

---

# CEF

Purpose:

Defines the structure of data.

---

# Think

```text id="l8f2sv"
CEF
=
How Logs Look
```

---

# Syslog

Purpose:

Moves log data between systems.

---

# Think

```text id="y9u7ab"
Syslog
=
How Logs Travel
```

---

# Comparison Table

| CEF                 | Syslog             |
| ------------------- | ------------------ |
| Event Format        | Transport Protocol |
| Defines Structure   | Moves Data         |
| Standardizes Events | Delivers Events    |
| Log Appearance      | Log Transportation |

---

# Easy Memory Trick

```text id="k2n4jc"
Syslog
=
Transportation

CEF
=
Packaging
```

---

# Real Enterprise Relevance

Data connectors support:

* Security Monitoring
* Threat Hunting
* Incident Response
* Compliance Monitoring
* Cloud Security
* Multi-Vendor Security Operations

Most enterprise Sentinel deployments manage dozens or even hundreds of connectors.

---

# Interview-Level Questions

## Q1. What is a Data Connector?

A mechanism used to ingest data into Microsoft Sentinel.

---

## Q2. What happens if no data connectors are configured?

Sentinel cannot collect telemetry and therefore cannot perform security operations.

---

## Q3. What is CEF?

Common Event Format used to standardize security event structures.

---

## Q4. What is Syslog?

A protocol used to transport log messages.

---

## Q5. What is the difference between CEF and Syslog?

CEF defines how logs are structured.

Syslog defines how logs are transported.

---

# Important Revision Sheet

| Concept                 | Meaning                         |
| ----------------------- | ------------------------------- |
| Data Connector          | Ingests data into Sentinel      |
| Content Hub             | Connector & Solution Repository |
| CEF                     | Common Event Format             |
| Syslog                  | Log Transport Protocol          |
| Log Analytics Workspace | Data Storage Layer              |
| Sentinel                | Security Operations Layer       |

---

# Quick Recall Sheet

```text id="v8p3gd"
Data Source
↓
Connector
↓
Workspace
↓
Table
↓
KQL

CEF
→ Event Format

Syslog
→ Transport Protocol

Content Hub
→ Install Connectors
```

---

# MOST IMPORTANT EXAM FACTS

✅ Data Connectors ingest telemetry into Sentinel.

✅ No data = No detections.

✅ Content Hub is used to install many Sentinel solutions and connectors.

✅ CEF = Event Structure.

✅ Syslog = Log Transport.

✅ CEF and Syslog are NOT the same thing.

---

# Analyst Takeaways

* Data connectors form the foundation of Sentinel visibility.
* Sentinel supports Microsoft, Azure, and third-party telemetry sources.
* Content Hub simplifies connector deployment.
* CEF standardizes event structures.
* Syslog transports logs between systems.
* Understanding data ingestion is critical for SOC operations and the SC-200 exam.

---

# Next Module Focus

* Microsoft Security Connectors
* Defender Data Sources
* Data Collection Rules
* Azure Monitoring Integration
* Sentinel Data Onboarding

---
