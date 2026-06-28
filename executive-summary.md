# Executive Summary — ITGC Audit Report
## Banking Environment | IT General Controls Assessment

**To:** Audit Committee / Board Risk Committee  
**From:** IT Audit Team  
**Date:** Current Audit Period  
**Classification:** Confidential

---

## Overall Audit Opinion

> **Needs Improvement** — The IT General Controls environment contains significant deficiencies in User Access Management, Password Policy enforcement, Incident Response, and Logging practices. Immediate management action is required in three areas to reduce the bank's exposure to unauthorised access, data breach, and regulatory sanction.

Physical security and backup/recovery controls are operating effectively and require no immediate remediation.

---

## Key Metrics

| Metric | Result |
|---|---|
| Controls Assessed | 42 |
| Controls Passed | 20 (48%) |
| Controls Partially Effective | 8 (19%) |
| Controls Failed | 15 (36%) |
| Critical / High Findings | 5 |
| Medium Findings | 3 |

---

## Top 3 Areas Requiring Immediate Action

### 1. Access Management & MFA (Critical)
Nine privileged accounts belonging to former employees remain active in core systems. Multi-factor authentication is not enforced on the Core Banking System, internet banking administration, or VPN. This combination presents the highest residual risk in the assessment — a single compromised credential could provide unchallenged access to transaction systems.

**Required action within 30 days:** Disable all orphaned accounts; enforce MFA for all privileged and remote access paths.

### 2. Incident Response Capability (High)
The Incident Response Plan has not been updated since 2021 and no tabletop exercise has been conducted in the current year. Three of five critical incidents reviewed exceeded SLA resolution times with no documented escalation. The bank is not operationally ready to respond to a significant cyber event.

**Required action within 60 days:** Update IRP; schedule and conduct a tabletop exercise with IT, Operations, and Compliance participation.

### 3. Security Log Retention (High)
SIEM log retention is configured at 90 days, significantly below the 12-month minimum required by applicable data protection and banking regulations. Additionally, the legacy core banking module is not integrated with the SIEM, creating a monitoring blind spot on the most critical system.

**Required action within 60 days:** Extend log retention to 12 months; implement compensating manual review for CBS until SIEM integration is complete.

---

## What Is Working Well

- **Backup & Recovery** is a clear strength — daily backups with offsite replication, and a successful recovery test within the last 47 days meeting RTO (4hrs) and RPO (1hr) targets.
- **Physical Security** controls are mature — biometric access, visitor management, CCTV, and quarterly reviews are all functioning as designed.
- **Change Management framework** exists with an active CAB process, though execution gaps remain around emergency changes and rollback documentation.

---

## Management Action Plan Summary

| Priority | Finding | Action | Owner | Due |
|---|---|---|---|---|
| Critical | Orphaned accounts | Disable 9 identified accounts immediately | CISO | 7 days |
| Critical | No MFA on CBS | Enforce MFA — privileged & remote access | CISO | 30 days |
| High | Outdated IRP | Update IRP; conduct tabletop exercise | CISO | 60 days |
| High | Log retention (90d) | Extend SIEM retention to 12 months | IT Security | 60 days |
| High | CBS not in SIEM | Integrate or apply compensating control | IT Security | 90 days |
| Medium | Emergency changes bypass CAB | Revise emergency change policy | IT Operations | 60 days |
| Medium | Vendor assurance gaps | Collect SOC 2 from all critical vendors | Procurement | 90 days |
| Medium | Rollback plans incomplete | Update CAB template; validate at next review | IT Operations | 45 days |

---

## Audit Team Statement

This assessment was conducted in accordance with COBIT 2019, ISO/IEC 27001:2022, and CISA IT Audit Methodology. All findings were validated with process owners prior to issuance. Management responses are recorded in the full Findings Report.

---

*Chief Audit Executive Sign-off Required Before Distribution*
