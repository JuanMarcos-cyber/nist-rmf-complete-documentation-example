# System Security Plan (SSP)  
**System:** eCommerceCo Cloud-Based E-Commerce Platform  
**Author:** Juan Marcos Lázaro  
*All names appearing in this document are fictitious and used solely for educational and illustrative purposes.*

---

## A. System Overview

eCommerceCo operates a cloud-native e-commerce processing platform that enables:

- Customer identity and profile management  
- Merchant analytics  
- Payment orchestration  
- Order and logistics workflows  
- High-volume API integrations  

The system is distributed across **AWS** and **GCP**, leveraging containerized microservices, serverless compute, and managed databases.

---

## B. System Boundary

### The system boundary includes:

- Front-end applications
- Back-end microservices (API, auth, payments, products)
- Datastores (PostgreSQL, MongoDB, Redis)
- AWS EKS / GCP Cloud Run services
- Authentication services (IdP + IAM)
- Logging and SIEM pipelines
- CI/CD services

### The system boundary excludes:

- Physical infrastructure  
- Merchant-owned IT systems  
- Third-party payment networks  
- End-user devices  

---

## C. System Architecture Summary

The architecture comprises:

- **API Gateway** (routing, throttling, OAuth2)
- **Identity Layer** (IdP → IAM)
- **Microservices** (Docker containers running on EKS / Cloud Run)
- **Data Tier** (RDS, Cloud SQL, MongoDB Atlas)
- **Messaging** (SQS, Pub/Sub)
- **Caching** (Redis/Memcached)
- **Static Content** (S3, Cloud Storage, CloudFront CDN)
- **CI/CD** (GitHub Actions/Jenkins)
- **Monitoring & SIEM** (CloudTrail, GuardDuty, ELK/Splunk)

---

## D. Control Implementation Responsibility (Shared Model)

| Layer | AWS/GCP Responsibility | eCommerceCo Responsibility |
|-------|-------------------------|-----------------------------|
| Physical Security | ✔ Full | — |
| Hypervisor / Hardware | ✔ Full | — |
| Managed Services Infra | ✔ Partial | ✔ Partial (config) |
| Identity & Access | — | ✔ Full |
| Logging / Monitoring | — | ✔ Full |
| Application Security | — | ✔ Full |
| Data Protection | — | ✔ Full |
| Network Config | Partial | Partial |

---

## E. Applicable Controls (NIST SP 800-53 Rev.5 HIGH)

Controls apply from all 20 NIST families, including:

- **AC** Access Control  
- **AU** Audit & Accountability  
- **CM** Configuration Management  
- **CP** Contingency Planning  
- **IA** Identification & Authentication  
- **IR** Incident Response  
- **RA** Risk Assessment  
- **SC** System & Communications Protection  
- **SI** System Integrity  

Full control-by-control implementations are in **IMPLEMENT.md**.

---

## F. Roles & Responsibilities

| Role | Responsibility |
|------|---------------|
| CEO | Approves strategic security direction |
| CTO | Oversees secure architecture |
| Security Director | Manages RMF and cybersecurity program |
| DevOps Lead | Enforces security in CI/CD & cloud infrastructure |
| Compliance Manager | Ensures PCI/GDPR/SOC2 alignment |
| Engineering Managers | Apply secure development practices |

---

## G. Laws, Regulations & Policies

- **PCI DSS**  
- **GDPR**  
- **CCPA**  
- **SOC 2**  
- **NIST SP 800-53 Rev.5**  
- **eCommerceCo Security Policies**  
- **IAM Policy Standard**  
- **Encryption Policy**

---

## H. Control Status Summary

| Status | Count | Description |
|--------|-------|-------------|
| Implemented | Majority | Controls fully functional |
| Partially Implemented | Few | Identified in POA&M |
| Inherited | Several | From AWS/GCP |

---

## I. Attachments / Related Artifacts

- `ASSESSMENT.md`  
- `SAR.md`  
- `POAM.md`
- Arquitechture Diagram

- <img width="425" height="319" alt="image" src="https://github.com/user-attachments/assets/c1f26490-730a-49f1-8caf-4a920a66f79a" />
