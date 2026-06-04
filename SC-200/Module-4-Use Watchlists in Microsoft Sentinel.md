# Module 4 — Use Watchlists in Microsoft Sentinel

## Microsoft SC-200: Security Operations Analyst
---

# Module Overview

Microsoft Sentinel Watchlists allow analysts to store and reference custom datasets during investigations, threat hunting activities, and detection workflows.

Unlike security events, alerts, or incidents, watchlists contain:

> analyst-defined reference data.

Watchlists provide contextual information that can be combined with security telemetry to improve:

* Investigations
* Threat Hunting
* Analytics Rules
* Detection Engineering
* Incident Prioritization

This module introduces how watchlists work, common use cases, and how analysts access watchlist data using Kusto Query Language (KQL).

---

# 1. What is a Watchlist?

## Definition

A Watchlist is a Microsoft Sentinel feature used to store reference data that analysts can use during security operations.

---

# Key Characteristic

Watchlists do NOT contain:

❌ Security Events

❌ Alerts

❌ Incidents

Instead, they contain:

✅ Custom Reference Data

---

# Think

```text id="hqm3up"
Watchlist
=
Reference Data Repository
```

---

# Why Watchlists Exist

Security investigations often require contextual information.

Example:

An analyst may want to know:

* Is this IP trusted?
* Is this user considered high-risk?
* Is this device approved?
* Is this domain known to be malicious?

Watchlists help answer these questions.

---

# Security Operations Workflow

```text id="c5k0vf"
Security Event
        ↓
Investigation
        ↓
Reference Data Lookup
        ↓
Context Added
        ↓
Decision Making
```

---

# SOC Perspective

Watchlists provide:

> Context

not

> Telemetry

This distinction is important.

---

# 2. Common Watchlist Use Cases

One of the most heavily tested concepts in this module.

---

# Approved IP Addresses

## Purpose

Store trusted network locations.

---

# Examples

* Corporate Offices
* VPN Gateways
* Administrative Networks
* Security Operations Centers

---

# Investigation Example

Question:

```text id="1jz53f"
Did this login originate from a trusted network?
```

Watchlist provides the answer.

---

# Detection Engineering Example

Suppress alerts generated from:

* approved infrastructure
* known management systems

to reduce false positives.

---

# Think

```text id="4q3m1j"
Approved IP Watchlist
=
Trusted Network Locations
```

---

# VIP Users

## Purpose

Identify high-value individuals within the organization.

---

# Examples

* Executives
* Domain Administrators
* Security Administrators
* Privileged Users

---

# Why This Matters

An authentication event involving:

```text id="j6s8oa"
Regular Employee
```

may be lower priority than:

```text id="gvduj2"
Chief Executive Officer
```

or

```text id="35l8c7"
Global Administrator
```

---

# Investigation Benefit

Watchlists allow analysts to:

* prioritize investigations
* assign severity levels
* create specialized detections

---

# Think

```text id="8hjg8z"
VIP User Watchlist
=
High-Value Targets
```

---

# Known Malicious Indicators

## Purpose

Store threat intelligence indicators.

---

# Common Indicators

* Malicious IP Addresses
* Domains
* URLs
* File Hashes

---

# Common Use Cases

* IOC Matching
* Threat Hunting
* Detection Rules
* Investigation Enrichment

---

# Example Workflow

```text id="yzs1pn"
Network Event
        ↓
IOC Watchlist Match
        ↓
Suspicious Activity Identified
```

---

# Think

```text id="tdw4hc"
IOC Watchlist
=
Known Bad Indicators
```

---

# Approved Devices

Another common enterprise use case.

---

# Examples

* Corporate Laptops
* Authorized Servers
* Managed Workstations

---

# Purpose

Differentiate:

```text id="zhsuyv"
Known Device
```

from

```text id="pkh3lj"
Unknown Device
```

during investigations.

---

# 3. Watchlist Management

Watchlists require ongoing maintenance.

---

# Data Can Be

### Added Manually

Useful for:

* small datasets
* rapid updates

---

### Imported in Bulk

Useful for:

* large datasets
* threat intelligence feeds
* asset inventories

---

### Updated Regularly

Recommended approach.

---

# Microsoft Best Practice

Microsoft recommends:

✅ Updating existing watchlists

instead of:

❌ Deleting and recreating watchlists

---

# Why?

Updating preserves:

* continuity
* references
* integrations
* operational consistency

---

# SOC Perspective

Watchlists should be treated as:

> living datasets

that evolve with the organization.

---

# 4. Watchlist Service Level Agreement (SLA)

A frequently tested exam topic.

---

# SLA Definition

Changes made to a watchlist should become available within:

> 5 minutes

---

# Why This Matters

Analysts often update watchlists during:

* active investigations
* threat response activities
* IOC enrichment

---

# If Updates Are Not Visible

Recommended actions:

1. Verify update completion
2. Wait for SLA window
3. Investigate synchronization issues
4. Open Microsoft Support request if necessary

---

# EXAM FACT

```text id="u0fj9u"
Watchlist Update SLA
=
5 Minutes
```

---

# 5. Accessing Watchlists with KQL

One of the MOST important exam objectives.

---

# KQL Function

Watchlists are accessed using:

```kusto
_GetWatchlist("WatchlistName")
```

---

# Example

```kusto
_GetWatchlist("VIPUsers")
```

---

# Purpose

Returns:

> watchlist contents for use within KQL queries.

---

# Why This Matters

Watchlists become significantly more powerful when combined with:

* Log Data
* Authentication Records
* Endpoint Activity
* Security Alerts

---

# Example Investigation Logic

```text id="52cx3o"
Authentication Logs
         +
VIP User Watchlist
         =
High-Value Target Detection
```

---

# Example Threat Hunting Logic

```text id="8c3yp3"
Network Events
       +
Malicious IP Watchlist
       =
IOC Matching
```

---

# Detection Engineering Perspective

Watchlists enable:

* contextual detections
* enriched analytics rules
* risk-based alerting
* dynamic investigations

This makes them extremely valuable in enterprise SOC environments.

---

# 6. Why Watchlists Matter

Watchlists improve investigations by providing:

* Context
* Prioritization
* Threat Intelligence
* Organizational Knowledge

---

# Security Operations Benefit

Without watchlists:

```text id="gqg0l8"
User Logged In
```

With watchlists:

```text id="jofx6i"
VIP User Logged In
```

or

```text id="rqc6v2"
Known Malicious IP Connected
```

The context changes the investigation significantly.

---

# SOC Analyst Perspective

Experienced analysts rarely investigate events in isolation.

They combine:

* telemetry
* threat intelligence
* asset information
* business context

to make decisions.

Watchlists provide much of that context.

---

# Real Enterprise Relevance

Watchlists are commonly used for:

* Threat Intelligence Management
* VIP User Monitoring
* Asset Tracking
* IOC Matching
* Detection Engineering
* Investigation Prioritization

Many enterprise SOC teams maintain dozens of watchlists for different operational purposes.

---

# Interview-Level Questions

## Q1. What is a Watchlist?

A repository of analyst-defined reference data used during investigations, threat hunting, and detection workflows.

---

## Q2. Are Watchlists security events?

No.

Watchlists contain reference data, not telemetry.

---

## Q3. What KQL function accesses Watchlists?

```kusto
_GetWatchlist()
```

---

## Q4. What is the Watchlist SLA?

Updates should become available within 5 minutes.

---

## Q5. Give common Watchlist examples.

* Trusted IPs
* VIP Users
* Approved Devices
* Malicious Indicators

---

# Important Revision Sheet

| Concept         | Meaning                      |
| --------------- | ---------------------------- |
| Watchlist       | Reference Data Repository    |
| VIP Users       | High-value targets           |
| Approved IPs    | Trusted networks             |
| IOC Watchlist   | Known malicious indicators   |
| SLA             | 5-minute update availability |
| _GetWatchlist() | KQL watchlist function       |

---

# Quick Recall Sheet

```text id="9x6gwv"
Watchlist
→ Reference Data

Trusted IPs
→ Known Good

VIP Users
→ High Value Targets

Malicious Indicators
→ Known Bad

_GetWatchlist()
→ Access Watchlist Data

SLA
→ 5 Minutes
```

---

# MOST IMPORTANT EXAM FACTS

✅ Watchlists contain reference data.

✅ Watchlists do NOT contain alerts, incidents, or events.

✅ Access watchlists using:

```kusto
_GetWatchlist()
```

✅ Common use cases include:

* Trusted IPs
* VIP Users
* Approved Devices
* Threat Intelligence Indicators

✅ Watchlist update SLA = 5 minutes.

---

# Analyst Takeaways

* Watchlists provide contextual data for investigations and hunting.
* They enhance threat intelligence and detection workflows.
* Watchlists are frequently used for IOC matching and VIP monitoring.
* KQL uses _GetWatchlist() to access watchlist contents.
* Effective watchlist management improves SOC efficiency and investigation quality.

---

# Next Module Focus

* Kusto Query Language (KQL)
* Search Operators
* Filtering Data
* Query Construction
* Threat Hunting Queries

---
