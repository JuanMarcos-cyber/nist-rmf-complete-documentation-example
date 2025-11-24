# Security Assessment Report (SAR)  
**System:** eCommerceCo Cloud-Based Platform  
**Stage:** RMF – Assess  
**Author:** Juan Marcos Lázaro  

---

## A. Purpose

The SAR provides an in-depth summary of:

- Control testing  
- Results (PASS / PARTIAL)  
- Evidence reviewed  
- Recommendations  
- Residual risks  

It complements `ASSESSMENT.md` and feeds directly into the **Authorize** and **POA&M** stages.

---

## B. Controls Tested (Detailed)

| Control | Result | Evidence | Notes |
|---------|--------|----------|-------|
| **AC-2 – Account Management** | PASS | IAM configuration, CloudTrail logs | Access lifecycle well controlled |
| **IA-5 – Authenticator Management** | PASS | Password policy, key rotation logs | Keys and tokens are well governed |
| **AU-6 – Audit Review** | PASS | SIEM dashboards, alert rules | Alerts functional and reviewed daily |
| **CM-6 – Configuration Settings** | PARTIAL | Terraform configs, PR records | Missing enforcement in some pipelines |
| **SC-13 – Cryptographic Protection** | PASS | TLS scan, KMS configuration | Meets strong cryptographic standards |
| **IR-4 – Incident Handling** | PASS | IR plan, playbooks, prior IR tickets | Team well prepared |
| **SI-4 – Monitoring** | PASS | CloudTrail/GD logs, SIEM events | Anomalies detected effectively |
| **AC-17 – Remote Access** | PARTIAL | Zero-trust rollout records | Legacy VPN fallback still exists |

---

## C. Gap Analysis Summary

### **1. AC-17 – Remote Access**
- Zero-Trust not fully deployed  
- Legacy VPN fallback → elevated exposure  
- **Risk:** Moderate  
- **Recommendation:** Complete ZT rollout in 90 days  

### **2. CM-6 – Configuration Settings**
- Baseline hardened images exist  
- Enforcement in CI/CD not universal  
- **Risk:** Moderate  
- **Recommendation:** Enforce automated compliance scans  

---

## D. Residual Risk Summary

| Residual Risk | Description | Severity | Owner |
|----------------|-------------|----------|-------|
| Remote Access Gap | Legacy VPN path still active | Moderate | CTO |
| CI/CD Hardening Gap | Missing enforcement on pipelines | Moderate | DevOps Lead |

---

## E. Strengths Observed

- Excellent IAM and least privilege discipline  
- High-quality SIEM correlation and alerting  
- Strong cryptographic controls  
- Mature DevSecOps integration  
- Consistent incident response practices  

---

## F. Assessment Conclusion

The eCommerceCo system demonstrates a **high level of control maturity**.  
Residual risks are limited and manageable and have been assigned for timely remediation.

The system is ready to proceed to the **Authorize** stage with conditional approval.

---

## G. Next Steps

- Add gaps to `POAM.md`  
- Continue evidence updates  
- Prepare authorization briefing package  


