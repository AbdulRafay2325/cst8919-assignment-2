# Cloud Security Services: Azure vs AWS vs GCP

This repository documents a comparison of key Microsoft Azure security, compliance, and DevSecOps services with their closest equivalents in Amazon Web Services (AWS) and Google Cloud Platform (GCP).  

The goal is to understand similarities, differences, and trade-offs across providers in terms of features, compliance, pricing, and DevSecOps integration.

---

## Service Comparison Table

| Azure Service | AWS Equivalent | GCP Equivalent | Category |
|---------------|---------------|----------------|----------|
| **Microsoft Entra ID (Azure AD)** | AWS IAM, AWS IAM Identity Center (SSO), Amazon Cognito | Google Cloud Identity, IAM, Identity-Aware Proxy | Identity & Access Management |
| **Azure Monitor & Log Analytics** | Amazon CloudWatch, AWS CloudTrail, Amazon OpenSearch | Cloud Monitoring, Cloud Logging, BigQuery | Monitoring & Logging |
| **Azure Policy** | AWS Config, AWS Organizations SCPs | Google Cloud Organization Policy Service | Governance & Compliance |
| **Microsoft Defender for Cloud** | AWS Security Hub + GuardDuty + Inspector | Google Security Command Center (SCC) | Cloud Security Posture & Workload Protection |
| **Microsoft Sentinel (SIEM/SOAR)** | Amazon Security Lake + Partner SIEMs (Splunk, QRadar, Elastic) | Chronicle SIEM (Google Cloud) | Threat Detection & Response |

---

## 1. Microsoft Entra ID (Azure Active Directory)

**AWS Equivalent:** IAM, IAM Identity Center (formerly AWS SSO), Cognito  
**GCP Equivalent:** Cloud Identity, IAM, Identity-Aware Proxy  

### Overview
Microsoft Entra ID provides centralized **identity and access management (IAM)** with SSO, MFA, RBAC, and conditional access. AWS and GCP offer similar capabilities but split them across multiple services.

### Core Features
- **Azure:** SSO, MFA, Conditional Access, RBAC, Hybrid Identity, Identity Protection  
- **AWS:** Fine-grained IAM policies, temporary credentials, SSO via Identity Center, user federation with Cognito  
- **GCP:** Role-based IAM, Cloud Identity for workforce, Identity-Aware Proxy for Zero Trust  

### Security & Compliance
- Compliant with **ISO 27001, SOC 1/2/3, GDPR, HIPAA** across all providers  
- Azure integrates tightly with Microsoft 365 security stack  
- AWS and GCP offer strong federation and Zero Trust models  

### Pricing
- **Azure:** Free tier + Premium P1/P2 plans (per user/month)  
- **AWS:** IAM free, Identity Center included, Cognito billed per MAU  
- **GCP:** IAM free, Cloud Identity (per-user premium tiers)  

### DevSecOps Integration
- **Azure:** integrates with GitHub Actions, Azure DevOps  
- **AWS:** IAM roles used in CI/CD pipelines  
- **GCP:** workload identity federation for Cloud Build, CI/CD pipelines  

---

## 2. Azure Monitor & Log Analytics

**AWS Equivalent:** CloudWatch, CloudTrail, OpenSearch  
**GCP Equivalent:** Cloud Monitoring, Cloud Logging, BigQuery  

### Overview
Azure Monitor centralizes telemetry from infrastructure and applications, with Log Analytics (KQL) for powerful queries. AWS provides CloudWatch (metrics/logs), CloudTrail (audit logs), and OpenSearch for analysis. GCP offers Cloud Logging & Monitoring with BigQuery for deep analytics.

### Core Features
- **Azure:** Metrics, logs, alerts, dashboards, KQL queries, integration with Sentinel  
- **AWS:** Metrics, dashboards, alarms, audit trails, anomaly detection  
- **GCP:** Real-time logging, monitoring dashboards, BigQuery for historical log analysis  

### Security & Compliance
- All providers support **audit logging, encryption, regulatory compliance**  
- Logs are critical for SOC 2, PCI DSS, HIPAA audits  

### Pricing
- **Azure:** Pay per GB ingested and stored  
- **AWS:** Charged per metric, dashboard, and log ingestion  
- **GCP:** Free tier + pay per GB ingestion and retention  

### DevSecOps Integration
- **Azure:** integrates with Logic Apps, Sentinel, Defender  
- **AWS:** integrates with EventBridge, Lambda  
- **GCP:** integrates with Cloud Functions, Pub/Sub  

---

## 3. Azure Policy

**AWS Equivalent:** AWS Config, AWS Organizations SCPs  
**GCP Equivalent:** Organization Policy Service  

### Overview
Azure Policy enforces compliance at scale by denying or auditing non-compliant resource configurations. AWS uses Config (compliance) and SCPs (service control). GCP offers Organization Policy constraints.

### Core Features
- **Azure:** Enforce/deny policies, audit, remediate, tagging strategies  
- **AWS:** Config rules, compliance checks, drift detection, SCPs  
- **GCP:** Constraint-based policies across resource hierarchy  

### Security & Compliance
- Supports **PCI DSS, HIPAA, FedRAMP, GDPR** alignment  
- Continuous evaluation in all platforms  

### Pricing
- **Azure:** Free for policy definitions (some remediation costs)  
- **AWS:** Config billed per resource per rule evaluation  
- **GCP:** Organization Policy free  

### DevSecOps Integration
- **Azure:** integrates with pipelines to enforce policies before deployment  
- **AWS:** Config rules tied into CodePipeline and Security Hub  
- **GCP:** validates deployments in Cloud Build, Terraform  

---

## 4. Microsoft Defender for Cloud

**AWS Equivalent:** Security Hub, GuardDuty, Inspector  
**GCP Equivalent:** Security Command Center (SCC)  

### Overview
Defender for Cloud is a **Cloud-Native Application Protection Platform (CNAPP)** providing DevSecOps security, CSPM (posture management), and CWPP (workload protection). AWS distributes this across GuardDuty (threat detection), Inspector (vulnerability scans), and Security Hub (compliance). GCP centralizes with SCC.

### Core Features
- **Azure:** DevSecOps IaC scanning, CSPM, CWPP, vulnerability mgmt.  
- **AWS:** GuardDuty (threats), Inspector (vulnerabilities), Security Hub (compliance)  
- **GCP:** SCC (risk analysis, vulnerabilities, compliance)  

### Security & Compliance
- All integrate with **SOC 2, HIPAA, GDPR, PCI DSS** frameworks  
- Azure integrates with Microsoft threat intelligence for enriched detection  

### Pricing
- **Azure:** Charged per protected resource type (VM, DB, container)  
- **AWS:** GuardDuty per GB analyzed, Inspector per instance, Security Hub per check  
- **GCP:** SCC Standard (free), Premium tier billed per resource  

### DevSecOps Integration
- **Azure:** IaC scanning in pipelines (Terraform, GitHub Actions)  
- **AWS:** Inspector integrated with AMI builds and CI/CD pipelines  
- **GCP:** SCC hooks with Cloud Build, API-driven alerts  

---

## 5. Microsoft Sentinel (SIEM/SOAR)

**AWS Equivalent:** Security Lake + Partner SIEMs  
**GCP Equivalent:** Chronicle SIEM  

### Overview
Sentinel is Microsoft’s **native SIEM/SOAR** for real-time analytics, incident response, and automation. AWS centralizes logs in Security Lake but depends on third-party SIEMs. GCP offers Chronicle SIEM for large-scale threat detection.

### Core Features
- **Azure:** SIEM + SOAR, KQL queries, automation playbooks, AI-driven analytics  
- **AWS:** Security Lake for log aggregation, integrates with Splunk/Elastic/QRadar  
- **GCP:** Chronicle SIEM, strong integration with Google threat intel  

### Security & Compliance
- Designed for compliance frameworks requiring **log retention & threat monitoring**  
- Supports regulated industries (finance, healthcare, government)  

### Pricing
- **Azure:** Pay-per-GB ingestion + retention  
- **AWS:** Security Lake (per GB stored) + external SIEM pricing  
- **GCP:** Chronicle (subscription or data-based pricing)  

### DevSecOps Integration
- **Azure:** integrates with Logic Apps & Defender playbooks  
- **AWS:** integrates with Lambda, EventBridge, third-party SOAR tools  
- **GCP:** integrates with SCC, Pub/Sub, Cloud Functions  

---

## Analysis

- **Azure provides integrated, end-to-end security services** (Entra ID, Monitor, Policy, Defender, Sentinel).  
- **AWS spreads capabilities across multiple services** (IAM, Config, GuardDuty, Security Hub, Inspector, CloudWatch), relying on partner SIEMs.  
- **GCP consolidates around fewer core tools** (Cloud Identity, Cloud Logging, SCC, Chronicle).  

**Key Takeaway:**  
- **Azure** = strong integration, enterprise-ready, Microsoft ecosystem  
- **AWS** = flexible but fragmented, requires multiple services + partners  
- **GCP** = simpler, consolidated, strong analytics  

---

