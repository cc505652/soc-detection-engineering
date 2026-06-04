# Module 5 — Manage Threat Intelligence in Microsoft Sentinel

## Microsoft SC-200: Security Operations Analyst
---

# Module Overview

Threat Intelligence (TI) is one of the most important components of modern security operations.

Security teams continuously collect information about:

* Threat Actors
* Malicious Infrastructure
* Malware Campaigns
* Command-and-Control Servers
* Attack Indicators

Microsoft Sentinel provides built-in capabilities for storing, managing, and querying threat intelligence data.

This intelligence can then be used for:

* Threat Hunting
* Incident Investigation
* Alert Enrichment
* IOC Matching
* Detection Engineering

---

# 1. What is Threat Intelligence?

## Definition

Threat Intelligence (TI) is information about known threats that helps organizations:

* Detect attacks
* Investigate incidents
* Identify malicious activity
* Improve security monitoring
* Enhance response capabilities

---

# Security Perspective

Threat Intelligence answers questions such as:

```text id="egj3f4"
Is this IP known to be malicious?

Has this domain been associated with malware?

Is this file hash linked to ransomware?

Has this infrastructure been used by threat actors?
```

---

# Think

```text id="b82np7"
Threat Intelligence
=
Known Bad Information
```

---

# Common Threat Intelligence Indicators

Threat Intelligence often includes:

### Network Indicators

* IP Addresses
* Domains
* URLs

---

### File Indicators

* MD5 Hashes
* SHA1 Hashes
* SHA256 Hashes

---

### Identity Indicators

* Email Addresses
* Threat Actor Accounts

---

### Infrastructure Indicators

* Command-and-Control (C2) Servers
* Malicious Hosting Providers
* Adversary Infrastructure

---

# SOC Perspective

Threat Intelligence provides:

> Context about malicious activity.

instead of:

> General reference information.

This distinction is important.

---

# 2. Threat Intelligence in Microsoft Sentinel

Microsoft Sentinel includes a built-in framework for managing threat intelligence indicators.

---

# Why Sentinel Uses Threat Intelligence

Threat Intelligence helps analysts:

* Identify malicious activity faster
* Prioritize investigations
* Correlate security events
* Improve detections
* Enrich alerts

---

# Common Security Operations Use Cases

### Threat Hunting

Search for activity matching known malicious indicators.

---

### Incident Investigation

Determine whether entities involved in an incident are already known threats.

---

### Alert Enrichment

Provide additional context during triage.

---

### Detection Engineering

Build detections around known malicious infrastructure.

---

# Threat Intelligence Workflow

```text id="fd8gj7"
Threat Feed
      ↓
Indicators Imported
      ↓
Threat Intelligence Store
      ↓
KQL Queries
      ↓
Detection / Hunting / Investigation
```

---

# 3. Threat Intelligence Indicators

## What is an Indicator?

An Indicator is a piece of data associated with suspicious or malicious activity.

---

# Common IOC Types

## IP Address

Example:

```text id="c78q1w"
185.220.101.42
```

Used to identify:

* Malicious Infrastructure
* C2 Servers
* Scanning Activity

---

## Domain

Example:

```text id="k4g7rx"
malicious-domain.com
```

Used to identify:

* Phishing Sites
* Malware Delivery Infrastructure
* Threat Actor Domains

---

## URL

Example:

```text id="j2q9bz"
https://malicious-site.com
```

Used to identify:

* Malicious Downloads
* Exploit Pages
* Credential Theft Sites

---

## File Hash

Examples:

* MD5
* SHA1
* SHA256

Used to identify:

* Malware Samples
* Known Malicious Files
* Ransomware Artifacts

---

## Email Address

Used to identify:

* Phishing Campaigns
* Threat Actor Accounts
* Business Email Compromise Activity

---

# Think

```text id="u9bnm3"
IOC
=
Indicator of Compromise
```

---

# 4. Threat Intelligence Storage

One of the most important SC-200 exam facts.

---

# Primary Table

Microsoft Sentinel stores threat intelligence indicators inside:

```kusto
ThreatIntelligenceIndicator
```

---

# Why This Matters

This table contains:

* Imported Indicators
* Threat Feeds
* IOC Records
* Indicator Metadata

---

# IMPORTANT EXAM FACT

```kusto
ThreatIntelligenceIndicator
```

is the primary table used for threat intelligence storage.

Memorize it.

---

# Architecture Relationship

```text id="z71g4h"
Threat Feed
      ↓
ThreatIntelligenceIndicator
      ↓
KQL Query
      ↓
Detection / Investigation
```

---

# 5. Accessing Threat Intelligence

Threat Intelligence can be accessed through multiple methods.

---

# Sentinel User Interface

Analysts can:

* Search Indicators
* Filter Indicators
* Review IOC Details
* Manage Indicator Records

---

# Common Activities

* Review imported feeds
* Validate indicators
* Investigate IOC matches
* Remove outdated indicators

---

# KQL Queries

Threat Intelligence can also be queried directly.

---

# Basic Query

```kusto
ThreatIntelligenceIndicator
```

---

# Purpose

Returns:

> stored threat intelligence records.

---

# Why Analysts Use KQL

KQL enables:

* Hunting
* Correlation
* IOC Matching
* Investigation Workflows

---

# SOC Perspective

Experienced analysts often combine:

```text id="r5w8nt"
Security Logs
       +
Threat Intelligence
       =
Threat Detection
```

---

# 6. Threat Intelligence vs Watchlists

One of the MOST IMPORTANT SC-200 distinctions.

---

# Watchlists

Purpose:

Store analyst-defined reference data.

---

# Examples

* VIP Users
* Approved Devices
* Trusted Networks
* Approved Vendors

---

# Think

```text id="j94k1w"
Watchlists
=
Known Good / Reference Data
```

---

# Threat Intelligence

Purpose:

Store indicators associated with malicious activity.

---

# Examples

* Malicious IPs
* Malicious Domains
* Malware Hashes
* Threat Actor Infrastructure

---

# Think

```text id="a8yq6m"
Threat Intelligence
=
Known Bad Data
```

---

# Quick Comparison

| Watchlist        | Threat Intelligence |
| ---------------- | ------------------- |
| Analyst Defined  | Threat Related      |
| Reference Data   | IOC Data            |
| Known Good       | Known Bad           |
| VIP Users        | Malicious Domains   |
| Approved Devices | Malware Hashes      |

---

# EXAM SHORTCUT

```text id="rq3w2e"
Watchlist
=
Reference Data

Threat Intelligence
=
Malicious Data
```

---

# 7. Real SOC Use Cases

## IOC Matching

Question:

```text id="n4pq8z"
Did any endpoint communicate with a known malicious IP?
```

Workflow:

```text id="x8m5jc"
Endpoint Logs
      +
Threat Intelligence
      =
Detection
```

---

# Threat Hunting

Question:

```text id="v1e7bt"
Have users visited known malicious domains?
```

Workflow:

```text id="5k9nfr"
DNS Logs
      +
Threat Intelligence
      =
Investigation
```

---

# Alert Enrichment

Question:

```text id="m7d3qo"
Is this IP already known to be malicious?
```

Workflow:

```text id="v6z0hu"
Alert
     +
Threat Intelligence Lookup
     =
Additional Context
```

---

# Why This Matters

Threat Intelligence helps analysts:

* Prioritize incidents
* Reduce investigation time
* Improve confidence
* Increase detection accuracy

---

# Detection Engineering Perspective

Threat Intelligence can be used to:

* Build analytics rules
* Improve detections
* Correlate activity
* Identify malicious infrastructure

Many enterprise detections rely heavily on threat intelligence feeds.

---

# Real Enterprise Relevance

Threat Intelligence supports:

* SOC Operations
* Incident Response
* Threat Hunting
* Detection Engineering
* Security Analytics
* IOC Management

Most enterprise SOC teams continuously consume commercial, open-source, and internal threat intelligence feeds.

---

# Interview-Level Questions

## Q1. What is Threat Intelligence?

Information about known threats used to improve detection, investigation, and response.

---

## Q2. What is an IOC?

An Indicator of Compromise associated with malicious activity.

---

## Q3. What table stores Threat Intelligence indicators?

```kusto
ThreatIntelligenceIndicator
```

---

## Q4. Give examples of Threat Intelligence indicators.

* IP Addresses
* Domains
* URLs
* File Hashes
* Email Addresses

---

## Q5. What is the difference between Watchlists and Threat Intelligence?

Watchlists store reference data.

Threat Intelligence stores malicious indicators.

---

# Important Revision Sheet

| Concept                     | Meaning                  |
| --------------------------- | ------------------------ |
| Threat Intelligence         | Known threat information |
| IOC                         | Indicator of Compromise  |
| Threat Feed                 | Source of indicators     |
| ThreatIntelligenceIndicator | TI storage table         |
| Watchlist                   | Reference Data           |
| Threat Intelligence         | Known Bad Data           |

---

# Quick Recall Sheet

```text id="8gvj5m"
Threat Intelligence
→ Known Bad Data

IOC
→ Indicator of Compromise

Threat Intelligence Table
→ ThreatIntelligenceIndicator

Watchlist
→ Reference Data

Threat Intelligence
→ Malicious Indicators
```

---

# MOST IMPORTANT EXAM FACTS

✅ Threat Intelligence contains malicious indicators.

✅ Common IOC types:

* IPs
* Domains
* URLs
* Hashes
* Email Addresses

✅ Primary Sentinel TI table:

```kusto
ThreatIntelligenceIndicator
```

✅ Watchlists = Reference Data

✅ Threat Intelligence = Known Bad Data

---

# Analyst Takeaways

* Threat Intelligence helps identify known malicious activity.
* Sentinel provides built-in IOC management capabilities.
* ThreatIntelligenceIndicator is the primary TI storage table.
* Threat Intelligence supports hunting, investigations, detections, and enrichment.
* Understanding the difference between Watchlists and Threat Intelligence is critical for SC-200.

---

# Next Module Focus

* Kusto Query Language (KQL)
* Search Operators
* Filtering Data
* Hunting Queries
* Detection Logic

---
