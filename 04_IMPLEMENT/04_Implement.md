# NIST RMF – Implement Stage  
**Organization:** eCommerceCo  
*All names appearing in this document are fictitious and used solely for educational and illustrative purposes.*

---

## A. Purpose of the Implement Stage

The Implement stage documents **how the selected NIST SP 800-53 Rev.5 controls are actually realized** in the eCommerceCo environment.

This includes:

- Technical configurations  
- Process and policy enablers  
- Mappings to cloud-native services (AWS/GCP)  
- Evidence types that can be collected during assessments  

The goal is to move from **“control planned”** → **“control implemented with evidence.”**

---

## B. Implementation Approach

eCommerceCo follows these principles when implementing controls:

1. **Cloud-Native First** – Prefer AWS/GCP managed services and security features.  
2. **Infrastructure as Code (IaC)** – Use Terraform / CloudFormation to enforce secure baselines.  
3. **DevSecOps Integration** – Embed security checks in CI/CD pipelines.  
4. **Least Privilege** – Minimize permissions for services, users, and roles.  
5. **Evidence by Design** – Implementation must generate logs/metrics to prove control effectiveness.

---

## C. Example Control Implementations

A subset of key controls is documented below as examples of how the implementation is described for the full catalog.

---

### 1. AC-2 – Account Management

**Control Objective**  
Manage information system accounts, including creation, modification, disabling, and removal.

**Implementation at eCommerceCo**

- All user and service accounts are managed through **AWS IAM** and **GCP IAM**, integrated with the corporate IdP (e.g., Okta / Azure AD).
- Administrative access requires:
  - Named user accounts  
  - Multi-factor authentication (MFA)  
  - Role-based access control (RBAC)
- Account lifecycle is tied to HR events:
  - Joiners: accounts auto-provisioned based on role  
  - Movers: role changes trigger access review and update  
  - Leavers: accounts disabled within 24 hours of termination
- Shared accounts are prohibited for administrative operations; break-glass accounts are stored in a secure vault with strict logging.

**Evidence**

- IAM configuration exports  
- HR access review tickets  
- Logs of account creation/deletion events  
- Screenshots of MFA enforcement settings  

---

### 2. IA-5 – Authenticator Management

**Control Objective**  
Manage authentication mechanisms (passwords, tokens, keys) securely.

**Implementation at eCommerceCo**

- All passwords follow a hardened policy:
  - Minimum length (e.g., 14+ characters)  
  - Blocklists for common/compromised passwords  
  - No forced periodic rotation except when compromise is suspected.
- API access uses:
  - Short-lived tokens (OAuth 2.0 / JWT)  
  - Rotated keys managed by **AWS Secrets Manager** or **GCP Secret Manager**  
- SSH access to servers:
  - Key-based authentication only  
  - Keys rotated regularly  
  - Keys mapped to individual identities (no shared keys)

**Evidence**

- Password policy configuration  
- Secrets Manager screenshots/config exports  
- API gateway token configuration  
- SSH key management procedures  

---

### 3. AU-6 – Audit Review, Analysis, and Reporting

**Control Objective**  
Review and analyze information system audit records for indications of inappropriate or unusual activity.

**Implementation at eCommerceCo**

- Audit logs from:
  - AWS CloudTrail  
  - GCP Audit Logs  
  - Application services  
  - API gateway  
  - OS-level logging

  are centralized into a SIEM (e.g., Splunk / ELK / Security Hub stack).
- The SIEM:
  - Normalizes events  
  - Applies correlation rules  
  - Generates alerts for suspicious behavior (e.g., failed logins, privilege escalation, anomalous API calls).
- Security team:
  - Reviews dashboards daily  
  - Handles alerts via an incident ticketing system  
  - Performs weekly trend analysis and monthly reporting.

**Evidence**

- SIEM dashboards / screenshots  
- Correlation rule definitions  
- Incident tickets with references to logs  
- Monthly audit review report  

---

### 4. SC-13 – Cryptographic Protection

**Control Objective**  
Protect the confidentiality and integrity of information using cryptography.

**Implementation at eCommerceCo**

- Data in transit:
  - All public endpoints use **TLS 1.2+** with modern cipher suites.  
  - HSTS enforced on web applications.
- Data at rest:
  - Databases (RDS, Cloud SQL, MongoDB, etc.) use AES-256 encryption at rest.  
  - S3 / GCS buckets are encrypted with KMS-managed keys.
- Key management:
  - Keys are managed via **AWS KMS** / **GCP KMS**  
  - Access to keys is restricted to specific roles.  
  - Key rotation policies are enforced per compliance requirements.

**Evidence**

- TLS configuration / SSL report  
- Database and storage encryption settings  
- KMS key policies and rotation settings  

---

### 5. CM-6 – Configuration Settings

**Control Objective**  
Establish and implement configuration settings for IT products employed within the information system.

**Implementation at eCommerceCo**

- Baseline OS and container images are built using hardened templates (e.g., CIS Benchmarks).  
- Configuration is managed via:
  - Infrastructure as Code (Terraform, CloudFormation)  
  - Configuration management (Ansible, etc.)
- Changes to configuration:
  - Must go through code review and approval in Git  
  - Are tested in non-production before deployment  
  - Are traceable via commit history and CI/CD logs.

**Evidence**

- Baseline configuration documents  
- Sample Terraform/CloudFormation templates  
- Git commit history / pull requests  
- CI/CD pipeline logs  

---

### 6. IR-4 – Incident Handling

**Control Objective**  
Establish an operational incident-handling capability.

**Implementation at eCommerceCo**

- Incident Response (IR) plan defines:
  - Triage process  
  - Roles and responsibilities (Security, DevOps, Product, Legal)  
  - Communication channels (Slack, PagerDuty, email)  
  - Escalation criteria (Low → Critical)
- Playbooks exist for:
  - Credential compromise  
  - Suspicious login activity  
  - API abuse / DDoS-like behavior  
  - Data leak scenarios
- Post-incident reviews feed into:
  - Updated detection rules  
  - Lessons learned and process improvements  

**Evidence**

- IR plan document  
- Playbooks  
- Incident tickets and post-incident review docs  

---

## D. Mapping to Cloud Service Responsibilities

eCommerceCo uses a **shared responsibility model**:

- **Cloud Provider (AWS/GCP)**  
  - Physical and environmental security  
  - Underlying infrastructure and hypervisors  
  - Certain managed service controls

- **eCommerceCo**  
  - Identity and access management  
  - Application security  
  - Logging, monitoring, response  
  - Data classification and protection  

This mapping is maintained in a **Responsibility Matrix**, referenced in the SSP.

---

## E. Implementation Status Tracking

Controls are tracked as:

- **Implemented** – Fully deployed and operating.  
- **Partially Implemented** – In progress, but gaps exist.  
- **Planned** – Not yet deployed; included in roadmap/POA&M.  
- **Inherited** – Provided entirely by the cloud provider or another system.

A summary might look like:

| Status | Count | Notes |
|--------|-------|-------|
| Implemented | 250+ | Majority of baseline controls in production. |
| Partially Implemented | ~40 | Improvement activities tracked in POA&M. |
| Planned | ~20 | Roadmapped for next 2–3 quarters. |
| Inherited | ~30 | From AWS/GCP (physical, environmental, some network services). |

---

## F. Evidence Collection Plan

For each control, eCommerceCo defines:

- **Evidence Type:** Screenshot, config export, log sample, ticket, policy document.  
- **Owner:** Which team provides evidence (Security, DevOps, Compliance, etc.).  
- **Frequency:** One-time / quarterly / annually.  

This plan feeds directly into the **Assessment (Assess Stage)** and simplifies recurring audits.

---

## G. Approvals

| Name | Role | Signature | Date |
|------|------|-----------|------|
| Alicia Washington | Security Director |  |  |
| Sanjay Patel | DevOps Lead |  |  |
| Marcus Harris | CTO |  |  |
