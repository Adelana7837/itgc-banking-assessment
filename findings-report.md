# Audit Findings Report — ITGC Assessment, Banking Environment

**Report Type:** IT General Controls Audit  
**Classification:** Confidential — Internal Distribution Only  
**Status:** Final

---

## F-001 — Absence of Access Recertification Process; Orphaned Privileged Accounts

**Rating:** 🔴 Critical  
**Domain:** User Access Management  
**Framework Reference:** COBIT DSS05.04 · ISO/IEC 27001:2022 A.9.2.6

### Condition
During testing of 30 sampled user accounts, 9 accounts were identified as belonging to individuals whose employment had been terminated between 14 and 183 days prior to the testing date. All 9 accounts remained active and held privileged access to the Core Banking System (CBS) and Active Directory. Additionally, no formal quarterly access recertification process was evidenced.

### Criteria
The bank's Access Management Policy (v2.3) requires user access to be revoked within 24 hours of employment termination. COBIT DSS05.04 requires periodic recertification of access rights. ISO/IEC 27001:2022 A.9.2.6 requires formal review of user access rights at regular intervals.

### Cause
The access removal process relies on manual notification from HR to IT. The HR system is not integrated with Active Directory, creating a dependency on timely email communication. The IT team confirmed no formal recertification programme exists.

### Effect
Active accounts belonging to former employees represent a direct pathway for unauthorised access to customer financial data and transaction systems. The risk is amplified by the absence of MFA (see F-002). Nine accounts were active with no business justification.

### Recommendation
1. Immediately disable the 9 identified orphaned privileged accounts
2. Integrate HR offboarding workflow with Active Directory provisioning system
3. Implement a quarterly access recertification process with documented sign-off by line managers
4. Establish a privileged access inventory reviewed by the CISO monthly

**Management Response:** *[Pending]*  
**Target Date:** 30 days

---

## F-002 — Multi-Factor Authentication Not Enforced on Core Systems

**Rating:** 🔴 Critical  
**Domain:** Password Policies  
**Framework Reference:** ISO/IEC 27001:2022 A.9.4.2 · COBIT DSS05.04

### Condition
MFA is not enforced for access to the Core Banking System (CBS), the internet banking administration portal, or the VPN gateway. Password policy review revealed a minimum length of 8 characters (policy states 12), no complexity enforcement, and a 180-day maximum age (policy states 90 days).

### Criteria
The bank's Password Policy (v1.9) mandates MFA for all privileged access and all remote access. ISO A.9.4.2 requires secure log-on procedures including additional authentication where appropriate.

### Cause
MFA implementation for CBS was deferred during the core banking upgrade project in the prior year and has not been rescheduled. Password GPOs were updated partially — server settings were not pushed to the CBS environment.

### Effect
Without MFA, a single compromised password provides full access to core financial systems. Combined with F-001 (orphaned accounts), an attacker in possession of one former employee's credentials faces no additional authentication barrier.

### Recommendation
1. Enforce MFA immediately for all privileged accounts and VPN access
2. Implement CBS MFA integration within 30 days — include in project roadmap
3. Correct GPO settings for CBS environment to align with Password Policy v1.9
4. Review and test password settings quarterly

**Management Response:** *[Pending]*  
**Target Date:** 30 days

---

## F-003 — Incident Response Plan Outdated; No Annual Exercise Conducted

**Rating:** 🟠 High  
**Domain:** Incident Management  
**Framework Reference:** COBIT DSS02.01 · ISO/IEC 27001:2022 A.16.1.1

### Condition
The current Incident Response Plan (IRP) is dated March 2021 and has not been reviewed or updated. The current year's tabletop exercise has not been conducted. Of 5 critical (Sev-1) incidents reviewed, 3 exceeded SLA resolution times with no documented escalation to senior management.

### Criteria
The IRP states it shall be reviewed annually. COBIT DSS02.01 and ISO A.16.1 require that incident response capabilities are tested and maintained. Regulatory guidance from relevant banking authorities requires annual IRP exercises.

### Cause
The IRP review was assigned to the IT Operations Manager; however, competing project priorities delayed completion. No formal tracking of IRP review due dates exists.

### Effect
An outdated IRP may not reflect current system architecture, team structures, or threat landscape. The absence of exercises means team members are unfamiliar with their roles during a major incident. Three SLA breaches indicate existing response gaps are already materialising.

### Recommendation
1. Update IRP within 60 days to reflect current environment, roles, and contact lists
2. Conduct a tabletop exercise within 90 days involving IT, Operations, Compliance, and Communications
3. Establish annual IRP review calendar with CISO ownership and tracking
4. Implement SLA breach escalation alerts in ITSM tool

**Management Response:** *[Pending]*  
**Target Date:** 60–90 days

---

## F-004 — Emergency Changes Bypassing CAB Approval

**Rating:** 🟡 Medium  
**Domain:** Change Management  
**Framework Reference:** COBIT BAI06.03

### Condition
Of 280 changes executed in the audit period, 47 (17%) were classified as emergency changes. Of these, 29 had no documented post-implementation CAB approval within 24 hours. Rollback plans were absent in 38% of the full sample of 30 changes tested.

### Criteria
The Change Management Policy requires all emergency changes to receive retrospective CAB approval within 24 hours of implementation.

### Recommendation
Define emergency change eligibility criteria; require retrospective approval and mandatory rollback documentation. Add rollback plan as mandatory field in change request form.

**Target Date:** 60 days

---

## F-005 — Security Log Retention Below Regulatory Minimum

**Rating:** 🟠 High  
**Domain:** Logging & Monitoring  
**Framework Reference:** ISO/IEC 27001:2022 A.12.4.1

### Condition
SIEM log retention is configured at 90 days. Applicable regulatory guidance requires a minimum of 12 months for financial institutions. No archiving mechanism exists to extend effective retention.

### Recommendation
Extend SIEM hot storage or configure automated archiving to cold storage to achieve 12-month total retention. Validate with Compliance team against all applicable regulations.

**Target Date:** 60 days

---

## F-006 — Legacy Core Banking Module Excluded from SIEM

**Rating:** 🟡 Medium  
**Domain:** Logging & Monitoring  
**Framework Reference:** ISO/IEC 27001:2022 A.12.4.1

### Condition
The legacy CBS module does not support standard syslog forwarding and has been excluded from SIEM integration. No compensating control (manual log review) has been implemented.

### Recommendation
Engage CBS vendor for custom log integration options. Implement manual daily review of CBS event logs as compensating control until integration is achieved.

**Target Date:** 90 days

---

## F-007 — Insufficient Vendor Security Assurance Documentation

**Rating:** 🟡 Medium  
**Domain:** Vendor Management  
**Framework Reference:** COBIT APO10.03 · ISO/IEC 27001:2022 A.15.2.1

### Condition
Of 20 critical vendors reviewed, 8 (40%) did not have a current (within 12 months) SOC 2 Type II report on file. No sub-processor inventory existed for any of the top 5 critical vendors.

### Recommendation
Mandate SOC 2 Type II or equivalent annual submission as a contract condition. Build sub-processor disclosure into vendor agreements and collect initial inventories within 90 days.

**Target Date:** 90 days

---

## F-008 — Rollback Plans Absent for 38% of Production Changes

**Rating:** 🟡 Medium  
**Domain:** Change Management  
**Framework Reference:** COBIT BAI06.01

### Condition
Review of 30 sampled production change requests found 11 (38%) lacked a documented rollback or back-out procedure. All 11 related to application-layer changes rather than infrastructure.

### Recommendation
Update the change request form in the ITSM tool to make rollback documentation a mandatory field. CAB reviewers should validate rollback plans before approving changes.

**Target Date:** 45 days

---

*All findings were validated with management before issuance. Management responses to be appended upon receipt.*
