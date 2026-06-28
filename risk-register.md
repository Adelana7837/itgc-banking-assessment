# Risk Register — ITGC Assessment, Banking Environment

**Version:** 1.0 | **Classification:** Confidential — Internal Audit  
**Rating Scale:** Likelihood (1–5) × Impact (1–5) = Inherent Risk Score (1–25)

---

## Risk Rating Matrix

| Score | Rating | Action Required |
|---|---|---|
| 20–25 | 🔴 Critical | Immediate escalation; remediate within 30 days |
| 13–19 | 🟠 High | Remediate within 90 days; CISO sign-off required |
| 6–12 | 🟡 Medium | Remediate within 180 days; management action plan |
| 1–5 | 🟢 Low | Monitor; remediate in next planning cycle |

---

## Risk Register

### RR-001 — Unauthorised Access to Core Banking Systems
| Attribute | Detail |
|---|---|
| **Risk Domain** | User Access Management |
| **Risk Description** | Orphaned privileged accounts and absence of MFA create pathways for unauthorised access to core financial systems, enabling fraud, data theft, or system manipulation |
| **Threat Actor** | Insider threat; external attacker with stolen credentials |
| **Likelihood** | 4 — Likely (multiple orphaned accounts confirmed in sampling) |
| **Impact** | 5 — Critical (direct access to financial transactions and customer data) |
| **Inherent Risk Score** | **20 — Critical** |
| **Current Controls** | Access provisioning process; periodic (but inconsistent) reviews |
| **Control Gap** | No quarterly recertification; MFA absent on CBS; 9 orphaned accounts active |
| **Residual Risk** | 18 — High |
| **Related Finding** | F-001, F-002 |
| **Owner** | CISO |
| **Target Remediation** | 30 days |

---

### RR-002 — Data Breach via Credential Compromise
| Attribute | Detail |
|---|---|
| **Risk Domain** | Password Policies |
| **Risk Description** | Weak password policy (min 8 chars, 180-day expiry, no complexity enforcement) significantly increases the probability of credential compromise through brute force, dictionary attacks, or phishing |
| **Threat Actor** | External attacker; malicious insider |
| **Likelihood** | 4 — Likely |
| **Impact** | 5 — Critical |
| **Inherent Risk Score** | **21 — Critical** |
| **Current Controls** | Password policy exists; account lockout after 5 attempts |
| **Control Gap** | No complexity enforcement; no MFA; extended expiry period |
| **Residual Risk** | 16 — High |
| **Related Finding** | F-002 |
| **Owner** | CISO / IT Operations |
| **Target Remediation** | 30 days |

---

### RR-003 — Regulatory Non-Compliance (Log Retention)
| Attribute | Detail |
|---|---|
| **Risk Domain** | Logging & Monitoring |
| **Risk Description** | Current log retention of 90 days falls below the 12-month minimum required by CBN Guidelines on Cybersecurity and data protection regulation. In the event of a breach, forensic investigation capability is severely limited |
| **Threat Actor** | Regulatory / Audit body |
| **Likelihood** | 4 — Likely (policy gap is factual) |
| **Impact** | 4 — High (regulatory sanction, reputational damage, inability to investigate incidents) |
| **Inherent Risk Score** | **19 — High** |
| **Current Controls** | SIEM in place; partial log collection |
| **Control Gap** | 90-day retention vs. 12-month requirement; legacy module excluded |
| **Residual Risk** | 15 — High |
| **Related Finding** | F-005, F-006 |
| **Owner** | IT Security / CISO |
| **Target Remediation** | 60 days |

---

### RR-004 — Undetected Security Events
| Attribute | Detail |
|---|---|
| **Risk Domain** | Logging & Monitoring |
| **Risk Description** | Legacy core banking module excluded from SIEM creates a monitoring blind spot. Malicious activity originating from or targeting the CBS cannot be detected in real-time |
| **Threat Actor** | Insider threat; external attacker |
| **Likelihood** | 4 — Likely |
| **Impact** | 4 — High |
| **Inherent Risk Score** | **18 — High** |
| **Current Controls** | SIEM covers 78% of systems |
| **Control Gap** | CBS excluded; no compensating manual review process |
| **Residual Risk** | 14 — High |
| **Related Finding** | F-006 |
| **Owner** | IT Security |
| **Target Remediation** | 90 days |

---

### RR-005 — Unapproved or High-Risk System Changes
| Attribute | Detail |
|---|---|
| **Risk Domain** | Change Management |
| **Risk Description** | Emergency changes bypassing CAB approval and missing rollback plans increase the risk of system instability, unintended data corruption, or introduction of vulnerabilities in production |
| **Threat Actor** | Operational error; malicious change |
| **Likelihood** | 3 — Possible |
| **Impact** | 5 — Critical |
| **Inherent Risk Score** | **15 — High** |
| **Current Controls** | CAB process; change tracking in ITSM tool |
| **Control Gap** | Emergency bypass; rollback absent in 38% of changes |
| **Residual Risk** | 12 — Medium |
| **Related Finding** | F-004, F-008 |
| **Owner** | IT Operations Manager |
| **Target Remediation** | 60 days |

---

### RR-006 — Third-Party Service Failure / Supply Chain Risk
| Attribute | Detail |
|---|---|
| **Risk Domain** | Vendor Management |
| **Risk Description** | Absence of current security assurance for 40% of critical vendors and lack of sub-processor visibility creates unmanaged third-party risk, potentially exposing customer data or causing service disruption |
| **Threat Actor** | Third-party failure; supply chain attack |
| **Likelihood** | 3 — Possible |
| **Impact** | 4 — High |
| **Inherent Risk Score** | **13 — High** |
| **Current Controls** | Vendor register; contractual security clauses |
| **Control Gap** | Outdated SOC 2 reports; no sub-processor tracking |
| **Residual Risk** | 10 — Medium |
| **Related Finding** | F-007 |
| **Owner** | IT Procurement / CISO |
| **Target Remediation** | 90 days |

---

### RR-007 — Slow / Ineffective Incident Response
| Attribute | Detail |
|---|---|
| **Risk Domain** | Incident Management |
| **Risk Description** | Outdated IRP and absence of annual exercises mean the bank is unprepared to respond to a major cyber incident, resulting in prolonged outages, increased data loss, and regulatory reporting failures |
| **Threat Actor** | Any threat (ransomware, DDoS, insider) |
| **Likelihood** | 3 — Possible |
| **Impact** | 4 — High |
| **Inherent Risk Score** | **12 — Medium** |
| **Current Controls** | Incident classification; ITSM ticketing |
| **Control Gap** | IRP 3 years out of date; no tabletop exercise in current year |
| **Residual Risk** | 10 — Medium |
| **Related Finding** | F-003 |
| **Owner** | CISO / IT Operations |
| **Target Remediation** | 60 days |

---

### RR-008 — Physical Intrusion to Data Centre
| Attribute | Detail |
|---|---|
| **Risk Domain** | Physical Security |
| **Risk Description** | Unauthorised physical access to data centre infrastructure enabling hardware theft, data exfiltration, or sabotage |
| **Likelihood** | 1 — Rare |
| **Impact** | 5 — Critical |
| **Inherent Risk Score** | **5 — Low** |
| **Current Controls** | Biometric + badge access; CCTV; visitor escort; quarterly reviews |
| **Control Gap** | None identified |
| **Residual Risk** | 3 — Low |
| **Related Finding** | None |
| **Owner** | Facilities / IT Operations |
| **Target Remediation** | No action required |

---

### RR-009 — Backup Failure / Data Loss
| Attribute | Detail |
|---|---|
| **Risk Domain** | Backup & Recovery |
| **Risk Description** | Failure of backup processes resulting in inability to recover financial data following system failure or ransomware attack |
| **Likelihood** | 1 — Rare |
| **Impact** | 5 — Critical |
| **Inherent Risk Score** | **4 — Low** |
| **Current Controls** | Daily backups; offsite replication; quarterly recovery tests; RTO/RPO met |
| **Control Gap** | None identified |
| **Residual Risk** | 2 — Low |
| **Related Finding** | None |
| **Owner** | IT Operations |
| **Target Remediation** | Continue monitoring |

---

*Document Owner: Lead Auditor | Review Frequency: Each Audit Cycle*
