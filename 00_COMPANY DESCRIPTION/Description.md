# eCommerceCo – Company & Platform Description  
*All names and scenarios are fictitious and used solely for educational and illustrative purposes.*

---

## 1. Company Overview

eCommerceCo is a fast-growing, cloud-native e-commerce platform designed for **small and mid-sized retailers** who require modern, scalable digital commerce capabilities without deep technical expertise.

Founded in 2017 and headquartered in **Seattle**, with a secondary office in **Austin**, the company has expanded rapidly—from 30 to more than 120 employees—driven by strong demand, merchant success, and a subscription-based SaaS business model.

The organization emphasizes:

- Agile development  
- Innovation  
- Secure cloud adoption  
- Strong merchant support  
- Data-driven decision-making  

Leadership includes professionals with experience at Amazon, Shopify, Square, and other technology-driven retail organizations. Recent Series B funding (USD $18M) is accelerating product expansion and security maturity. :contentReference[oaicite:1]{index=1}

---

## 2. Core Platform Offerings

The eCommerceCo platform provides an integrated suite of retail-focused capabilities:

### **StoreFront**
Customizable online stores with secure inventory and order management.

### **PaymentHub**
Payment orchestration supporting Stripe, Adyen, and multiple tender types with PCI DSS L1 alignment.

### **LogisticsLink**
End-to-end shipping workflows integrating with major carriers.

### **RetailInsights**
Merchant analytics covering sales trends, customer behavior, and inventory optimization.

### **MarketConnect**
Marketplace integrations with Amazon, eBay, and other channels.

The platform processes over **$275M in annual GMV** and supports more than 500 active retailers across diverse verticals. :contentReference[oaicite:2]{index=2}

---

## 3. Technology Architecture Summary

The architecture is **multi-cloud**, distributed across **AWS** and **Google Cloud Platform**, following a **microservices** model with containers orchestrated on EKS and Cloud Run.

Below is a structured description aligned with the architecture diagram:

---

### **3.1 AWS Cloud Environment**

#### 🔹 API Gateway Security Layer
- AWS API Gateway  
- WAF (Web Application Firewall)  
- Custom authentication service (JWT, OAuth2)  
- Rate limiting, DDoS protection  

#### 🔹 Microservices Layer (EKS)
Services include:
- StoreFront (Node.js / React)  
- PaymentHub (Stripe/Adyen)  
- LogisticsLink (Shipping APIs)  
- RetailInsights (Analytics)  
- MarketConnect (3rd-party API integrations)  
- Inventory & Product Management  

Security features:
- Kubernetes RBAC  
- Kubernetes Security Controls  
- Container security scanning & policy enforcement  

#### 🔹 Data Layer
- PostgreSQL (Amazon RDS) – primary DB  
- MongoDB Atlas – product catalog  
- Redis – caching and session storage  
- S3 – static content & images  

---

### **3.2 Google Cloud Platform**

#### 🔹 Content Delivery
- Google Cloud CDN  
- Static asset distribution  

#### 🔹 Analytics Services
- BigQuery – centralized analytics warehouse  
- ETL pipelines for cross-cloud data movement  

---

### **3.3 Identity & Access**

- Okta for employee IAM  
- Custom identity service for merchants and customers  
- MFA enforced for critical functions  
- OAuth2 for mobile & API authentication  
- RBAC for merchant admins (currently being strengthened) :contentReference[oaicite:3]{index=3}

---

### **3.4 Monitoring & Security**

Security stack includes:

- AWS Security Hub  
- GuardDuty  
- Datadog (APM + metrics)  
- New Relic (telemetry)  
- ELK Stack (logging)  
- Snyk (SCA & container scanning)  
- OWASP ZAP (DAST)  

Identified issues include:
- Inadequate RBAC in some workloads  
- Gaps in container security monitoring  
- Limited cloud configuration visibility  
- Incomplete audit logging for certain admin actions :contentReference[oaicite:4]{index=4}

---

### **3.5 Corporate Offices**

**Seattle HQ**  
- Development Team (CI/CD pipeline)  
- Security Team (SOC operations)  

**Austin Office**  
- Customer Success  
- Merchant Support  
- Sales / Onboarding  

---

### **3.6 External Systems**
- Payment processors  
- Shipping carriers  
- Marketplaces (Amazon, eBay, etc.)  
These dependencies introduce **third-party risk** and strict compliance obligations.

---

### **3.7 Users**
- Merchant Admins (store management)  
- End Customers (shopping experience)  
- Mobile app users (React Native)  
- Web users (React/Next.js)  

---

## 4. Compliance Requirements

eCommerceCo must comply with a wide range of international regulations:  
- **PCI DSS Level 1**  
- **GDPR** (EU)  
- **CCPA** (California)  
- **SOC 2 Type II**  
- **ADA** (Accessibility)  
- **PIPEDA** (Canada)  
- **LGPD** (Brazil)  
- **Australian APP**  
- **ISO 27001** (in progress)  

These obligations increase operational complexity and require robust monitoring, documentation, and control implementation. :contentReference[oaicite:5]{index=5}

---

## 5. Sensitive Data Types

The platform processes:

- Customer PII  
- Tokenized payment card information  
- Merchant financial/settlement data  
- User credentials  
- Shopping behavior & preferences  
- Inventory & pricing data  
- API keys and integration secrets  
- Internal employee data  
- Machine learning datasets :contentReference[oaicite:6]{index=6}

---

## 6. Key Challenges

Based on recent assessments and internal analysis:

- Rapid growth → increasing attack surface  
- Technical debt in legacy components  
- Multi-cloud complexity  
- Inconsistent API security controls  
- Limited 24/7 security operations coverage  
- Inadequate RBAC for merchant admins  
- Container security monitoring gaps  
- Secrets management weaknesses  
- Global expansion → evolving regulatory requirements  
- Trade-off between usability and strict security  
- Increasing cloud infrastructure cost pressures :contentReference[oaicite:7]{index=7}

---

## 7. Current Priorities & Security Focus Areas

- API security standardization  
- Cloud Security Posture Management (CSPM)  
- Fully integrated DevSecOps  
- Strengthened identity and access controls  
- Payment security modernization  
- Evidence automation for audits  
- Merchant security baseline enforcement  
- Enhanced incident detection & response  
- Third-party risk program development  
- Encryption & data protection expansion :contentReference[oaicite:8]{index=8}

---

## 8. Summary

eCommerceCo is a rapidly scaling, multi-cloud e-commerce platform facing:

- High regulatory burden  
- Increasing infrastructure complexity  
- Merchant-driven usability pressures  
- Growing threat exposure  

Despite these challenges, the company is committed to maturing its cybersecurity program through:

- Strong executive support  
- Cloud-native security technologies  
- RMF-aligned governance  
- Comprehensive monitoring  
- Continuous improvement practices

This repository reflects that maturity journey through a **complete RMF documentation package** demonstrating control selection, implementation, assessment, authorization, and continuous monitoring.


## 9. Network Architecture

<img width="425" height="319" alt="image" src="https://github.com/user-attachments/assets/58bbaef1-2b72-44dc-9571-67f7ca195fe4" />

