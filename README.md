# IT General Controls (ITGC) Assessment — Banking Environment
> **IT Audit Portfolio · Project 1**

A comprehensive simulated ITGC audit of a banking environment, evaluating the design and operating effectiveness of IT controls supporting core financial systems.

---

## 📋 Project Overview

| Attribute | Detail |
|---|---|
| **Audit Type** | IT General Controls (ITGC) |
| **Environment** | Simulated Banking Institution |
| **Frameworks** | COBIT 2019 · ISO/IEC 27001:2022 · CISA Audit Methodology |
| **Controls Assessed** | 42 across 8 domains |
| **Overall Opinion** | Needs Improvement |

---

## 🌐 Live Dashboard

👉 **[View the Interactive ITGC Dashboard](https://adelana7837.github.io/itgc-banking-assessment/)**  


The dashboard includes:
- Control testing results across all 8 domains
- Audit findings register with risk ratings
- Risk register heat map
- Executive summary with management action plan

---

## 📁 Repository Structure

```
itgc-banking-assessment/
├── index.html                  # Interactive audit dashboard (GitHub Pages)
├── README.md                   # This file
└── docs/
    ├── audit-plan.md           # ITGC Audit Plan
    ├── testing-checklist.md    # 42-item control testing checklist
    ├── risk-register.md        # Risk register with ratings
    └── executive-summary.md    # Executive summary & management action plan
```

---

## 🔍 Audit Scope

### Control Domains
1. **User Access Management** — Provisioning, recertification, privileged access, SoD
2. **Password Policies** — Complexity, expiry, MFA enforcement
3. **Change Management** — CAB process, emergency changes, rollback procedures
4. **Backup & Recovery** — Schedule adherence, offsite storage, recovery testing
5. **Incident Management** — IRP currency, SLA compliance, tabletop exercises
6. **Logging & Monitoring** — SIEM coverage, retention, alert management
7. **Physical Security** — Data centre access, visitor management, CCTV
8. **Vendor Management** — Due diligence, SLA monitoring, sub-processor risk

---

## 📊 Key Findings Summary

| ID | Finding | Risk |
|---|---|---|
| F-001 | No access recertification; 9 orphaned privileged accounts | 🔴 Critical |
| F-002 | MFA not enforced on core banking systems | 🔴 Critical |
| F-003 | Incident Response Plan outdated (2021); no annual exercise | 🟠 High |
| F-004 | 17% of changes bypass CAB approval process | 🟡 Medium |
| F-005 | Log retention 90 days vs. 12-month regulatory requirement | 🟠 High |
| F-006 | Legacy CBS excluded from SIEM monitoring | 🟡 Medium |
| F-007 | 40% of critical vendors lack current SOC 2 Type II | 🟡 Medium |
| F-008 | Rollback plans absent for 38% of production changes | 🟡 Medium |

---

## ✅ Skills Demonstrated

- **IT Audit Methodology** — Risk-based scoping, attribute sampling, evidence evaluation
- **Framework Application** — COBIT 2019, ISO/IEC 27001:2022, CISA standards
- **Control Testing** — Walkthrough documentation, sample selection, test execution
- **Risk Assessment** — Likelihood × Impact scoring, residual risk evaluation
- **Audit Reporting** — Finding narrative, root cause analysis, management action plans
- **Communication** — Executive-level summary, technical and non-technical audiences

---


```



---

## 📚 Frameworks Reference

- **COBIT 2019** — ISACA Governance and Management framework for enterprise IT
- **ISO/IEC 27001:2022** — International standard for Information Security Management Systems
- **CISA** — Certified Information Systems Auditor audit methodology and standards
- **Basel III / BCBS 239** — Banking regulatory context for data governance

---

## 📄 License

