# DOCUMENT 09: FOUNDER NEGOTIATION PLAYBOOK

**Purpose:** This playbook provides the founder of CHCS with strategic guidelines, negotiation frameworks, IP protection strategies, and response templates for high-stakes meetings with venture capitalists, government officials, and corporate partners.
**Intended Audience:** Startup Founders and Executive Advisors.
**Why it matters:** Technology startup founders face significant risks of equity dilution, loss of operational control, and IP theft during early fundraising rounds. This playbook details how to navigate these challenges, negotiate term sheets, and protect the core vision of CHCS.

---

## 1. Meeting Strategy & Negotiation Framework

```
                      +-----------------------------------+
                      |     FOUNDER NEGOTIATION PILLARS   |
                      +-----------------------------------+
                                        |
            +---------------------------+---------------------------+
            |                                                       |
            v                                                       v
  [Align on Vision First]                                 [Protect Board Control]
  - Ensure partner accepts the public-                    - Never surrender the right
    good mission of CHCS.                                   to nominate key seats.
            |                                                       |
            +---------------------------+---------------------------+
                                        |
                                        v
                            [Anchor Valuations Early]
                            - Base asks on explicit 3-year
                              projections, not speculation.
```

### 1. Maintain a Public-Private Balance
Position CHCS as an essential public utility operating on commercial engines. If investors try to force a pivot to high B2C premium fees, remind them that the scale of the platform is what drives its B2B SaaS and analytics value.

### 2. Guard Board Control
During Seed rounds, target term sheets that preserve board control for the founding team (e.g., a 3-seat board: 2 Founders, 1 Investor). Avoid yielding veto rights over product roadmaps or key hires.

---

## 2. Hard Q&A Preparation: Best vs. Worst Answers

### Q1: "If the government decides to build this themselves, how does your business survive?"
*   **Worst Answer:** *"We hope they don't. We have good relationships with ministry officials so they will probably just use our software."*
    *   *Why it's bad:* Shows a lack of strategic defense and relies entirely on personal relationships.
*   **Best Answer:** *"The government's main obstacle isn't software development; it's the operational challenge of connecting fragmented private clinics and pharmacies. CHCS acts as the neutral, interoperable layer. It is faster and more cost-effective for the government to mandate and license our platform than to build and maintain their own national scale system from scratch."*

### Q2: "This is a public service. Why shouldn't this be a non-profit funded by NGOs?"
*   **Worst Answer:** *"Non-profits don't make money. We want to build a highly profitable startup."*
    *   *Why it's bad:* Sounds transactional and misses the strategic alignment of digital health infrastructure.
*   **Best Answer:** *"To build a system capable of serving 170 million people, we need sustainable operations. NGO funding is project-based and has high administrative overhead. By operating on a commercial SaaS and transaction fee model, we secure the capital needed for continuous system development and security audits, while providing basic access to citizens for free."*

---

## 3. Intellectual Property (IP) Protection Strategy

```
  +-----------------------------------------------------------------+
  |                  CHCS Core IP Protection Protocol               |
  +-----------------------------------------------------------------+
  | [Patents]     - File for identity resolution algorithm.          |
  | [Copyright]   - Copyright the custom interface code.            |
  | [Data Silos]  - Enforce data protection by design in system.    |
  | [Trade Secret]- Keep offline synchronization algorithms secure.  |
  +-----------------------------------------------------------------+
```

*   **Sovereign Data Protection:** Ensure all custom code, API gateways, and databases are owned by the parent company, with licenses granted to the government (rather than surrendering code ownership).
*   **API Security & Firewalls:** Never expose the underlying identity resolution logic directly. All external parties must query through the Kong API Gateway using encrypted tokens.
*   **Strict NDAs:** Ensure all partners, developers, and pilot hospitals sign comprehensive Non-Disclosure Agreements (NDAs) before getting access to API sandboxes.

---

## 4. Term Sheet Red Flags vs. Green Flags

When reviewing term sheets from institutional investors, look for these key indicators:

| Parameter | Green Flag (Acceptable) | Red Flag (Walk Away) |
|---|---|---|
| **Board Structure** | Balanced representation (e.g., 2 Founders, 1 Investor). | Investor gains immediate board control or veto power over CEO hiring. |
| **Liquidation Preference** | 1x non-participating preference. | Multiple (e.g., 2x or 3x) participating liquidation preferences. |
| **IP Clauses** | The operating company retains full ownership of all source code. | IP ownership transfers to the funding partner or government agency. |
| **Exclusivity** | Normal, limited-period exclusivity during due diligence. | Indefinite restriction on partnering with other public health agencies. |
