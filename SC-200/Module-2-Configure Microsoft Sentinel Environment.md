# Module 2 — Configure Microsoft Sentinel Environment

## Microsoft SC-200: Security Operations Analyst
---

# Module Overview

Before Microsoft Sentinel can perform security monitoring, investigations, and threat detection, a properly configured environment must exist.

This module focuses on:

* Sentinel deployment architecture
* Log Analytics Workspace design
* Multi-workspace strategies
* Multi-tenant management
* Data retention planning
* Role-Based Access Control (RBAC)

Understanding these concepts is critical because poor architecture decisions can impact:

* cost
* compliance
* scalability
* operational efficiency
* investigation workflows

---

# 1. Microsoft Sentinel Workspace Foundation

## Why a Workspace is Required

Microsoft Sentinel cannot operate independently.

Before Sentinel is enabled:

> An Azure Log Analytics Workspace must exist.

The workspace serves as the underlying storage and analytics platform.

---

# What the Workspace Stores

The Log Analytics Workspace stores:

* Security logs
* Events
* Telemetry
* Threat intelligence data
* Query results
* Investigation data

---

# Architecture Relationship

```text
Data Sources
      ↓
Log Analytics Workspace
      ↓
Microsoft Sentinel
      ↓
Detection
Investigation
Threat Hunting
Automation
```

---

# Easy Memory Trick

```text
Log Analytics Workspace
=
Data Layer

Microsoft Sentinel
=
Security Operations Layer
```

---

# Why This Matters

Every major Sentinel capability depends on the workspace:

* Analytics Rules
* Threat Hunting
* Incident Investigation
* Workbooks
* Automation
* Dashboards

No workspace = No Sentinel.

---

# 2. Sentinel Deployment Architectures

Organizations choose different deployment models depending on:

* size
* geography
* compliance requirements
* business structure
* operational complexity

---

# Architecture 1 — Single-Tenant Single Workspace

## Overview

The simplest Sentinel deployment model.

```text
Single Tenant
      ↓
Single Workspace
      ↓
Single Sentinel Instance
```

---

# Characteristics

* One Sentinel deployment
* Centralized visibility
* Unified monitoring
* Simplified administration

---

# Best For

Organizations that:

* operate primarily in one region
* have centralized security operations
* have limited compliance requirements

---

# Advantages

✅ Easy management

✅ Single security dashboard

✅ Simplified investigations

✅ Reduced operational complexity

---

# Disadvantages

❌ Cross-region bandwidth costs

❌ Potential latency concerns

❌ Less regional flexibility

---

# SOC Perspective

Analysts benefit from:

* centralized visibility
* unified investigations
* easier correlation

because all telemetry exists in one location.

---

# Architecture 2 — Single-Tenant Regional Workspaces

## Overview

Organizations maintain multiple workspaces within the same Azure tenant.

```text
Single Tenant
      ↓
Multiple Regional Workspaces
      ↓
Multiple Sentinel Workspaces
```

---

# Characteristics

* Multiple workspaces
* Same Azure tenant
* Regional separation

---

# Best For

Organizations operating across:

* multiple countries
* multiple continents
* regulated environments

---

# Advantages

✅ Regional data residency

✅ Lower bandwidth costs

✅ Improved compliance

✅ Better geographic separation

---

# Disadvantages

❌ More administrative overhead

❌ Multiple workspaces to manage

❌ More complex investigations

---

# Real Enterprise Example

A global company may maintain:

```text
US Workspace
EU Workspace
Asia Workspace
```

to satisfy regional compliance requirements.

---

# Architecture 3 — Multi-Tenant Deployment

One of the most important SC-200 concepts.

---

# Overview

Used when managing:

* multiple Azure tenants
* multiple business entities
* multiple customers

---

# Architecture

```text
Tenant A
      ↓
Workspace A

Tenant B
      ↓
Workspace B

Tenant C
      ↓
Workspace C
```

---

# Managed Through

> Azure Lighthouse

---

# EXAM FACT

```text
Multi-Tenant
       ↓
Azure Lighthouse
```

Memorize this relationship.

---

# Why Azure Lighthouse Exists

Azure Lighthouse enables:

* centralized visibility
* delegated administration
* cross-tenant monitoring
* unified security management

---

# Common Use Cases

### MSSPs

Managed Security Service Providers

### Large Enterprises

Multiple subsidiaries

### Holding Companies

Multiple business units

---

# Advantages

✅ Centralized management

✅ Cross-tenant visibility

✅ Operational efficiency

---

# SOC Perspective

A single SOC team can manage security operations across multiple tenants without constantly switching environments.

---

# 3. Data Retention

One of the most frequently tested SC-200 topics.

---

# What is Retention?

Retention determines:

> How long security data remains available.

---

# Why Retention Matters

Retention impacts:

* investigations
* compliance
* auditing
* threat hunting
* storage costs

---

# Security Operations Perspective

Some attacks remain undetected for months.

Retention determines whether analysts can:

* reconstruct attack timelines
* perform historical investigations
* identify persistence

---

# Interactive Retention

## Purpose

Used for:

* searching
* investigations
* threat hunting
* analytics

---

# Characteristics

Interactive retention allows analysts to actively query and analyze data.

---

# Example Activities

* Running KQL queries
* Hunting threats
* Reviewing incidents
* Building analytics rules

---

# Long-Term Retention

## Purpose

Designed for:

* compliance
* audits
* historical investigations
* regulatory requirements

---

# Key Capability

Long-term retention can extend up to:

> 12 years

---

# Why Organizations Use It

Requirements such as:

* financial regulations
* healthcare compliance
* government regulations

often require long-term log storage.

---

# EXAM FACT

Many exam questions focus on retention.

Remember:

❌ Do not assume retention is always 30 days.

✅ Retention is configurable.

✅ Long-term retention can extend significantly beyond interactive retention.

---

# 4. Microsoft Sentinel Roles

Role-Based Access Control (RBAC) determines what users can do within Sentinel.

---

# Why RBAC Matters

SOC environments require:

* separation of duties
* least privilege
* operational accountability

Not every user should have full administrative access.

---

# Sentinel Reader

## Purpose

Read-only access.

---

# Permissions

✅ View incidents

✅ View alerts

✅ View workbooks

✅ View logs

---

# Cannot

❌ Modify incidents

❌ Create analytics rules

❌ Configure Sentinel

---

# Best For

* Auditors
* Compliance Teams
* Read-only stakeholders

---

# Sentinel Responder

## Purpose

Incident management role.

---

# Permissions

✅ View incidents

✅ Update incidents

✅ Manage investigations

✅ Respond to alerts

---

# Cannot

❌ Create analytics rules

❌ Modify Sentinel resources

---

# Best For

* SOC Analysts
* Incident Responders

---

# Sentinel Contributor

## Purpose

Full Sentinel management.

---

# Permissions

✅ Create analytics rules

✅ Modify resources

✅ Create hunting queries

✅ Manage workbooks

✅ Configure Sentinel

---

# Think

```text
Contributor
=
Full Sentinel Administration
```

---

# Best For

* Sentinel Engineers
* Security Administrators
* Detection Engineers

---

# Sentinel Automation Contributor

## Purpose

Automation-focused role.

---

# Permissions

✅ Manage Playbooks

✅ Create automation rules

✅ Modify automation workflows

---

# Why It Exists

Automation often requires separate ownership from general Sentinel administration.

---

# Common Responsibilities

* Playbook development
* Workflow automation
* Logic App integration

---

# Operational Security Insight

Many organizations combine:

```text
Contributor
+
Automation Contributor
```

for engineering teams responsible for detection and automation.

---

# RBAC Comparison Table

| Role                   | View    | Manage Incidents | Manage Sentinel | Manage Automation |
| ---------------------- | ------- | ---------------- | --------------- | ----------------- |
| Reader                 | ✅       | ❌                | ❌               | ❌                 |
| Responder              | ✅       | ✅                | ❌               | ❌                 |
| Contributor            | ✅       | ✅                | ✅               | ❌                 |
| Automation Contributor | Limited | Limited          | ❌               | ✅                 |

---

# SOC Analyst Perspective

A typical SOC hierarchy may look like:

```text
Reader
     ↓
Responder
     ↓
Contributor
```

with automation teams using:

```text
Automation Contributor
```

for workflow management.

---

# Real Enterprise Relevance

These concepts directly impact:

* SOC architecture
* Cloud security operations
* Detection engineering
* Multi-region deployments
* MSSP environments
* Regulatory compliance

Many large organizations spend significant time designing:

* workspace architecture
* retention policies
* RBAC strategies

before deploying Sentinel at scale.

---

# Interview-Level Questions

## Q1. What component must exist before Sentinel can be enabled?

An Azure Log Analytics Workspace.

---

## Q2. What service enables multi-tenant Sentinel management?

Azure Lighthouse.

---

## Q3. Which Sentinel role can create analytics rules?

Sentinel Contributor.

---

## Q4. Which role manages incidents but cannot configure Sentinel?

Sentinel Responder.

---

## Q5. Why is retention important?

It supports investigations, compliance, auditing, and historical analysis.

---

# Important Revision Sheet

| Concept                | Meaning                        |
| ---------------------- | ------------------------------ |
| Workspace              | Sentinel data storage platform |
| Single Workspace       | Simplest deployment model      |
| Regional Workspaces    | Multi-region deployment        |
| Azure Lighthouse       | Multi-tenant management        |
| Interactive Retention  | Searchable investigation data  |
| Long-Term Retention    | Compliance and audits          |
| Reader                 | View-only access               |
| Responder              | Incident management            |
| Contributor            | Full Sentinel management       |
| Automation Contributor | Playbook management            |

---

# Analyst Takeaways

* Microsoft Sentinel requires a Log Analytics Workspace.
* Workspace architecture impacts cost, compliance, and scalability.
* Azure Lighthouse enables centralized multi-tenant management.
* Retention policies directly affect investigations and compliance.
* RBAC enforces least privilege and operational accountability.
* Sentinel roles are heavily tested in SC-200.

---

# MOST IMPORTANT EXAM FACTS

✅ Log Analytics Workspace is required before Sentinel can operate.

✅ Multi-Tenant Management = Azure Lighthouse.

✅ Contributor can create analytics rules.

✅ Automation Contributor manages Playbooks and Automation.

✅ Long-Term Retention can extend up to 12 years.

✅ Retention is configurable.

---

# Next Module Focus

* Data Connectors
* Data Ingestion
* Microsoft Security Connectors
* Threat Intelligence Integration
* Sentinel Data Sources

---
