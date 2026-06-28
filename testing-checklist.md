# ITGC Testing Checklist — Banking Environment

**Version:** 1.0 | **Period:** Current Audit Year | **Frameworks:** COBIT 2019 · ISO 27001:2022

---

## Domain 1: User Access Management

| Ref | Control Objective | Framework Ref | Test Procedure | Result |
|---|---|---|---|---|
| UAM-01 | Formal process exists for provisioning user access | COBIT DSS05.04 / ISO A.9.2.1 | Review access request forms and approvals for 30 sampled accounts | ✅ Pass |
| UAM-02 | User access is reviewed at least quarterly | COBIT DSS05.04 / ISO A.9.2.6 | Obtain access review reports for last 4 quarters; verify sign-off | ❌ Fail |
| UAM-03 | Privileged access is restricted and documented | COBIT DSS05.05 / ISO A.9.2.3 | Review privileged account list; confirm need-to-know justifications | ❌ Fail |
| UAM-04 | Access is revoked within 24 hours of termination | COBIT APO07.02 / ISO A.9.2.6 | Sample 10 terminated employees; trace to access removal date | ❌ Fail |
| UAM-05 | Segregation of duties enforced for financial systems | COBIT DSS05.04 / ISO A.6.1.2 | Review role matrix for SOD conflicts on CBS | ⚠️ Partial |
| UAM-06 | Generic/shared accounts are prohibited | ISO A.9.2.1 | Query AD for accounts without individual assignment | ✅ Pass |

---

## Domain 2: Password Policies

| Ref | Control Objective | Framework Ref | Test Procedure | Result |
|---|---|---|---|---|
| PWD-01 | Minimum password length ≥ 12 characters enforced | ISO A.9.4.3 | Extract Group Policy Objects (GPO); inspect password settings | ❌ Fail |
| PWD-02 | Password complexity enabled (upper, lower, number, symbol) | ISO A.9.4.3 | Review GPO complexity settings across all in-scope systems | ❌ Fail |
| PWD-03 | Password maximum age ≤ 90 days | ISO A.9.4.3 | Review GPO max password age policy | ❌ Fail |
| PWD-04 | Password history prevents reuse of last 10 passwords | ISO A.9.4.3 | Inspect password history setting in GPO | ✅ Pass |
| PWD-05 | MFA enforced for privileged and remote access | COBIT DSS05.04 / ISO A.9.4.2 | Confirm MFA configuration for VPN, admin consoles, and CBS | ❌ Fail |
| PWD-06 | Default credentials changed on all systems | ISO A.9.4.3 | Review commissioning checklist for last 5 systems deployed | ✅ Pass |

---

## Domain 3: Change Management

| Ref | Control Objective | Framework Ref | Test Procedure | Result |
|---|---|---|---|---|
| CHG-01 | Formal change request process documented | COBIT BAI06.01 | Review change management policy and procedure | ✅ Pass |
| CHG-02 | All changes approved by Change Advisory Board (CAB) | COBIT BAI06.02 | Sample 30 changes; verify CAB approval in ticketing system | ⚠️ Partial |
| CHG-03 | Emergency changes have post-approval within 24 hours | COBIT BAI06.03 | Identify emergency changes; verify retrospective approval | ❌ Fail |
| CHG-04 | Rollback plan documented for all production changes | COBIT BAI06.01 | Review 30 sampled change requests for rollback documentation | ⚠️ Partial |
| CHG-05 | Changes tested in non-production before deployment | COBIT BAI07.04 | Inspect UAT sign-off for 15 sampled significant changes | ✅ Pass |
| CHG-06 | Post-implementation review conducted for major changes | COBIT BAI06.01 | Confirm PIR completion for all major changes in period | ⚠️ Partial |

---

## Domain 4: Backup & Recovery

| Ref | Control Objective | Framework Ref | Test Procedure | Result |
|---|---|---|---|---|
| BKP-01 | Backup schedule defined and documented for all Tier-1 systems | ISO A.12.3.1 | Review backup policy and schedule matrix | ✅ Pass |
| BKP-02 | Backups completed successfully per schedule | ISO A.12.3.1 | Review 90-day backup job logs; calculate success rate | ✅ Pass |
| BKP-03 | Backup media stored offsite or replicated to alternate DR site | ISO A.12.3.1 | Confirm offsite storage agreement and replication config | ✅ Pass |
| BKP-04 | Recovery test conducted within last 90 days | COBIT DSS04.04 | Obtain recovery test report; verify date and scope | ✅ Pass |
| BKP-05 | RTO and RPO targets met during recovery tests | COBIT DSS04.04 | Review recovery test results against documented RTO/RPO | ✅ Pass |

---

## Domain 5: Incident Management

| Ref | Control Objective | Framework Ref | Test Procedure | Result |
|---|---|---|---|---|
| INC-01 | Incident response plan (IRP) documented and current (≤12 months) | COBIT DSS02.01 / ISO A.16.1.1 | Review IRP — check approval date and version | ❌ Fail |
| INC-02 | Incidents classified by severity with defined SLAs | COBIT DSS02.02 | Review incident classification matrix and SLA definitions | ✅ Pass |
| INC-03 | Critical incidents resolved within SLA | COBIT DSS02.03 | Sample 5 critical incidents; compare resolution to SLA | ❌ Fail |
| INC-04 | Incidents escalated per escalation matrix | COBIT DSS02.02 | Review escalation evidence in 5 critical incident tickets | ❌ Fail |
| INC-05 | Post-incident review (PIR) for critical incidents | COBIT DSS02.05 | Confirm PIR reports for all Sev-1 incidents in period | ⚠️ Partial |
| INC-06 | Tabletop or simulation exercise completed annually | COBIT DSS02.01 | Request evidence of exercise; verify current year | ❌ Fail |

---

## Domain 6: Logging & Monitoring

| Ref | Control Objective | Framework Ref | Test Procedure | Result |
|---|---|---|---|---|
| LOG-01 | All Tier-1 systems generating security logs | ISO A.12.4.1 | Review SIEM coverage inventory against in-scope system list | ⚠️ Partial |
| LOG-02 | Log retention meets regulatory minimum (12 months) | ISO A.12.4.1 | Review SIEM retention configuration | ❌ Fail |
| LOG-03 | SIEM alerts reviewed and actioned daily | ISO A.12.4.1 | Inspect SIEM alert queue; review action logs for 30 days | ⚠️ Partial |
| LOG-04 | Privileged activity logged and reviewed | ISO A.12.4.3 | Confirm logging of admin actions; review quarterly report | ✅ Pass |
| LOG-05 | Log integrity protected (tamper-evident) | ISO A.12.4.2 | Verify log forwarding to read-only SIEM; no local deletion rights | ✅ Pass |

---

## Domain 7: Physical Security

| Ref | Control Objective | Framework Ref | Test Procedure | Result |
|---|---|---|---|---|
| PHY-01 | Data centre access restricted to authorised personnel | ISO A.11.1.1 | Review access control list; verify badge + biometric requirement | ✅ Pass |
| PHY-02 | Visitor access logged and escorted | ISO A.11.1.2 | Review visitor log for last 90 days; confirm escort policy | ✅ Pass |
| PHY-03 | CCTV monitoring in place and footage retained | ISO A.11.1.1 | Confirm CCTV coverage of critical areas; check retention period | ✅ Pass |
| PHY-04 | Physical access reviews conducted quarterly | ISO A.11.1.1 | Obtain quarterly access review sign-off for data centre | ✅ Pass |

---

## Domain 8: Vendor Management

| Ref | Control Objective | Framework Ref | Test Procedure | Result |
|---|---|---|---|---|
| VEN-01 | Critical vendor register maintained and current | COBIT APO10.01 | Review vendor register; check last update date | ✅ Pass |
| VEN-02 | Contracts include security and SLA requirements | COBIT APO10.03 / ISO A.15.1.2 | Review 10 sampled vendor contracts for security clauses | ✅ Pass |
| VEN-03 | Annual due diligence (SOC 2 / ISO cert) for critical vendors | COBIT APO10.03 | Request SOC 2 reports for all critical vendors; check currency | ❌ Fail |
| VEN-04 | SLA performance reviewed at least quarterly | COBIT APO10.04 | Obtain quarterly SLA performance reports for top 10 vendors | ⚠️ Partial |
| VEN-05 | Sub-processor / fourth-party risk assessed | COBIT APO10.03 | Review sub-processor inventory for top 5 critical vendors | ❌ Fail |

---

## Summary

| Domain | Tested | Pass | Partial | Fail |
|---|---|---|---|---|
| User Access Management | 6 | 2 | 1 | 3 |
| Password Policies | 6 | 2 | 0 | 4 |
| Change Management | 6 | 2 | 3 | 1 |
| Backup & Recovery | 5 | 5 | 0 | 0 |
| Incident Management | 6 | 1 | 1 | 4 |
| Logging & Monitoring | 5 | 2 | 2 | 1 |
| Physical Security | 4 | 4 | 0 | 0 |
| Vendor Management | 5 | 2 | 1 | 2 |
| **TOTAL** | **42** | **20** | **8** | **15** |

---

*Legend: ✅ Pass | ⚠️ Partial | ❌ Fail*
