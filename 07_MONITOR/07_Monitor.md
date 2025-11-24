# NIST RMF – Monitor Stage  
**Organization:** eCommerceCo  
*All names appearing in this document are fictitious and used solely for educational and illustrative purposes.*

---

## A. Purpose of the Monitor Stage

The Monitor stage ensures that:

- Controls remain effective  
- New risks are identified promptly  
- Evidence is continuously collected  
- The system maintains readiness for future audits  
- RMF compliance is sustained over time  

This is a **continuous, repeatable cycle** integrated into daily operations.

---

## B. Monitoring Strategy Overview

eCommerceCo uses a **Continuous Monitoring (ConMon)** program with:

- Automated security tools  
- Cloud-native logging  
- SIEM correlation  
- Ticketing integration  
- Recurring assessments  
- Quarterly reporting to leadership  

The strategy aligns with NIST SP 800-137.

---

## C. Continuous Monitoring Components

### **1. Logging & SIEM Monitoring**
- AWS CloudTrail  
- GCP Audit Logs  
- Application logs  
- API gateway logs  
- Kubernetes/EKS cluster logs  
- VPC Flow Logs  

All logs feed into a central SIEM (Splunk / ELK / Security Hub).

### **2. Threat Detection**
- GuardDuty  
- Cloud IDS / traffic anomaly detection  
- Runtime monitoring for container workloads  
- UEBA (behavior analytics) for user anomalies  

### **3. Vulnerability Management**
- Weekly container scans (e.g., Trivy, Clair)  
- Monthly cloud resource scans  
- Automated dependency scanning in CI/CD  
- Quarterly penetration tests or purple team exercises  

### **4. Configuration Compliance**
- Terraform drift detection  
- AWS Config / GCP Config Monitoring  
- CIS Benchmark conformance checks  
- Alerts on misconfigurations (public buckets, wide IAM roles, etc.)  

---

## D. Control Monitoring Schedule

| Frequency | Monitoring Activities |
|-----------|------------------------|
| **Daily** | SIEM alert review, suspicious login detection, API anomaly analysis |
| **Weekly** | Vulnerability scan review, IAM role deltas, container image checks |
| **Monthly** | Control effectiveness review, compliance metrics, drift detection |
| **Quarterly** | Risk register updates, roadmap adjustments, reporting to leadership |
| **Annually** | Full RMF reassessment, re-authorization readiness review |

---

## E. POA&M Tracking

All corrective actions from the SAR feed into the POA&M.

Tracked attributes:

- Control ID  
- Issue description  
- Risk rating  
- Assigned owner  
- Planned completion date  
- Mitigation evidence  

The POA&M is reviewed monthly and approved quarterly.

---

## F. Incident Response Integration

Continuous monitoring feeds directly into IR workflows:

- Alerts → triage → ticket → investigation  
- Evidence logged automatically in SIEM  
- Post-incident reviews update:
  - Detection rules  
  - Playbooks  
  - Monitoring configurations  

---

## G. Metrics & KPIs

Examples of metrics tracked:

| Metric | Target | Description |
|--------|---------|-------------|
| Mean Time to Detect (MTTD) | < 5 minutes | Time to detect suspicious activity |
| Mean Time to Respond (MTTR) | < 30 minutes | Time to remediate confirmed incidents |
| Patch Timeliness | >= 95% | % of vulnerabilities patched within SLA |
| Log Coverage | 100% | All critical systems sending logs to SIEM |
| Drift Findings | 0 | Expected config drift in IaC-managed resources |

---

## H. Reporting

Monitoring outputs are shared with stakeholders:

- **Security Team:** daily dashboards  
- **Product/Engineering:** monthly security posture updates  
- **Compliance:** evidence bundles for audits  
- **Leadership:** quarterly risk reports  
- **Board:** annual security briefing  

---

## I. Continuous Authorization (cATO) Readiness

eCommerceCo aims to mature toward a **continuous ATO** model with:

- Automated evidence collection  
- Real-time control validation  
- Continuous risk scoring  
- Automated compliance pipelines  

This reduces audit overhead and improves system resilience.

---

## J. Approvals

| Name | Role | Signature | Date |
|------|------|-----------|------|
| Security Director | ConMon Lead |  |  |
| Compliance Manager | Reviewer |  |  |
| CTO | System Owner |  |  |
