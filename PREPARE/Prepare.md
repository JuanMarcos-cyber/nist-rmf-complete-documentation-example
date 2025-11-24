# NIST RMF – Prepare Stage Activity Template  
**Organization Name:** eCommerceCo  
*All names appearing in this document are fictitious and used for educational and illustrative purposes only.*

---

## A. Stakeholder Identification

### 1. Stakeholder List

| Stakeholder Name / Role | Department / Organization | Primary Interest in Risk Management |
|-------------------------|---------------------------|-------------------------------------|
| Emily Chen – CEO | Executive | Executive sponsor for security initiatives; aligns security with business goals. |
| Marcus Harris – CTO | Technology | Ensures secure architecture and supports the innovation–security balance. |
| Alicia Washington – Security Director | Security | Leads the cybersecurity program; responsible for strategy and implementation. |
| Sanjay Patel – DevOps Lead | DevOps | Integrates security into CI/CD pipeline and infrastructure management. |
| Mia Johnson – Head of Product | Product | Aligns product roadmap with security requirements. |
| Robert Wilson – CFO | Finance | Controls budget; evaluates ROI of security investments. |
| Thomas Lee – VP of Engineering | Engineering | Oversees development; enforces secure coding practices. |
| Sarah Kim – Compliance Manager | Compliance | Manages regulatory alignment (PCI, SOC 2, GDPR, etc.). |
| Jason Rodriguez – Customer Success Manager | Customer Success | Balances merchant experience with secure platform practices. |
| Board of Directors | C-suite / Governance | Provides oversight; demands transparency on risk posture. |
| Merchants | Third Parties | End users of the platform; varying security expectations and compliance needs. |
| Payment Partners (Stripe, Adyen) | Third Parties | Require contractual compliance with strict security standards. |

---

### 2. Stakeholder Role Definition

| Stakeholder | Key Responsibilities in Risk Management | Authority Level | Decision-Making Capacity |
|------------|------------------------------------------|-----------------|--------------------------|
| Emily Chen (CEO) | Executive sponsor; ensures risk management aligns with business strategy. | High | Final approval on strategic security decisions. |
| Marcus Harris (CTO) | Oversees secure system architecture and technology risk mitigation. | High | Decides on technical architecture and investment direction. |
| Alicia Washington (Security Director) | Leads the cybersecurity program; defines and implements risk management strategy. | High | Directs cybersecurity operations and policies. |
| Sanjay Patel (DevOps Lead) | Implements secure DevOps practices; embeds security controls in automation. | Medium | Influences technical risk controls in CI/CD workflows. |
| Mia Johnson (Head of Product) | Ensures security is integrated in product features and lifecycle. | Medium | Prioritizes features with secure design. |
| Robert Wilson (CFO) | Allocates resources for risk mitigation; evaluates financial impact. | High | Approves budget for risk and security investments. |
| Thomas Lee (VP of Engineering) | Enforces secure development practices; mitigates development-related risks. | Medium | Manages engineering priorities to align with risk posture. |
| Sarah Kim (Compliance Manager) | Ensures adherence to PCI, GDPR, SOC 2 and other standards. | Medium | Guides compliance-driven risk responses. |
| Jason Rodriguez (Customer Success Manager) | Balances platform usability with merchant data protection. | Medium | Recommends security changes based on user impact. |
| Board of Directors | Provides oversight and governance; reviews organizational risk exposure. | Very High | Sets overall risk appetite and approves strategic policies. |
| Merchants | Expect reliable and secure services; raise concerns about platform risks. | Low | Feedback influences roadmap and security posture. |
| Payment Partners (Stripe, Adyen) | Require contractual compliance and high security standards. | Medium | Enforce compliance through SLAs and legal agreements. |

---

### 3. Stakeholder Communication Matrix

| Stakeholder | Communication Method | Frequency | Information to Share | Response Expected |
|------------|----------------------|-----------|----------------------|-------------------|
| Executive Leadership (C-suite) | Briefings, dashboards | Semi-annually | Strategic alignment, funding needs, security posture | Funding decisions, strategic guidance |
| Security Team | Stand-ups, reports | Weekly | Incident summaries, system health metrics, emerging threats | Operational adjustments, escalation of critical issues |
| Product & Dev Teams | Sprint planning, code reviews | Bi-weekly | Secure coding updates, backlog security tasks, risk feedback | Remediation actions, backlog reprioritization |
| Compliance Manager | Audit meetings, compliance reports | Monthly | Compliance metrics, audit findings, regulatory changes | Policy updates, audit prep actions |
| Board of Directors | Risk presentations, summaries | Quarterly | Enterprise risk posture, high-level incidents, investment needs | Oversight feedback, governance actions |
| Merchants | Support portal, training webinars | Ongoing | Best practices, changes to platform security policies | Merchant queries, support tickets |
| Payment Partners | Security review reports, compliance check-ins | Quarterly | Security controls validation, SLA compliance | Compliance confirmations, integration feedback |

---

## B. Risk Management Strategy Documentation

### 1. Organizational Risk Management Principles

1. Security is everyone’s responsibility across the organization.  
2. Risk-based decision-making guides prioritization of controls.  
3. Compliance is a baseline; risk reduction is the goal.  
4. Transparency in risk communication is vital for governance.

---

### 2. Risk Tolerance Levels

| Risk Category | Low Tolerance | Medium Tolerance | High Tolerance | Rationale |
|--------------|--------------|------------------|----------------|-----------|
| Financial | Severe financial impact due to fraud or payment processing issues is **not acceptable**. | — | — | Critical for business operations and trust. |
| Operational | — | Temporary bugs or delays with compensating controls (e.g., backups, redundancy). | — | Some disruption tolerated if mitigations are in place. |
| Reputational | Negative media exposure due to data leaks is **not acceptable**. | — | — | Brand trust is a key asset for the business. |
| Legal / Compliance | Regulatory penalties or PCI/GDPR violations are **not acceptable**. | — | — | Legal non-compliance carries significant risk. |
| Security / Privacy | Risks to customer PII or platform security are treated as **high priority**. | — | — | Sensitive data and user trust must be protected. |

---

### 3. Risk Assessment Methodology

**Identification Methods**

- Use NIST SP 800-30 as the primary risk assessment reference.  
- Classify assets and data types (PII, payment data, admin credentials, etc.).  

**Analysis Approach**

- Identify threats, vulnerabilities, likelihood and impact.  
- Apply qualitative scoring; supplement with quantitative analysis where feasible.  

**Evaluation Criteria**

- Likelihood of occurrence.  
- Potential impact on confidentiality, integrity and availability (CIA).  

---

### 4. Risk Governance Structure

- **Top-Level Oversight:**  
  The Security Director provides quarterly risk updates to the Board of Directors and reports directly to the CTO.

- **Risk Management Committee:**  
  Representatives from DevOps, Compliance and Product leadership collaborate on risk decisions and report to the Security Director.

- **Operational Risk Management:**  
  Risk metrics and escalations are reviewed during regular operational meetings; significant issues are escalated formally.

- **Working-Level Implementation:**  
  Risk-related activities are executed by DevOps, Engineering, Compliance and Product teams under their department leads.

---

### 5. Risk Escalation Protocols

| Risk Level | Escalation Threshold | Escalated To | Response Timeframe | Documentation Required |
|-----------|----------------------|--------------|--------------------|------------------------|
| Low | Minor operational deviations | Team lead / Line manager | 3–5 days | Internal ticket or log entry |
| Medium | Moderate issues with potential to grow or delay operations | Security Director | 1–2 days | Incident report |
| High | Risks with significant business or regulatory impact | CTO, CEO, Security Director | 24 hours | Full incident report |
| Critical | Regulatory exposure or major breach requiring board awareness | Compliance Manager, CTO, CEO, Board of Directors | Immediate | IR plan entry + regulatory notification |

---

## C. Initial Risk Tolerance Assessment

### 1. Risk Acceptance Levels

| Risk Level | Financial Impact Range | Operational Impact Description | Acceptance Authority |
|-----------|------------------------|--------------------------------|----------------------|
| Negligible | Minimal or no financial impact | No effect on operations or performance | No action required |
| Low | \$1K–\$10K | Minimal disruption, easily recoverable | Security Team or Risk Analyst |
| Moderate | \$10K–\$100K | Noticeable delays or workarounds needed | Risk Management Committee (with justification) |
| High | \$100K+ | Major operational impact; system/component failure | Executive Leadership (C-suite) with immediate mitigation |
| Severe | \$500K+ | Mission-critical impact; threatens organizational viability | CEO / C-suite and Board approval |

---

### 2. Risk Impact / Likelihood Matrix

| Impact \\ Likelihood | Rare | Unlikely | Possible | Likely | Almost Certain |
|----------------------|------|----------|----------|--------|----------------|
| **Catastrophic** | 5 | 10 | 15 | 20 | 25 |
| **Major** | 4 | 8 | 12 | 16 | 20 |
| **Moderate** | 3 | 6 | 9 | 12 | 15 |
| **Minor** | 2 | 4 | 6 | 8 | 10 |
| **Insignificant** | 1 | 2 | 3 | 4 | 5 |

**Impact Levels**

- **Catastrophic:** Total business disruption, massive data breach, legal consequences, or irreversible damage.  
- **Major:** Significant disruption, substantial loss of sensitive data, serious financial/reputational damage.  
- **Moderate:** Noticeable impact on operations or customers; limited data exposure.  
- **Minor:** Minimal disruption with minor cost implications.  
- **Insignificant:** No measurable impact.

**Likelihood Levels**

- **Rare:** Exceptional circumstances; < once every 5 years.  
- **Unlikely:** Could occur, but not observed recently.  
- **Possible:** Might occur occasionally; seen in similar orgs.  
- **Likely:** Expected periodically; has occurred before.  
- **Almost Certain:** Highly likely in the short term under current conditions.

---

### 3. Risk Scoring Methodology

**Scoring Formula**

> **Risk Score = Impact × Likelihood**

**Risk Score Interpretation**

| Score Range | Risk Category | Required Actions | Review Frequency |
|------------|--------------|------------------|------------------|
| 1–6 | Low | Accept; monitor periodically | Annually |
| 7–14 | Medium | Accept with documented justification and monitoring | Semi-annually |
| 15–19 | High | Mitigation/treatment plan required; not accepted as-is | Quarterly |
| 20–25 | Critical | Not acceptable; immediate mitigation and executive escalation | Monthly |

**Additional Considerations**

- Recalculate scores when threats, architecture or business priorities change.  
- Risk aggregation across systems or business units can change prioritization even when individual scores look acceptable.

---

**Prepared By:** Juan Marcos Lázaro  
**Date:** July 23rd 2025  

**Approval**

| Name | Role | Signature | Date |
|------|------|-----------|------|
