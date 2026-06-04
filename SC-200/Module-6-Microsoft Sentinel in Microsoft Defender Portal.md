# Module 6 — Microsoft Sentinel in Microsoft Defender Portal

## Microsoft SC-200: Security Operations Analyst
---

# Module Overview

Microsoft Sentinel can be integrated into the Microsoft Defender Portal, providing security teams with a unified security operations experience.

Traditionally, analysts worked across multiple tools and portals when:

* Investigating incidents
* Hunting threats
* Reviewing alerts
* Managing security operations

Microsoft's goal is to consolidate these workflows into a centralized experience.

This integration enables organizations to:

* Simplify investigations
* Reduce portal switching
* Improve analyst efficiency
* Enhance threat hunting
* Strengthen incident response

---

# 1. Why Microsoft Integrated Sentinel with Defender

Modern security teams often use:

* Microsoft Sentinel
* Microsoft Defender XDR
* Microsoft Defender for Endpoint
* Microsoft Defender for Identity
* Microsoft Defender for Cloud Apps

Historically, analysts frequently switched between multiple consoles.

This created:

* Operational complexity
* Investigation delays
* Fragmented visibility
* Reduced analyst efficiency

---

# Microsoft's Vision

Provide:

```text id="k8q2wj"
One Security Platform
         ↓
Unified Visibility
         ↓
Unified Investigations
         ↓
Unified Response
```

---

# SOC Perspective

The integration focuses on:

> operational efficiency

rather than

> replacing Sentinel functionality.

---

# 2. Benefits of Sentinel Integration

## Simplified Operations

One of the biggest benefits.

---

# Traditional Workflow

```text id="3sqw1r"
Alert
   ↓
Switch Portal
   ↓
Investigate
   ↓
Switch Portal Again
   ↓
Respond
```

---

# Integrated Workflow

```text id="91zq5v"
Alert
   ↓
Investigate
   ↓
Respond
```

inside a single portal.

---

# Benefits

✅ Reduced operational complexity

✅ Faster investigations

✅ Improved analyst productivity

✅ Better visibility

---

# Security Operations Impact

Less time navigating tools.

More time investigating threats.

---

# 3. Unified Entity Pages

One of the most useful operational features.

---

# What are Entity Pages?

Entity pages provide a centralized view of security-related objects.

---

# Common Entities

### Users

View:

* Login activity
* Risk information
* Incident involvement

---

### Devices

View:

* Endpoint telemetry
* Alerts
* Security posture

---

### Alerts

View:

* Detection details
* Investigation context

---

### Incidents

View:

* Related alerts
* Evidence
* Impacted assets

---

# Why This Matters

Analysts often investigate:

```text id="pgtuwi"
User
 ↓
Device
 ↓
Alert
 ↓
Incident
```

The unified entity experience simplifies this process.

---

# SOC Perspective

Entity correlation is one of the most valuable aspects of modern investigations.

---

# 4. Enhanced Threat Hunting

Another major integration benefit.

---

# Traditional Hunting

Threat hunters often needed to:

* Gather telemetry
* Correlate multiple sources
* Switch between tools

---

# Integrated Hunting

Microsoft Defender XDR and Sentinel data can be leveraged together.

---

# Benefits

* Better visibility
* Improved correlation
* Broader telemetry coverage
* Faster investigations

---

# Hunting Workflow

```text id="q6d3wn"
Identity Data
      +
Endpoint Data
      +
Cloud Data
      +
Sentinel Data
      =
Enhanced Threat Hunting
```

---

# Why This Matters

Threat hunters gain access to a more complete security picture.

---

# 5. Attack Disruption

One of the newer Microsoft security capabilities.

---

# What is Attack Disruption?

Attack disruption allows Microsoft security products to automatically interfere with active attacks.

---

# Goal

Reduce attacker progress before significant damage occurs.

---

# Examples

Possible actions include:

* Blocking malicious activity
* Restricting compromised accounts
* Interrupting attacker workflows

---

# Example Mentioned in Training

SAP attack disruption scenarios.

---

# SOC Perspective

Attack disruption represents:

```text id="y44nki"
Detection
      ↓
Automated Action
      ↓
Threat Containment
```

instead of relying solely on manual analyst intervention.

---

# 6. Azure Portal vs Defender Portal

One of the MOST IMPORTANT SC-200 exam topics.

---

# Azure Portal

## Purpose

Provides complete Sentinel administration capabilities.

---

# Best For

* Configuration
* Administration
* Workspace Management
* Deployment
* Engineering Tasks

---

# Think

```text id="wh7hpb"
Azure Portal
=
Full Control
```

---

# Common Activities

* Configure Sentinel
* Create Data Connectors
* Manage Workspaces
* Configure Analytics Rules
* Deploy Solutions

---

# Defender Portal

## Purpose

Provides a unified analyst experience.

---

# Best For

* Investigations
* Incident Response
* Threat Hunting
* Defender XDR Integration
* SOC Operations

---

# Think

```text id="tvfjqf"
Defender Portal
=
Unified Operations
```

---

# Common Activities

* Review incidents
* Investigate alerts
* Hunt threats
* Analyze entities
* Coordinate response

---

# Easy Exam Shortcut

```text id="i6m9on"
Azure Portal
      =
Administration

Defender Portal
      =
Operations
```

Memorize this distinction.

---

# 7. Multiple Workspace Management

Another common exam topic.

---

# Azure Portal

Supports:

* Multiple Sentinel Workspaces
* Cross-Workspace Administration
* Large Deployments

---

# Common Use Cases

* MSSPs
* Multi-region Organizations
* Large Enterprises

---

# Example

```text id="7t6skg"
US Workspace

EU Workspace

Asia Workspace
```

managed centrally.

---

# Defender Portal

Supports:

> One primary Sentinel workspace per tenant.

---

# Why This Matters

Organizations requiring extensive multi-workspace administration typically rely on:

```text id="6r6ovv"
Azure Portal
```

rather than:

```text id="9qlk0v"
Defender Portal
```

---

# 8. Microsoft Defender XDR Integration Requirements

Before Sentinel can integrate with Defender XDR, several prerequisites must be met.

---

# Requirement 1

## Log Analytics Workspace

A workspace must exist.

---

# Requirement 2

## Microsoft Sentinel Enabled

Sentinel must be enabled on the workspace.

---

# Requirement 3

## Microsoft Defender XDR Access

Appropriate Defender XDR access is required.

---

# Integration Flow

```text id="efl4bz"
Log Analytics Workspace
          ↓
Microsoft Sentinel
          ↓
Microsoft Defender XDR
          ↓
Unified Security Operations
```

---

# Real Enterprise Relevance

This integration supports:

* SOC Operations
* Incident Response
* Threat Hunting
* Security Analytics
* Microsoft Security Ecosystem Integration

Many organizations are moving toward Defender Portal-centric workflows while retaining Azure Portal for administration.

---

# Interview-Level Questions

## Q1. Why integrate Sentinel with Defender Portal?

To provide a unified security operations experience.

---

## Q2. What is the primary purpose of Azure Portal?

Sentinel administration and configuration.

---

## Q3. What is the primary purpose of Defender Portal?

Security operations, investigations, and hunting.

---

## Q4. Which portal supports full multi-workspace management?

Azure Portal.

---

## Q5. What are the prerequisites for Sentinel-Defender integration?

* Log Analytics Workspace
* Microsoft Sentinel Enabled
* Microsoft Defender XDR Access

---

# Important Revision Sheet

| Concept                    | Meaning                           |
| -------------------------- | --------------------------------- |
| Azure Portal               | Full Sentinel Administration      |
| Defender Portal            | Unified Security Operations       |
| Unified Entity Pages       | Centralized investigation view    |
| Enhanced Hunting           | Combined Sentinel + XDR telemetry |
| Attack Disruption          | Automated attack response         |
| Multi-Workspace Management | Azure Portal capability           |

---

# Quick Recall Sheet

```text id="7wh0wr"
Azure Portal
→ Administration

Defender Portal
→ Operations

Entity Pages
→ Users, Devices, Incidents, Alerts

Attack Disruption
→ Automated Response

Enhanced Hunting
→ Sentinel + Defender XDR

Multi-Workspace Management
→ Azure Portal
```

---

# MOST IMPORTANT EXAM FACTS

✅ Azure Portal = Full Sentinel Administration

✅ Defender Portal = Unified Analyst Experience

✅ Defender Portal improves investigations and hunting

✅ Azure Portal supports multiple workspace management

✅ Defender Portal supports one primary Sentinel workspace per tenant

✅ Sentinel integration requires:

* Log Analytics Workspace
* Sentinel Enabled
* Defender XDR Access

---

# Analyst Takeaways

* Microsoft is moving toward a unified security operations experience.
* Defender Portal simplifies investigations and threat hunting.
* Azure Portal remains the primary administration platform.
* Entity pages improve investigation efficiency.
* Sentinel and Defender XDR together provide broader visibility and stronger hunting capabilities.
* Understanding Azure Portal vs Defender Portal is critical for the SC-200 exam.

---

# Next Module Focus

* Kusto Query Language (KQL)
* Query Operators
* Data Filtering
* Search Techniques
* Threat Hunting Queries

---
