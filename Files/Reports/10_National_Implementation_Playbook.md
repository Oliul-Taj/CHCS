# DOCUMENT 10: NATIONAL IMPLEMENTATION PLAYBOOK

**Purpose:** This playbook provides detailed instructions for executing the pilot program and managing regional and national rollouts of CHCS across Bangladesh. It outlines operations, user training, tech support, and disaster recovery processes.
**Intended Audience:** Operations Directors, Field Implementation Managers, Regional Coordinators, and Hospital Technical Staff.
**Why it matters:** Technology deployment in low-resource settings requires systematic operations. This playbook ensures field teams can install hardware, train clinical users, manage software updates, and handle local connectivity failures without disrupting active hospital workflows.

---

## 1. Pilot Rollout Execution Guide (Sylhet Phase)

The pilot phase connects 2 public hospitals, 5 private clinics, and 50 pharmacies over a 6-month period.

```
                    +------------------------------------+
                    |        PILOT ROLLOUT SEQUENCE      |
                    +------------------------------------+
                                      |
     +--------------------------------+--------------------------------+
     |                                |                                |
     v                                v                                v
[Week 1-2: Setup]             [Week 3-4: Training]             [Month 2-6: Sync Check]
- Deploy local cache nodes    - Train Champion staff           - Validate data sync
- Verify NID API connection   - Run sandboxed test entries     - Audit database write speeds
```

### Key Milestones
*   **Infrastructure Verification (Weeks 1-2):** Deploy offline cache hardware in the designated hospitals. Test API queries to the central registry.
*   **User Training (Weeks 3-4):** Conduct interactive training sessions using sandboxed test environments.
*   **System Launch (Month 2):** Go live with patient registration and clinical logs.
*   **Audit & Review (Months 3-6):** Assess query latency, data sync rates, and software bugs. Share weekly summaries with the Steering Committee.

---

## 2. Phased National Scaling Strategy

Following a successful pilot, CHCS will scale across Bangladesh in three major waves:

```
                  +-----------------------------------+
                  |          NATIONAL SCALE-UP        |
                  +-----------------------------------+
                                    |
            +-----------------------+-----------------------+
            |                                               |
            v                                               v
  [Wave 1 (Months 7-12)]                         [Wave 2 (Months 13-24)]
  - Divisional medical colleges.                 - District level hospitals.
  - Urban private clinics.                       - Upazila health complexes.
            |                                               |
            +-----------------------+-----------------------+
                                    |
                                    v
                          [Wave 3 (Months 25+)]
                          - Community clinics (rural).
                          - National retail pharmacies.
```

---

## 3. Help Desk & Operational Support Model

To support users, CHCS operates a three-tiered support model:

```
  +-----------------------------------------------------------------+
  |                  CHCS Support Operations Model                  |
  +-----------------------------------------------------------------+
  | [Tier 1: On-Site] - Hospital Digital Health Champions.          |
  |                   - Resolve password resets, basic UI queries.  |
  +-----------------------------------------------------------------+
  | [Tier 2: Regional]- Regional Help Desk (Divisional offices).    |
  |                   - Hardware swaps, network configuration issues|
  +-----------------------------------------------------------------+
  | [Tier 3: Central] - Central Dev & Security Operations.           |
  |                   - Database recoveries, API failures, bugs.    |
  +-----------------------------------------------------------------+
```

---

## 4. Incident Management & Disaster Recovery Protocols

Operational disruptions are categorized by severity:

| Severity Level | Example Scenario | Target Response Time (SLA) | Escalation Path |
|---|---|---|---|
| **L-1 (Critical)** | Central API Gateway is down; no NID lookups or EHR access nationwide. | < 15 minutes | DevOps Lead -> CTO -> Project Director |
| **L-2 (High)** | Local cache server at a major hospital fails; data sync is offline. | < 1 hour | Regional IT Lead -> Systems Engineer |
| **L-3 (Medium)** | Pharmacist unable to retrieve a prescription due to local config error. | < 4 hours | On-Site Champion -> Help Desk Agent |
| **L-4 (Low)** | Minor bug in the ministry analytics report dashboard export. | < 48 hours | Bug tracker queue -> Software Engineer |

### Offline Data Synchronization & Conflict Resolution
When a clinic's internet connection goes down:
1.  **Local Logging:** The local cache server continues to log clinical encounters locally, using UUIDs as primary keys.
2.  **Queue Syncing:** When internet connection is restored, the local client pushes changes to the central queue.
3.  **Conflict Resolution:**
    *   If a patient's record was updated in multiple locations during an outage, the system uses the record signed by the medical practitioner with the latest timestamp.
    *   Conflicts are flagged in the administrative panel for manual review if data discrepancy thresholds are met.
