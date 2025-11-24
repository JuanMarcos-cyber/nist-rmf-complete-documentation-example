# NIST RMF – Assess Stage  
**Organization:** eCommerceCo  
*All names appearing in this document are fictitious and used solely for educational and illustrative purposes.*

---

## A. Purpose of the Assess Stage

The Assess stage verifies whether the security controls selected and implemented by eCommerceCo:

- Are correctly deployed  
- Function as intended  
- Produce the required security outcomes  
- Have sufficient evidence available for authorization  

Assessment activities follow **NIST SP 800-53A Rev.5** using examination, interviews, and technical testing.

---

## B. Assessment Methodology

eCommerceCo follows a structured assessment approach:

### **1. Examination**
Review of documentation, configurations, logs, policies, diagrams, and evidence artifacts.

Examples examined:
- IAM policies  
- Network diagrams  
- CI/CD pipeline security configurations  
- SIEM dashboards  
- Encryption settings  
- Incident response playbooks  

### **2. Interviews**
Interviews conducted with:

- Security Director  
- DevOps Lead  
- CTO  
- Compliance Manager  
- Engineering Managers  

Purpose:
- Validate processes  
- Confirm alignment between policy and operational reality  
- Understand risk-based decisions  

### **3. Technical Testing**
Hands-on validation including:

- IAM role and permission testing  
- MFA enforcement verification  
- API authentication tests  
- Log generation and SIEM correlation testing  
- Vulnerability scanning of container images  
- Configuration analysis of cloud resources  

Testing tools may include:
- AWS CLI / GCP CLI  
- Splunk / ELK  
- Nessus / Trivy  
- Automated scripts  
- CI/CD security scanners  

---

## C. Assessment Summary

Below is the high-level summary of tested controls.

| Control ID | Control Name | Assessment Result | Notes |
|------------|--------------|-------------------|-------|
| **AC-2** | Account Management | PASS | IAM user lifecycle validated; MFA enforced. |
| **IA-5** | Authenticator Management | PASS | Strong token and password policies in place. |
| **AU-6** | Audit Review / Reporting | PASS | SIEM correlation rules functioning correctly. |
| **CM-6** | Configuration Settings | PARTIAL | Baseline image missing pipeline enforcement. |
| **SC-13** | Cryptographic Protection | PASS | Encryption correctly implemented at rest and in transit. |
| **IR-4** | Incident Handling | PASS | Playbooks validated; evidence of prior IR reviews. |
| **SI-4** | System Monitoring | PASS | Alerts triggered appropriately during test events. |
| **AC-17** | Remote Access | PARTIAL | Zero-trust rollout ongoing; deprecating legacy methods. |

---

## D. Detailed Findings

### 1. **AC-2 – Account Management**  
**Result:** PASS  
**Evidence Reviewed:**
- IAM user list  
- Group/role policies  
- HR-driven account lifecycle tickets  
- MFA log samples  

**Tester Notes:**  
Access reviews are consistently performed; privileged accounts well maintained.

---

### 2. **IA-5 – Authenticator Management**  
**Result:** PASS  
**Evidence Reviewed:**
- Password policies  
- Key rotation logs  
- API token expiration configuration  

**Tester Notes:**  
Authenticator controls exceed baseline with strong token lifecycle enforcement.

---

### 3. **AU-6 – Audit Review, Analysis, and Reporting**  
**Result:** PASS  
**Evidence Reviewed:**
- SIEM dashboards  
- Alerting rules  
- Security Incident tickets  

**Tester Notes:**  
Team demonstrates effective analysis and escalation of log-based anomalies.

---

### 4. **CM-6 – Configuration Settings**  
**Result:** PARTIAL  
**Issue Identified:**  
Baseline hardened images created but CI/CD enforcement not active on all pipelines.

**Risk:**  
Non-compliant container images may reach production if manual process is bypassed.

**Recommendation:**  
Enable mandatory pipeline checks for image compliance.

---

### 5. **SC-13 – Cryptographic Protection**  
**Result:** PASS  
**Evidence Reviewed:**
- TLS configuration validation  
- Database encryption settings  
- KMS configuration export  

**Tester Notes:**  
No deviations detected; strong encryption posture.

---

### 6. **IR-4 – Incident Handling**  
**Result:** PASS  
**Evidence Reviewed:**
- IR plan  
- Roles/responsibilities  
- Prior incident review reports  

**Tester Notes:**  
Procedures are well-documented; simulations performed regularly.

---

### 7. **SI-4 – System Monitoring**  
**Result:** PASS  
**Evidence Reviewed:**
- Monitoring alerts  
- GuardDuty findings  
- API anomaly detection  

**Tester Notes:**  
Monitoring is proactive with threshold-based alerts and anomaly detections.

---

### 8. **AC-17 – Remote Access**  
**Result:** PARTIAL  
**Issue Identified:**  
Zero-trust remote access migration is ongoing; legacy VPN still in fallback mode.

**Risk:**  
Legacy VPN may expose wider network surface compared to ZTNA

**Recommendation:**  
Accelerate deprecation of legacy VPN and update documentation accordingly.

---

## E. Overall Assessment Results

### **Summary by Status**

| Status | Count | Description |
|--------|-------|-------------|
| **PASS** | 6 | Controls fully implemented and effective |
| **PARTIAL** | 2 | Controls need improvement or completion |
| **FAIL** | 0 | No failed controls in scope |
| **NOT APPLICABLE** | Inherited | Covered by cloud provider or not relevant |

---

## F. Key Recommendations

1. **Enable automated CI/CD compliance checks** for container image hardening.  
2. **Complete Zero-Trust rollout** to eliminate legacy VPN dependence.  
3. **Continue expanding API logging** to include low-frequency endpoints.  
4. **Implement quarterly purple-team exercises** to stress-test detection and response.  
5. **Create a unified evidence repository** for easier future audits.

---

## G. Assessment Conclusion

The eCommerceCo system demonstrates a **strong control environment**, with:

- High maturity in IAM, logging, monitoring  
- Robust incident response procedures  
- Effective encryption measures  
- Identified gaps that are already part of improvement roadmap  

Residual risks are **manageable** and will be addressed in the POA&M.

The system is recommended to proceed to the **Authorize** stage once partial implementations are remediated.

---

## H. Approvals

| Name | Role | Signature | Date |
|------|------|-----------|------|
| Security Director | Assessment Lead |  |  |
| Compliance Manager | Reviewer |  |  |
| CTO | Final Approver |  |  |
