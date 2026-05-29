# Module 8 — Threat Hunting Fundamentals, PEAK Framework & Model-Assisted Hunting

## Cisco Cybersecurity Defense Analyst (Splunk)
---

This is one of the MOST valuable modules in the entire Cybersecurity Defense Analyst path.

Up until now, the focus has been on:

- SOC operations
- SIEM platforms
- Splunk
- Threat intelligence
- Enterprise Security
- Risk-Based Alerting
- Investigations

This module introduces:

> proactive threat discovery.

This is the transition from:

```text
Reactive Security
```

to:

```text
Proactive Security
```

This is the difference between:

- investigating alerts
- actively hunting hidden threats

VERY high-value module.

---

# 1. What is Threat Hunting?

## Definition

Threat Hunting is:

> the proactive process of searching for hidden threats that may have bypassed automated detections and security controls.

---

# Traditional SOC Workflow

```text
Alert
   ↓
Investigation
   ↓
Response
```

---

# Threat Hunting Workflow

```text
Hypothesis
      ↓
Search Environment
      ↓
Analyze Evidence
      ↓
Validate Findings
      ↓
Improve Security
```

---

# Key Difference

| SOC Monitoring | Threat Hunting |
|---|---|
| Reactive | Proactive |
| Alert Driven | Hypothesis Driven |
| Investigates Known Events | Searches for Unknown Threats |
| Detection Focused | Discovery Focused |

---

# Why Threat Hunting Matters

Many attackers:

- evade signatures
- bypass detections
- abuse legitimate tools
- maintain persistence
- avoid generating alerts

Threat hunters seek to identify:

- stealthy attackers
- insider threats
- advanced persistent threats (APTs)
- suspicious behavior patterns
- hidden compromise

---

# Operational Security Insight

Threat hunting helps organizations:

- reduce attacker dwell time
- identify detection gaps
- strengthen visibility
- improve detection quality
- enhance security maturity

---

# 2. PEAK Threat Hunting Framework

One of the MOST important concepts introduced in this module.

---

# What is PEAK?

PEAK is a structured threat hunting methodology.

```text
Prepare
   ↓
Execute
   ↓
Act
```

---

# Prepare Phase

Understand:

- assets
- users
- infrastructure
- risks
- threat landscape
- business context

Then develop a hunting hypothesis.

---

# Execute Phase

Conduct:

- searches
- investigations
- log analysis
- telemetry review
- hypothesis testing

---

# Act Phase

Apply findings to improve security.

Possible outcomes:

- create new detections
- improve monitoring
- update playbooks
- refine baselines
- strengthen security posture

---

# Why PEAK Matters

Without a framework:

```text
Random Searching
```

With PEAK:

```text
Structured Investigation
```

This improves:

- consistency
- repeatability
- investigation quality
- operational maturity

---

# 3. Threat Hunting Approaches

Organizations use multiple hunting methodologies.

---

# Topic-Based Hunting

Focuses on:

> specific threat categories.

---

# Examples

- ransomware
- credential theft
- phishing
- PowerShell abuse
- lateral movement

---

# Data-Based Hunting

Begins with:

> interesting data sources.

---

# Common Sources

- DNS logs
- authentication logs
- firewall logs
- endpoint telemetry
- cloud activity logs

---

# Goal

Search for:

- anomalies
- unusual behavior
- suspicious activity

within datasets.

---

# Hypothesis-Based Hunting

The most mature hunting methodology.

---

# Core Idea

Start with:

> a theory about attacker behavior.

---

# Example

Hypothesis:

```text
Attackers may be abusing PowerShell for persistence.
```

Then:

- search logs
- analyze activity
- validate evidence
- confirm or reject hypothesis

---

# Why It Matters

Hypothesis-driven hunting closely mirrors:

- scientific analysis
- real-world investigations
- advanced threat hunting workflows

---

# 4. Scientific Method in Threat Hunting

Threat hunting follows a process similar to scientific research.

---

# Hunting Methodology

```text
Observation
      ↓
Hypothesis
      ↓
Testing
      ↓
Analysis
      ↓
Conclusion
```

---

# Example

Observation:

```text
Multiple PowerShell Executions
```

Hypothesis:

```text
Potential attacker PowerShell abuse.
```

Testing:

Search telemetry.

Conclusion:

Validate or reject.

---

# Security Insight

Strong hunters rely on:

- evidence
- telemetry
- context

NOT assumptions.

---

# 5. Documentation & Knowledge Sharing

One of the most overlooked threat hunting skills.

---

# Important Principle

A hunt is valuable even when:

```text
No Threat Found
```

---

# Why?

Because analysts still learn:

- normal behavior
- environmental baselines
- monitoring weaknesses
- detection gaps
- operational context

---

# Professional Hunt Documentation

Should include:

- hypothesis
- methodology
- searches used
- findings
- recommendations
- lessons learned

---

# Operational Security Insight

Threat hunting improves organizational knowledge over time.

Every hunt contributes to:

- better detections
- stronger visibility
- improved investigations

---

# 6. Organizational Knowledge

Threat hunters leverage existing organizational intelligence.

---

# Common Sources

- previous incidents
- threat intelligence
- attack reports
- historical investigations
- business context

---

# Example

If the organization recently experienced:

```text
Phishing Campaigns
```

Threat hunters may investigate:

- suspicious authentication events
- mailbox access
- MFA abuse
- impossible travel logins

---

# Why This Matters

Threat hunting should align with:

- organizational risks
- threat landscape
- business priorities

---

# 7. Measuring Threat Hunting Success

A hunt is NOT successful only when:

```text
Threat Found
```

---

# Successful Outcomes Include

- improved detections
- refined monitoring
- stronger baselines
- improved visibility
- reduced blind spots

---

# Key Security Insight

Threat hunting is a continuous improvement process.

Even unsuccessful hunts can improve:

- SOC operations
- detection engineering
- security posture

---

# 8. Baseline Analysis

One of the MOST important hunting concepts.

---

# What is a Baseline?

A baseline represents:

> normal behavior.

---

# Example

Normal user activity:

```text
20 logins/day
```

Observed activity:

```text
400 logins/day
```

Potential anomaly.

---

# Why Baselines Matter

Threat hunters search for:

```text
Deviation From Normal
```

instead of:

```text
Known Bad Activity Only
```

---

# Operational Security Insight

Strong security monitoring depends heavily on:

- behavioral understanding
- environmental baselines
- context-aware investigations

---

# 9. Statistical Analysis in Threat Hunting

Modern threat hunting frequently uses statistics.

---

# Standard Deviation

Measures variation from normal behavior.

---

# Example

Average:

```text
100 requests
```

Normal range:

```text
90-110
```

Observed:

```text
1000 requests
```

Potential anomaly.

---

# Cardinality

Measures:

> number of unique values.

---

# Example

```text
10 unique IPs
```

vs

```text
5000 unique IPs
```

High cardinality may indicate:

- scanning
- automation
- suspicious behavior

---

# Interquartile Range (IQR)

Used for:

- anomaly detection
- identifying outliers
- understanding data spread

---

# Why Hunters Use IQR

IQR helps identify:

```text
Unexpected Outliers
```

while reducing sensitivity to extreme values.

---

# Analyst Mindset

Never assume:

```text
Outlier = Attack
```

Instead:

```text
Outlier + Context = Investigation
```

This is a critical hunting principle.

---

# 10. Environmental Context

Context determines whether activity is suspicious.

---

# Example

```text
5 TB Data Transfer
```

May appear suspicious.

However:

```text
Scheduled Backup Window
```

makes it normal.

---

# Key Insight

Threat hunters must understand:

- users
- systems
- business operations
- maintenance activities

before drawing conclusions.

---

# 11. Threat Hunting Tools

Several tools support threat hunting operations.

---

# SPL (Search Processing Language)

The most important hunting tool covered.

Used for:

- searching telemetry
- correlation
- anomaly analysis
- investigation workflows

---

# Regular Expressions (Regex)

Used for:

- pattern matching
- extraction
- parsing logs
- identifying anomalies

---

# Why These Matter

Effective hunting depends heavily on:

- search capability
- data visibility
- analytical flexibility

---

# 12. Model-Assisted Threat Hunting (M-ATH)

Advanced threat hunting concept.

Very relevant to modern SOC environments.

---

# Definition

Model-Assisted Threat Hunting (M-ATH) uses:

> Machine Learning to support threat hunting activities.

---

# Why M-ATH Exists

Modern organizations generate:

- billions of events
- millions of logs
- massive telemetry datasets

Manual analysis alone becomes difficult.

---

# M-ATH Workflow

```text
Data Collection
      ↓
Data Cleaning
      ↓
Data Labeling
      ↓
Model Training
      ↓
Model Testing
      ↓
Threat Detection
```

---

# Stage 1 — Data Preparation

Ensure:

- accurate data
- clean telemetry
- quality labels

---

# Stage 2 — Model Selection

Choose algorithms based on:

- use case
- hunting objective
- available data

---

# Stage 3 — Refinement

Improve:

- precision
- recall
- accuracy
- detection quality

---

# Stage 4 — Real-World Validation

Validate models against:

- actual attacks
- production telemetry
- known threats

---

# Why M-ATH Matters

Machine learning can help identify:

- hidden patterns
- subtle anomalies
- stealthy adversaries
- behavioral deviations

that may be difficult for humans to identify manually.

---

# 13. Threat Hunter vs SOC Analyst

Important distinction.

---

| SOC Analyst | Threat Hunter |
|---|---|
| Investigates Alerts | Searches for Hidden Threats |
| Reactive | Proactive |
| Detection Focused | Discovery Focused |
| Incident Driven | Hypothesis Driven |

---

# Career Insight

Threat hunting combines:

- SOC operations
- detection engineering
- threat intelligence
- behavioral analytics
- investigation methodology

making it one of the most advanced blue-team disciplines.

---

# SOC Analyst Perspective

This module teaches:

> don't wait for alerts.

Instead:

- understand normal behavior
- form hypotheses
- search proactively
- identify anomalies
- improve detections continuously

This mindset separates:

- average defenders

from

- advanced defenders.

---

# Real Enterprise Relevance

This module directly connects to:

- Threat Hunting
- Detection Engineering
- Security Analytics
- SOC Operations
- Threat Intelligence
- Behavioral Monitoring
- Cloud Security Monitoring

---

# Interview-Level Questions

## Q1. What is Threat Hunting?

Proactive search for hidden threats that may bypass traditional detections.

---

## Q2. What is the PEAK Framework?

| Phase | Purpose |
|---|---|
| Prepare | Build hypothesis and scope |
| Execute | Conduct hunt |
| Act | Improve defenses |

---

## Q3. What is a Baseline?

A representation of normal behavior used to identify anomalies.

---

## Q4. Why is context important in threat hunting?

Because not every anomaly is malicious.

---

## Q5. What is M-ATH?

Model-Assisted Threat Hunting using machine learning techniques to assist threat discovery.

---

# Important Revision Sheet

| Concept | Meaning |
|---|---|
| Threat Hunting | Proactive threat discovery |
| PEAK | Prepare → Execute → Act |
| Baseline | Normal behavior |
| Hypothesis Hunt | Test a theory |
| Topic-Based Hunt | Hunt specific threat category |
| Data-Based Hunt | Hunt from data source |
| Cardinality | Number of unique values |
| Standard Deviation | Measure of variation |
| IQR | Statistical outlier detection |
| M-ATH | Machine learning-assisted hunting |

---

# Analyst Takeaways

- Threat hunting focuses on proactive threat discovery
- PEAK provides a structured hunting methodology
- Baselines are critical for anomaly detection
- Context is essential when evaluating suspicious behavior
- Statistical analysis supports advanced hunting workflows
- Machine learning is becoming increasingly important in modern threat hunting

---

# SOC / Splunk Relevance

Splunk enables threat hunters to:

- search large telemetry datasets
- test hypotheses
- identify anomalies
- investigate suspicious activity
- improve detections
- develop behavioral hunts

This module directly influences:

- Threat Hunting
- Detection Engineering
- Security Analytics
- SIEM Operations
- Behavioral Monitoring

---

# Real-World Security Connections

- Modern APT groups often evade traditional signature-based detections
- Threat hunting helps reduce attacker dwell time
- Behavioral analytics increasingly powers enterprise detections
- Cloud environments generate massive datasets that benefit from hunting methodologies
- Machine learning is becoming more common in advanced SOC operations

---

# Potential Detection Opportunities

Possible hunting opportunities related to this module:

- unusual PowerShell activity
- abnormal authentication behavior
- rare outbound connections
- privilege escalation anomalies
- suspicious cloud activity
- high-cardinality network events
- deviation from user baselines

---

# MOST IMPORTANT TAKEAWAY

This module introduces:

> proactive security operations.

You are now learning how to:

- think like a threat hunter
- build hypotheses
- establish baselines
- analyze anomalies
- improve detections continuously

This is one of the most valuable skills in:

- Threat Hunting
- Detection Engineering
- Security Analytics
- Advanced SOC Operations
- Modern Cloud Security Monitoring

And for a future Security Engineer, Detection Engineer, or Security Architect, this may be one of the most important modules in the entire Cisco Cybersecurity Defense Analyst path.

---
