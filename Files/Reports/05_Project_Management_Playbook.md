# DOCUMENT 05: PROJECT MANAGEMENT PLAYBOOK

**Purpose:** This playbook establishes the project management methodology, governance models, communications strategy, risk mitigation framework, and resource scheduling for the development, pilot, and nationwide execution of the Centralized Health Care System (CHCS) in Bangladesh.
**Intended Audience:** Project Directors, Scrum Masters, Product Owners, Government Program Managers, and Delivery Partners.
**Why it matters:** Evolving from a prototype to a national digital health network involves multiple parallel workstreams (software, infrastructure, training, procurement, policy, and compliance). Without a unified project management playbook, coordination failures can delay timelines and increase implementation risks.

---

## 1. Project Governance Model

```
                        +---------------------------------------+
                        |          Steering Committee           |
                        |      (MoHFW, DGHS, ICT Division)      |
                        +---------------------------------------+
                                            |
                                            v
                        +---------------------------------------+
                        |            Project Director           |
                        |          (Lead Program Mgr)           |
                        +---------------------------------------+
                                            |
                    +-----------------------+-----------------------+
                    |                                               |
                    v                                               v
        +-----------------------+                       +-----------------------+
        |   Software Delivery   |                       |    On-Site Operations |
        |  (Dev, QA, Security)  |                       |  (Training, Support)  |
        +-----------------------+                       +-----------------------+
```

### Roles and Responsibilities
*   **Steering Committee:** Meets monthly. Approves policy alignments, budgets, and strategic expansions.
*   **Project Director (PMO):** Oversees daily operations, manages timeline dependencies, and coordinates between developers and government departments.
*   **Software Delivery Team (Scrum Teams):** Focuses on microservice engineering, mobile application deployment, integration testing, and automated security scans.
*   **On-Site Operations Team:** Directs user training, deploys local hardware, and provides on-site user support in hospitals.

---

## 2. Decision Responsibility Matrix (RACI)

To ensure clear ownership, tasks are mapped using the RACI (Responsible, Accountable, Consulted, Informed) matrix:

| Project Phase / Deliverable | Steering Committee | Project Director | Tech Lead | QA & Ops Teams | MoHFW / DGHS |
|---|---|---|---|---|---|
| **System Architecture Sign-off** | I | A | R | C | C |
| **API Standards Validation** | I | A | R | C | C |
| **Pilot Infrastructure Setup** | I | A | C | R | I |
| **User Training & Rollout** | I | A | I | R | C |
| **Database Security Audits** | C | A | R | R | I |
| **National Policy Edicts** | A | R | I | I | R |

---

## 3. Communication Matrix

| Meeting / Artifact | Frequency | Target Audience | Primary Focus |
|---|---|---|---|
| **Daily Standup** | Daily (15 mins) | Developers, Scrum Master | Blockers, current sprint goals, immediate tasks. |
| **Sprint Review / Demo** | Bi-weekly (1 hour) | Product Owners, PMO | Reviewing working code features, checking deliverables. |
| **Project Status Report** | Bi-weekly | Steering Committee, MoHFW | High-level milestones, budget tracking, major project risks. |
| **Sprint Retrospective** | Bi-weekly (45 mins) | Delivery Team | Reviewing processes, identifying efficiency improvements. |
| **Operational Sync** | Weekly | Ops Lead, Hospital Admins | On-site deployment status, feedback collection, support tickets. |

---

## 4. Work Breakdown Structure (WBS)

### Phase 1: Planning & Compliance (Months 1-2)
*   **WBS 1.1:** Finalize system architecture and HL7/FHIR database schema.
*   **WBS 1.2:** Obtain data privacy approvals from the Ministry of Law and MoHFW.
*   **WBS 1.3:** Setup development and staging environments.

### Phase 2: Core Platform Development (Months 2-4)
*   **WBS 2.1:** Implement the Identity Resolution Engine (NID/BR verification).
*   **WBS 2.2:** Build the doctor clinical encounter logging and e-prescription interfaces.
*   **WBS 2.3:** Build the zero-knowledge pharmacy prescription dispensing module.
*   **WBS 2.4:** Set up the Redis caching layer and PostgreSQL write-replicas.

### Phase 3: Pilot Deployment (Months 4-6)
*   **WBS 3.1:** Deploy localized database cache servers in Sylhet pilot hospitals.
*   **WBS 3.2:** Conduct on-site training sessions for doctors and pharmacists.
*   **WBS 3.3:** Launch the pilot dashboard for real-time GIS epidemiological tracking.

### Phase 4: Nationwide Scale-up (Months 6-12)
*   **WBS 4.1:** Roll out system to all major public and private medical colleges.
*   **WBS 4.2:** Open API portals for private insurance integrations.
*   **WBS 4.3:** Transition operations to a sustainable Public-Private Partnership (PPP).

---

## 5. Risk & Issue Register

| Risk ID | Risk Description | Category | Impact | Likelihood | Mitigation Strategy |
|---|---|---|---|---|---|
| **R-101** | Resistance from doctors due to increased time spent entering data. | Adoption | High | High | Design clinical entry screens for speed (vitals auto-populate, drop-down diagnosis selections). |
| **R-102** | Frequent power cuts and internet outages in rural health complexes. | Technical | High | High | Implement offline-first local cache synchronization (e.g., PouchDB / local SQLite sync). |
| **R-103** | Delay in obtaining secure integration approvals for the government NID registry. | Political | Critical | Medium | Establish a Memorandum of Understanding (MoU) with the ICT Division early in Phase 1. |
| **R-104** | Vulnerability to cybersecurity breaches of sensitive medical histories. | Technical | Critical | Low | Deploy Kong API Gateway auth, apply AES-256 encryption for data at rest, and host regular penetration tests. |

---

## 6. Meeting Template: Steering Committee Status Sync

*   **Agenda:**
    *   Review of Milestones (Planned vs. Actual).
    *   Financial Budget Burn Rate.
    *   Pilot Operational Feedback (Hospital Onboarding, Bug Rate).
    *   Critical Policy Objections & Regulatory Clearances.
*   **Inputs required:** Project Director Status Report, QA Vulnerability Assessment, Pilot Ops Log.
*   **Outputs generated:** Meeting Minutes, Approved Change Orders, Strategic Directives for next Sprint.
