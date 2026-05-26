# Module 1 — Cybersecurity Foundations & Risk Fundamentals

## Cisco Cybersecurity Defense Analyst (Splunk)

---

# 1. Core Learning Objectives

## Historic High-Profile Security Events

Understanding major breaches helps analysts recognize:

- attack patterns
- attacker motivations
- organizational weaknesses
- security failures

### Examples

| Incident | Key Lesson |
| --- | --- |
| Target Breach (2013) | Third-party/vendor risk |
| WannaCry Ransomware | Importance of patching |
| Equifax Breach | Unpatched vulnerabilities |
| SolarWinds Attack | Supply chain compromise |
| Colonial Pipeline | Critical infrastructure risk |

---

# 2. Impact of Security Events

Cyberattacks are NOT just technical problems.

They create:

- financial loss
- reputational damage
- operational disruption
- legal/compliance consequences
- customer trust erosion

---

## Types of Costs

| Type | Example |
| --- | --- |
| Direct Costs | Incident response, recovery |
| Indirect Costs | Downtime, lost customers |
| Regulatory Costs | GDPR/PCI/HIPAA fines |
| Long-Term Costs | Brand damage |

---

# 3. Information Assurance (IA)

## Definition

Information Assurance ensures:

- data remains protected
- systems remain trustworthy
- business operations remain functional

---

# 4. CIA Triad — MOST IMPORTANT CONCEPT

This is one of the foundational concepts in cybersecurity.

| Principle | Meaning | Example |
| --- | --- | --- |
| Confidentiality | Prevent unauthorized access | Encryption, MFA |
| Integrity | Prevent unauthorized modification | Hashing, checksums |
| Availability | Ensure systems/data are accessible | Backups, redundancy |

---

# CIA Examples

## Confidentiality

Goal:

Only authorized users can access data.

Controls:

- Encryption
- Access Control
- MFA
- RBAC

---

## Integrity

Goal:

Ensure data is accurate and untampered.

Controls:

- Hashing
- Digital signatures
- File integrity monitoring

---

## Availability

Goal:

Ensure systems remain operational.

Controls:

- Load balancing
- Disaster recovery
- Redundancy
- Backups

---

# 5. Security Standards, Controls & Frameworks

## Purpose

Frameworks provide structured security guidance.

---

## Common Frameworks

| Framework | Purpose |
| --- | --- |
| NIST CSF | Cybersecurity risk management |
| ISO 27001 | Information security management |
| CIS Controls | Practical security controls |
| MITRE ATT&CK | Adversary tactics & techniques |
| PCI-DSS | Payment card security |
| SOC 2 | Service organization security |

---

# 6. Risk Management Process

## Basic Flow

```
Identify Risk
      ↓
Assess Risk
      ↓
Prioritize Risk
      ↓
Mitigate Risk
      ↓
Monitor Risk
```

---

## Important Terms

| Term | Meaning |
| --- | --- |
| Threat | Potential danger |
| Vulnerability | Weakness |
| Risk | Threat exploiting vulnerability |
| Asset | Valuable resource |
| Mitigation | Risk reduction action |

---

# Example

## Scenario

Server has outdated software.

| Component | Example |
| --- | --- |
| Asset | Web server |
| Vulnerability | Unpatched software |
| Threat | Remote attacker |
| Risk | Server compromise |
| Mitigation | Apply patches |

---

# 7. Core SOC Analyst Skills

---

## Researching

Security analysts constantly:

- investigate alerts
- analyze IOCs
- study malware
- monitor threats

---

## Constant Learning

Cybersecurity evolves rapidly:

- new vulnerabilities
- new malware
- new attack techniques
- new tooling

Learning never stops.

---

## Communication

Analysts must explain:

- incidents
- risks
- findings
- recommendations

to both:

- technical teams
- non-technical stakeholders

---

## Prioritization

SOC analysts cannot investigate every alert equally.

They must prioritize based on:

- severity
- business impact
- likelihood
- active exploitation

---

# SOC Perspective (IMPORTANT)

This module is introducing the mindset of:

> “business-oriented cybersecurity.”
> 

Security analysts do NOT just:

- monitor logs
- investigate alerts

They protect:

- business operations
- data
- customers
- infrastructure

---

# Real Enterprise Relevance

This module directly connects to:

- SOC operations
- Detection engineering
- Incident response
- Cloud security
- Threat hunting
- Governance & compliance

---

# Interview-Level Questions

## Q1. What is the CIA triad?

Framework defining:

- Confidentiality
- Integrity
- Availability

Core principles of information security.

---

## Q2. Difference between threat and vulnerability?

| Threat | Vulnerability |
| --- | --- |
| Potential danger | Weakness exploitable by threat |

---

## Q3. Why is prioritization important in SOCs?

Because analysts handle large alert volumes and must focus on:

- high-risk threats
- critical assets
- active incidents

---

# Important Terms Revision Sheet

| Term | Quick Meaning |
| --- | --- |
| CIA Triad | Core security principles |
| Risk | Threat exploiting vulnerability |
| Threat | Potential attacker/danger |
| Vulnerability | Weakness |
| Asset | Valuable resource |
| Mitigation | Risk reduction |
| NIST | Security framework |
| MITRE ATT&CK | Adversary behavior framework |

---

# Analyst Takeaways

- Cybersecurity incidents create both technical and business impact
- Risk management is a continuous operational process
- SOC analysts must prioritize incidents based on severity and business relevance
- Security frameworks help standardize organizational defense strategies
- CIA triad principles influence detection and security architecture decisions

# SOC / Splunk Relevance

SIEM platforms like Splunk help SOC analysts:

- aggregate logs from multiple systems
- correlate suspicious activity
- prioritize alerts
- investigate incidents
- improve organizational visibility

Many concepts introduced in this module directly influence:

- detection engineering
- alert triage
- incident escalation
- security monitoring workflows

# Real-World Security Connections

- The Equifax breach demonstrated the impact of unpatched vulnerabilities
- SolarWinds highlighted the dangers of supply chain compromise
- Colonial Pipeline emphasized how cyberattacks affect critical infrastructure and business continuity

# Potential Detection Opportunities

Possible SOC detections related to this module:

- excessive failed login attempts
- unauthorized privilege escalation
- suspicious third-party/vendor access
- vulnerable or unpatched systems
- abnormal network behavior

# Next Module Focus

- SIEM workflows
- Log aggregation
- Alert correlation
- Security monitoring
