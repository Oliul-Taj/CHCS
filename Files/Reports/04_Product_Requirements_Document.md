# DOCUMENT 04: PRODUCT REQUIREMENTS DOCUMENT (PRD)

**Purpose:** This document details the functional specifications, user personas, user stories, non-functional requirements, and success metrics for the Minimum Viable Product (MVP) and subsequent releases of the Centralized Health Care System (CHCS). It aligns the engineering, product, and clinical teams on *what* needs to be built and *how* performance will be measured.
**Intended Audience:** Product Managers, UI/UX Designers, Developers, QA Engineers, and Clinical Advisors.
**Why it matters:** A clear PRD prevents feature creep, establishes explicit definition-of-done criteria, and ensures the development lifecycle addresses the exact needs of rural health workers, urban doctors, and government administrators.

---

## 1. Product Vision & Value Proposition

### Vision
To create a seamless, secure, and unified national digital health ecosystem for Bangladesh that reduces clinical errors, eliminates redundant diagnostic testing, and provides every citizen with a lifelong portable health identity.

### Value Proposition
*   **For Citizens:** Portability of records, reduced out-of-pocket medical expenses, and control over medical data access.
*   **For Clinicians:** Patient longitudinal charts available at point of care, reduced paperwork, and dynamic electronic prescriptions.
*   **For Public Health Agencies:** Live geographic dashboards tracking symptom densities and epidemiological outbreaks.

---

## 2. Target User Personas

CHCS serves five key user groups across Bangladesh:

```
+--------------------------------------------------------------------------+
|                            USER PERSONAS                                 |
+--------------------------------------------------------------------------+
|  [Citizen/Patient]  [Clinician/Doctor] [Hospital Admin]  [Pharmacist]   |
|   Low-tech/MFS user   Time-constrained   Bulk Registrations  Retail POS  |
+--------------------------------------------------------------------------+
```

### 1. Rahima Begum (Citizen / Patient)
*   **Bio:** 48-year-old home-maker living in a rural union of Mymensingh.
*   **Tech Literacy:** Low. Uses a basic smartphone primarily for social media and mobile financial services (bKash).
*   **Key Pain Point:** Frequently loses paper prescriptions and medical test reports during travel between her village and the divisional hospital.

### 2. Dr. Asif Rahman (Clinician / Practitioner)
*   **Bio:** 34-year-old medical officer at Dhaka Medical College Hospital.
*   **Tech Literacy:** High. Extremely time-constrained, sees over 80 patients per outpatient shift.
*   **Key Pain Point:** Operates blind when treating patients referred from rural clinics; lacks time to read through unstructured paper files.

### 3. Kabir Hossain (Hospital Administrator)
*   **Bio:** 45-year-old administrative supervisor at a private clinic in Sylhet.
*   **Tech Literacy:** Medium. Manages hospital registration desk, billing, and reporting.
*   **Key Pain Point:** Tedious registration processes leading to long queues and typos in patients' personal records.

### 4. Selim Reza (Pharmacist / Dispenser)
*   **Bio:** 29-year-old drug store manager in Rajshahi.
*   **Tech Literacy:** Medium. Uses desktop point-of-sale systems.
*   **Key Pain Point:** Deciphering illegible handwritten prescriptions, leading to dispensing errors and inventory loss.

---

## 3. User Stories & Acceptance Criteria

### User Story 1: Identity Verification (Patient Onboarding)
*   **As a** Hospital Registrar,
*   **I want to** verify a patient's identity using their NID, Passport, or Birth Registration number (without needing complex prefixes),
*   **So that** I can register them instantly and link their record to the central database.

#### Acceptance Criteria:
*   The system must resolve identity automatically from a bare numeric string (e.g., `1988102938475`).
*   The system must handle lowercase/uppercase input and ignore redundant whitespaces.
*   If the record is found in the NID database, it must automatically populate the patient's name, age, and gender fields.

---

### User Story 2: Prescribing Medication (Clinician Workflow)
*   **As a** Doctor,
*   **I want to** issue an electronic prescription detailing medication name, dosage, and duration,
*   **So that** the patient can retrieve it at any registered pharmacy without a paper copy.

#### Acceptance Criteria:
*   Prescriptions must be linked to the patient's Unique Health ID (UHID).
*   The clinical interface must separate active prescriptions from diagnostic notes.
*   The prescription must be signed digitally by the prescribing doctor's license ID.

---

### User Story 3: Prescription Dispensing (Pharmacist RBAC)
*   **As a** Pharmacist,
*   **I want to** retrieve active prescriptions using the patient's ID,
*   **So that** I can dispense the correct medicine and log the transaction.

#### Acceptance Criteria:
*   The pharmacy view must only display: patient name, medicine name, dosage, and quantity.
*   The pharmacist must NOT have access to patient diagnoses, clinical logs, or family histories (data siloing).
*   The system must record the quantity of dispensed drugs and update the record status to "Dispensed".

---

## 4. Functional Requirements

### 1. Identity Resolution Engine
*   The engine must parse strings via regular expression matching or schema verification to determine identity type automatically (NID, Passport, Birth Registration, NHID).
*   The resolver must cleanse formatting anomalies (e.g., "nid 1988-10-29..." becomes "1988102938475").

### 2. Clinical Encounter Logging
*   Doctors must be able to log symptoms, vitals, primary diagnosis, and prescription details.
*   All encounter logs must be immutable. Edits must be appended as signed additions to the ledger.

### 3. Epidemiological Outbreak GIS Map
*   The system must aggregate diagnoses in real-time.
*   The system must overlay symptom densities onto a Bangladesh GeoJSON district map.
*   Public health officials must be able to filter the density map by disease type, date range, and location.

### 4. Hospital Grading Matrix
*   The system must compute hospital ratings automatically based on patient satisfaction, service availability, and operational metrics.
*   Grading tiers: A+ (Outstanding), A (Excellent), B (Good), N (Standard), Z (Critical).

---

## 5. Non-Functional Requirements (NFR)

*   **Security & Compliance:** All patient data must be encrypted at rest (AES-256) and in transit (TLS 1.3). Access must be logged with read/write audit trails.
*   **Performance:** API Gateway response time must be under 300ms for read requests under normal loads.
*   **Offline Operation:** The system must support local caching and synchronization (RPO < 5 minutes) when internet connectivity is restored.
*   **Scalability:** The database and indexing schemas must support up to 50 million registered profiles and 5,000 concurrent writes/second.

---

## 6. MVP vs. Future Product Backlog

```
   MVP (Phase 1)                  Release 1.5                    Release 2.0
+-----------------+            +-----------------+            +-----------------+
| - NID/BC Signup | ---------->| - Offline Sync  | ---------->| - AI Diagnose   |
| - EHR Records   |            | - SMS Alerts    |            | - Billing/MFS   |
| - Pharmacist POS|            | - Geo Outbreak  |            | - Portal Apps   |
+-----------------+            +-----------------+            +-----------------+
```

### Minimum Viable Product (MVP)
*   NID/BC-based registration.
*   Basic clinical encounter entry.
*   Pharmacy prescription view.
*   Local database instance (`nchds.db`).

### Release 1.5 (Scale-Up)
*   Distributed PostgreSQL deployment.
*   Offline cache container implementation.
*   Real-time Leaflet GIS Outbreak map.
*   Hospital grading dashboard.

### Release 2.0 (Advanced Services)
*   AI Personal Nurse integration for patient alerts.
*   Integrations with private health insurance companies.
*   Mobile Financial Services (MFS) billing integration.
