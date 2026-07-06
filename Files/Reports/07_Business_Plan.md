# DOCUMENT 07: BUSINESS PLAN

**Purpose:** This document defines the commercial structure, operational costs, revenue streams, and financial projections for CHCS. It presents a viable business case for private investors, public venture funds, and national treasury officers.
**Intended Audience:** Chief Financial Officers (CFOs), Venture Capitalists, Government Budget Committees, and Startup Founders.
**Why it matters:** A digital healthcare platform must achieve financial self-sustainability to survive beyond short-term pilot grants. This business plan details how to cover cloud infrastructure and engineering costs through B2B subscriptions, transaction fees, and analytics licensing.

---

## 1. Business Model Canvas

```
+-----------------------------------------------------------------------------------------------+
| KEY PARTNERS       | KEY ACTIVITIES      | VALUE PROPOSITION   | CUSTOMER RELATIONS | SEGMENTS|
| - MoHFW & DGHS     | - Core Software Dev | - Lifelong EHR      | - Portal support   | - Public|
| - ICT Division     | - API Integrations  | - Error reduction   | - On-site training |   Clinic|
| - Telecom/MFS      | - Database Scaling  | - Outbreak Tracking | - SLA management   | - Private|
| - WHO/World Bank   | - Security Audits   | - Cost savings      |                    |   Hosp. |
|                    +---------------------+                     +--------------------+ - Pharm. |
|                    | KEY RESOURCES       |                     | CHANNELS           | - Patient|
|                    | - Cloud Infrastructure                    | - Government Edict |         |
|                    | - Dev Engineers                           | - Direct Outreach  |         |
|                    | - Support Champions                       | - Telecom SMS      |         |
+--------------------+---------------------+---------------------+--------------------+---------+
| COST STRUCTURE                           | REVENUE STREAMS                                    |
| - Hosting & Cloud Database (AWS/Local)   | - B2B SaaS Subscriptions (Private Clinics)         |
| - Engineering & Support Staff Salaries   | - Transaction API Fees (Pharmacies / Labs)         |
| - Hardware Deployment & Training Costs   | - Anonymized Research Data Analytics Licenses      |
+------------------------------------------+----------------------------------------------------+
```

---

## 2. Revenue Model

CHCS generates revenue through four key streams, balancing public good with commercial viability:

### 1. B2B Private Hospital Subscriptions (SaaS)
Private clinics and hospital groups pay a tiered monthly subscription based on patient volume to access advanced EHR features, scheduling integrations, and analytics dashboards.

### 2. Diagnostic & Pharmacy API Fees
High-volume diagnostic centers and retail pharmacies pay a nominal fee (e.g., 2 BDT per transaction) to check patients' credentials or validate prescriptions.

### 3. De-Identified Data Analytics Licenses
Pharmaceutical companies, medical researchers, and epidemiological study teams license access to aggregate, de-identified healthcare databases (e.g., disease trends, therapy outcomes) in strict compliance with data privacy regulations.

### 4. Premium Patient Services
Citizens can purchase premium features, such as automated SMS prescription alerts, family account dashboards, and verified digital health cards for international travel.

---

## 3. 3-Year Financial Projections (BDT)

| Metric / Category | Year 1 | Year 2 | Year 3 |
|---|---|---|---|
| **Onboarded Hospitals (Public/Private)** | 60 | 450 | 1,800 |
| **Active Citizen UHID Profiles** | 1.5 Million | 12 Million | 65 Million |
| **Total Revenue** | **18,500,000** | **124,000,000** | **480,000,000** |
| *B2B SaaS Subscriptions* | 6,500,000 | 42,000,000 | 145,000,000 |
| *API Transaction Fees* | 4,000,000 | 38,000,000 | 185,000,000 |
| *Analytics Licensing* | 8,000,000 | 44,000,000 | 150,000,000 |
| **Total Operating Expenses (OpEx)** | **24,000,000** | **78,000,000** | **185,000,000** |
| *Cloud Hosting & Bandwidth* | 4,500,000 | 18,000,000 | 48,000,000 |
| *Engineering & Support Salaries* | 12,000,000 | 32,000,000 | 72,000,000 |
| *Training & Field Ops* | 5,500,000 | 20,000,000 | 45,000,000 |
| *Marketing & Legal Compliance* | 2,000,000 | 8,000,000 | 20,000,000 |
| **Net Profit / (Loss)** | **(5,500,000)** | **46,000,000** | **295,000,000** |

---

## 4. Cloud Infrastructure Cost Modeling

A significant component of our OpEx is cloud infrastructure, modeled below for scaling phases:

```
[Phase 1: Pilot (500k queries)] ---> Approx. Cost: 375,000 BDT/month
- 2x EC2 Web Application Servers (AWS t3.xlarge)
- 1x RDS PostgreSQL Instance with read-replica
- Redis cache & basic S3 backup storage

[Phase 2: Scale-Up (15M queries)] ---> Approx. Cost: 1,500,000 BDT/month
- Managed Kubernetes Cluster (EKS / GKE)
- Distributed RDS PostgreSQL cluster (multi-AZ)
- High-availability Redis nodes
- 10TB S3 secure storage + CloudFront CDN

[Phase 3: National (150M+ queries)] ---> Approx. Cost: 4,000,000 BDT/month
- Geo-distributed multi-region Kubernetes nodes
- Enterprise database cluster (PostgreSQL with read-replicas per division)
- High-throughput Kafka message queues
- Data warehousing cluster (BigQuery / Redshift) for analytics processing
```

---

## 5. Break-Even & ROI Analysis

*   **Initial Capital Expenditure (CapEx):** Estimated at 35,000,000 BDT (for initial product engineering, security audits, pilot hardware, and training).
*   **Break-Even Point:** Reached in Month 14 of operations, driven by private clinic SaaS onboarding and transaction fees.
*   **Projected ROI (Year 3):** 840% on initial investor CapEx, calculated using the Year 3 net profit projections.
*   **Public Value Dividend:** An estimated 4.2 Billion BDT saved annually in public health funds by eliminating duplicate diagnostic tests and improving early outbreak management.
