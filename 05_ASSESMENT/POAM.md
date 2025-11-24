# Plan of Action & Milestones (POA&M)  
**System:** eCommerceCo Cloud-Based Platform  
**Author:** Juan Marcos Lázaro  

---

## A. Purpose

The POA&M tracks:

- Weaknesses identified  
- Severity and impact  
- Remediation plans  
- Assigned owners  
- Completion dates  
- Evidence of closure  

It is a dynamic document updated continuously during monitoring.

---

## B. POA&M Summary

| ID | Control | Weakness | Severity | Owner | Planned Completion | Status |
|----|---------|----------|----------|--------|---------------------|--------|
| POAM-001 | AC-17 | Legacy VPN fallback remains active | Moderate | CTO | +90 days | Open |
| POAM-002 | CM-6 | CI/CD hardening not enforced consistently | Moderate | DevOps Lead | +60 days | Open |
| POAM-003 | AU-12 | Some API endpoints missing full audit logging | Low/Mod | Security Team | +45 days | Open |

---

## C. Detailed Corrective Actions

### **POAM-001 – Zero-Trust Remote Access Completion**
- Remove legacy VPN ingress path  
- Validate IdP-integrated ZT policy  
- Update network diagrams  
- Re-test AC-17  

### **POAM-002 – CI/CD Hardening Enforcement**
- Add mandatory compliance scans  
- Block merges until checks pass  
- Document evidence of pipeline enforcement  
- Validate CM-6 on next assessment  

### **POAM-003 – API Audit Logging Expansion**
- Add missing audit events  
- Update schema for low-frequency endpoints  
- Validate logging via SIEM  
- Re-run AU-12 assessment  

---

## D. Milestone Tracking

| Milestone | Target Date | Status |
|-----------|-------------|--------|
| ZT rollout complete | +90 days | In progress |
| CI/CD enforcement | +60 days | In progress |
| Audit logging full coverage | +45 days | In progress |

---

## E. Review & Approvals

| Name | Role | Signature | Date |
|------|------|-----------|------|
| Security Director | Owner |  |  |
| CTO | Reviewer |  |  |
| Compliance Manager | Auditor |  |  |
