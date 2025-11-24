# NIST RMF – Select Stage  
**Organization:** eCommerceCo  
*All names appearing in this document are fictitious and used solely for educational and illustrative purposes.*

---

## A. Purpose of the Select Stage

The Select stage identifies which NIST SP 800-53 Rev.5 security controls are required to protect the eCommerceCo platform based on its **FIPS 199 categorization** (HIGH overall).  
These controls form the system’s baseline and determine what must be implemented, assessed, and continuously monitored.

---

## B. Applicable Baseline (NIST SP 800-53 Rev.5)

Because the system was categorized as:

- **Confidentiality:** Moderate  
- **Integrity:** High  
- **Availability:** Moderate  
- **Overall Impact:** **HIGH**

…the applicable baseline is:

# **→ HIGH Baseline (NIST SP 800-53 Rev.5)**

This baseline includes **323 controls** (base + enhancements) across all 20 control families.

---

## C. Control Tailoring Summary

eCommerceCo applies tailoring to ensure the control set is relevant to its SaaS cloud-native environment.

### 1. Controls Added (due to business and technical requirements)

| Control ID | Title | Reason for Addition |
|------------|--------|---------------------|
| **AC-2(12)** | Account Monitoring | Needed due to multi-tenant risk and high volume of API access. |
| **IA-5(13)** | Multi-Factor Authentication | Strengthens identity protections for admin/API access. |
| **SC-23** | Session Authenticity | Protects session hijacking in customer/merchant portals. |
| **SI-4(20)** | User and Entity Behavior Analytics (UEBA) | Supports anomaly detection across distributed microservices. |

---

### 2. Controls Removed (Not Applicable)

| Control ID | Reason for Removal |
|-------------|--------------------|
| **PE- Physical Controls** series | Fully inherited from AWS/GCP; eCommerceCo does not manage physical datacenters. |
| **MA-5** | No on-prem hardware requiring maintenance program. |
| **MP** (Media Protection) | No physical removable media used in cloud-native environment. |

---

### 3. Controls With Compensating Measures

| Control | Compensating Measure | Justification |
|---------|-----------------------|---------------|
| **AC-17** (Remote Access) | Enforced via Zero-Trust, identity-based access and cloud-native VPN replacement | Cloud infrastructure replaces traditional remote access paths. |
| **CP-9** (Information System Backup) | Automated encrypted backups + cross-region replication | Cloud-native redundancy exceeds baseline requirement. |

---

## D. Control Selection Summary by Family

Below is the summarized selection outcome for each NIST 800-53 Rev.5 family.

| Control Family | Baseline Requirement | Tailoring Applied | Final Decision |
|----------------|-----------------------|--------------------|----------------|
| **AC – Access Control** | HIGH | Enhancements AC-2(3), AC-2(12) | Included |
| **AU – Audit & Accountability** | HIGH | AU-6 strengthened with SIEM | Included |
| **CM – Configuration Management** | HIGH | No changes | Included |
| **CP – Contingency Planning** | HIGH | CP-9 compensated | Included |
| **IA – Identification & Authentication** | HIGH | IA-5(13) added | Included |
| **IR – Incident Response** | HIGH | No changes | Included |
| **MA – Maintenance** | HIGH | Physical maintenance removed | Partially Included |
| **MP – Media Protection** | HIGH | Not applicable | Removed |
| **PE – Physical & Environmental** | HIGH | All inherited from cloud provider | Removed |
| **PL – Planning** | HIGH | No changes | Included |
| **PM – Program Management** | HIGH | No changes | Included |
| **PS – Personnel Security** | HIGH | No changes | Included |
| **RA – Risk Assessment** | HIGH | No changes | Included |
| **CA – Security Assessment & Authorization** | HIGH | No changes | Included |
| **SC – System & Communications Protection** | HIGH | SC-23 added | Included |
| **SI – System Integrity** | HIGH | SI-4(20) added | Included |

---

## E. Summary of Final Tailored Baseline

### ✔ Total Controls in HIGH Baseline: **323**  
### ✔ Controls Removed: **10**  
### ✔ Controls Added: **5**  
### ✔ Controls With Compensating Measures: **3**  
### ✔ Final Control Count: **318**

This tailored control set ensures:

- Compliance with NIST SP 800-53 Rev.5  
- Compatibility with cloud-native architecture  
- Alignment with PCI DSS, SOC 2, and privacy regulations  
- Appropriate coverage of high-impact integrity requirements  

---

## F. Approvals

| Name | Role | Signature | Date |
|------|------|-----------|------|
| Alicia Washington | Security Director |  |  |
| Marcus Harris | CTO |  |  |
| Compliance Manager | Governance |  |  |

