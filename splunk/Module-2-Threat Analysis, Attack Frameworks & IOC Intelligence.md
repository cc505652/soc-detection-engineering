# Module 2 — Threat Analysis, Attack Frameworks & IOC Intelligence
---

This module marks the transition from:

> “basic cybersecurity concepts”

into:

> “adversary-focused security analysis.”

This is one of the foundational modules for building:

- SOC analyst thinking
- Detection engineering concepts
- Threat hunting methodology
- Incident response workflows
- Threat intelligence understanding

---

# 1. Common Cybersecurity Threats

The module introduced modern cyber threats commonly investigated by SOC analysts.

---

# Common Threat Categories

| Threat Type | Description |
|---|---|
| Phishing | Social engineering via email/messages |
| Ransomware | Encrypts files for ransom |
| Malware | Malicious software |
| Credential Theft | Password/token compromise |
| Insider Threat | Threat from internal users |
| Supply Chain Attack | Third-party compromise |
| DDoS | Overwhelming systems with traffic |
| APTs | Long-term stealth attacks |

---

# SOC Analyst Perspective

Security analysts must:

- recognize attack patterns
- identify abnormal behavior
- understand attacker objectives
- correlate suspicious activity
- prioritize high-risk threats quickly

---

# 2. Real-World Attack Lifecycle Analysis

One of the most important concepts introduced:

> Cyber attacks occur in stages.

Attackers do NOT:

```text
Click button → instantly compromise organization
```

Instead, they:

- gather intelligence
- scan systems
- gain initial access
- escalate privileges
- move laterally
- maintain persistence
- exfiltrate data

This mindset is foundational for:

- SOC operations
- Threat hunting
- Detection engineering
- Incident response

---

# Example Attack Lifecycle

```text
Reconnaissance
      ↓
Initial Access
      ↓
Execution
      ↓
Privilege Escalation
      ↓
Lateral Movement
      ↓
Persistence
      ↓
Data Exfiltration
```

---

# 3. Vulnerabilities

## Definition

A vulnerability is:

> a weakness exploitable by attackers.

---

# Types of Vulnerabilities

| Type | Example |
|---|---|
| Software Vulnerability | Unpatched application |
| Hardware Vulnerability | CPU flaws (Meltdown/Spectre) |
| Misconfiguration | Open S3 bucket |
| Weak Authentication | Weak passwords |
| Human Error | Phishing victim |

---

# Why Vulnerabilities Matter

Attackers exploit vulnerabilities to:

- gain access
- escalate privileges
- execute malware
- steal sensitive data
- disrupt business operations

---

# Vulnerability Tracking

Security teams commonly track vulnerabilities using:

- CVEs (Common Vulnerabilities and Exposures)
- NVD (National Vulnerability Database)
- Vendor advisories
- Security bulletins

---

# Example CVE

| CVE | Description |
|---|---|
| CVE-2021-44228 | Log4Shell vulnerability |

---

# 4. MITRE ATT&CK Framework

## One of the MOST IMPORTANT concepts in modern cybersecurity.

MITRE ATT&CK is:

> a knowledge base of real-world attacker behavior.

It maps:

- tactics
- techniques
- procedures (TTPs)

used by adversaries.

---

# MITRE Structure

| Level | Meaning |
|---|---|
| Tactic | Attacker objective |
| Technique | Method used to achieve objective |
| Procedure | Specific implementation |

---

# Example

| Component | Example |
|---|---|
| Tactic | Credential Access |
| Technique | Brute Force |
| ATT&CK ID | T1110 |

---

# Why MITRE ATT&CK Matters

SOC analysts use MITRE for:

- threat detection
- attack mapping
- alert correlation
- threat hunting
- detection engineering
- adversary simulation

---

# Enterprise Relevance

Many enterprise SOCs map detections directly to:

- ATT&CK IDs
- ATT&CK tactics
- ATT&CK techniques

This becomes highly relevant in:

- Splunk
- SIEM engineering
- detection workflows
- SOC reporting

---

# 5. Lockheed Martin Cyber Kill Chain

The Cyber Kill Chain models attack progression stages.

---

# Kill Chain Phases

```text
Reconnaissance
Weaponization
Delivery
Exploitation
Installation
Command & Control
Actions on Objectives
```

---

# Purpose of the Kill Chain

Helps defenders:

- identify attacker stage
- disrupt attacks early
- improve defensive visibility
- enhance incident response

---

# MITRE ATT&CK vs Cyber Kill Chain

| MITRE ATT&CK | Cyber Kill Chain |
|---|---|
| Detailed attacker behaviors | Attack lifecycle stages |
| Tactical & technical focus | Strategic lifecycle focus |
| Detection-oriented | Phase-oriented |

---

# 6. Diamond Model

The Diamond Model is a threat intelligence framework.

---

# Core Components

```text
Adversary
Victim
Infrastructure
Capability
```

---

# Purpose

Helps analysts understand:

- who conducted the attack
- what tools were used
- what infrastructure was leveraged
- who was targeted

Useful for:

- Cyber Threat Intelligence (CTI)
- malware investigations
- threat hunting
- attribution analysis

---

# 7. Indicators of Compromise (IOCs)

## IOC Definition

Artifacts indicating potential malicious activity.

---

# IOC Examples

| IOC Type | Example |
|---|---|
| IP Address | Malicious server |
| Hash | Malware file hash |
| Domain | Phishing domain |
| URL | Malicious URL |
| Email | Suspicious sender |
| Registry Key | Persistence mechanism |

---

# 8. Pyramid of Pain

One of the most important threat hunting concepts.

---

# Core Idea

Some indicators are:

- easy for attackers to change
- difficult for attackers to change

The harder an indicator is to change:

> the more operational pain defenders create for attackers.

---

# Pyramid Levels

```text
Hash Values
IP Addresses
Domain Names
Network Artifacts
Host Artifacts
Tools
TTPs
```

---

# Key Security Insight

Low-level IOCs:

- hashes
- IPs
- domains

are relatively weak because attackers can easily replace them.

High-value detections focus on:

- attacker behavior
- TTPs
- adversary methodology

This is where:

- detection engineering
- advanced SOC analysis
- threat hunting

becomes significantly more powerful.

---

# SOC Analyst Perspective

Modern SOCs increasingly focus on:

✅ behavioral detection

✅ TTP-based detection

❌ simple IOC blocking alone

---

# Interview-Level Questions

## Q1. What is MITRE ATT&CK?

A framework mapping real-world attacker tactics and techniques.

---

## Q2. What is the purpose of the Cyber Kill Chain?

To understand and disrupt attack progression stages.

---

## Q3. What are IOCs?

Artifacts indicating possible compromise or malicious activity.

---

## Q4. Why are TTPs more valuable than IPs/hashes?

Because attackers can easily replace infrastructure, but changing operational behavior is much harder.

---

# Important Revision Sheet

| Concept | Meaning |
|---|---|
| IOC | Indicator of Compromise |
| TTP | Tactics, Techniques, Procedures |
| MITRE ATT&CK | Attacker behavior framework |
| Kill Chain | Attack lifecycle framework |
| Diamond Model | Threat intelligence framework |
| CVE | Public vulnerability identifier |
| Pyramid of Pain | IOC effectiveness model |

---

# Analyst Takeaways

- Modern SOC operations rely heavily on adversary behavior analysis
- Detection engineering increasingly focuses on behavioral detections instead of static signatures
- MITRE ATT&CK has become a core industry-standard framework for detection mapping
- Understanding attack progression improves incident investigation quality
- Threat intelligence frameworks help analysts contextualize attacks more effectively

---

# SOC / Splunk Relevance

SIEM platforms like Splunk help analysts:

- correlate attack indicators
- identify attack stages
- detect abnormal behavior
- map alerts to MITRE ATT&CK
- investigate IOC relationships
- improve threat visibility

Concepts introduced in this module directly influence:

- detection engineering
- threat hunting
- incident triage
- SIEM correlation searches
- behavioral analytics

---

# Real-World Security Connections

- SolarWinds demonstrated the impact of supply chain compromise
- Log4Shell highlighted the dangers of vulnerable dependencies
- Modern ransomware campaigns frequently use lateral movement and credential theft techniques
- APT groups commonly leverage stealth, persistence, and behavioral evasion tactics

---

# Potential Detection Opportunities

Possible SOC detections related to this module:

- brute-force authentication attempts
- suspicious lateral movement
- abnormal PowerShell execution
- malicious outbound connections
- unusual privilege escalation
- persistence mechanism creation
- repeated IOC matches across endpoints

---

# MOST IMPORTANT TAKEAWAY

This module introduces:

> adversary-centric security thinking.

Meaning:

- understanding attacker methodology
- analyzing attack progression
- mapping behaviors
- detecting techniques instead of only signatures

This mindset is foundational for:

- SOC operations
- Detection engineering
- Threat hunting
- Cloud security monitoring
- Incident response
- SIEM engineering

---

# Next Module Focus

- SIEM architecture
- Log ingestion
- Security event correlation
- Alert workflows
- Security monitoring pipelines

---
