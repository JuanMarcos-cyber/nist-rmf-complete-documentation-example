# NIST RMF – Categorize Stage  
**Organization:** eCommerceCo  
*All names appearing in this document are fictitious and used solely for educational and illustrative purposes.*

---

## A. System Characterization

### 1. System Name
**eCommerceCo Cloud-Based E-Commerce Platform**

### 2. System Description
The eCommerceCo platform is a cloud-native, multi-tenant e-commerce processing ecosystem that delivers:

- Secure payment orchestration  
- Customer account lifecycle management  
- Merchant-facing dashboards and analytics  
- Order, product, and logistics workflows  
- Third-party API integrations  

The system is deployed across AWS and GCP using microservices, managed databases, serverless functions, and containerized workloads.

---

## B. Information Types Processed

### 1. Information Type Identification

| Information Type | Description | Category | Examples |
|------------------|-------------|----------|----------|
| Customer PII | Personally identifiable information of users | Privacy | Name, email, phone, address |
| Payment Data | Tokenized or encrypted card data | Financial | Payment tokens, masked PAN |
| User Credentials | Authentication materials | Security | Hashes, MFA tokens, API keys |
| Merchant Data | Operational and business information | Business | Store settings, inventory |
| System Logs | Audit and telemetry information | Security | Access logs, events |
| API Communications | Third-party data exchange | Integration | Webhooks, order updates |

---

## C. Security Categorization (FIPS 199)

Under FIPS 199, each information type is evaluated across **Confidentiality**, **Integrity**, and **Availability**.

### 1. Impact Ratings per Information Type

| Information Type | Confidentiality | Integrity | Availability |
|------------------|------------------|-----------|--------------|
| Customer PII | Moderate | Moderate | Low |
| Payment Data | Moderate | High | Moderate |
| Merchant Data | Moderate | Moderate | Low |
| Credentials | High | High | Moderate |
| System Logs | Low | Moderate | Low |
| API Communications | Moderate | Moderate | Moderate |

---

## D. Overall System Security Category

Impact ratings (CIA):

- **Confidentiality:** Moderate  
- **Integrity:** High  
- **Availability:** Moderate  

📌 **Overall FIPS 199 Categorization:**  
# **HIGH**

This follows the "highest impact" rule.

---

## E. Rationale and Justification

### Confidentiality – **MODERATE**
Compromise of customer or merchant data leads to moderate regulatory and reputational impact.

### Integrity – **HIGH**
Unauthorized modification of:

- payment flows  
- credentials  
- API interactions  

…could cause fraud, service disruption, or PCI non-compliance.

Integrity is therefore the highest-impact factor.

### Availability – **MODERATE**
While outages affect merchants, redundancy and multi-region deployment limit long-term impact.

---

## F. System Environment & Boundaries

### 1. Cloud Environment
- AWS (EKS, Lambda, RDS, S3, CloudFront)  
- GCP (Cloud Run, BigQuery)  
- Vendor integrations (Stripe, Adyen, shipping services)

### 2. System Boundary Includes
- Frontend web clients  
- Backend microservices  
- Authentication and identity layer  
- Payment orchestration  
- Merchant dashboards  
- Logging, monitoring, SIEM pipeline  

### 3. System Boundary Excludes
- End-user devices  
- Third-party payment networks  
- Merchant-owned hardware and infrastructure  

---

## G. Regulatory Drivers

| Framework / Regulation | Applicability |
|------------------------|---------------|
| PCI DSS | Payment data handling |
| GDPR | EU personal data |
| CCPA | California consumer privacy |
| SOC 2 | SaaS trust principles (Security, Availability) |

---

## H. Approvals

| Name | Role | Signature | Date |
|------|------|-----------|------|
| Alicia Washington | Security Director |  |  |
| Marcus Harris | CTO |  |  |
| Board of Directors | Governance Oversight |  |  |
