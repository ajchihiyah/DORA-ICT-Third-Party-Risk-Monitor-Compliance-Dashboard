# DORA ICT Third-Party Risk Monitor

> A SOC analyst frontend for real-time ICT third-party risk monitoring, concentration tracking, and DORA-compliant exit strategy simulation.

---

## The Problem

The EU **Digital Operational Resilience Act (DORA)** mandates that German financial institutions:

- Maintain a **complete register** of all ICT third-party providers
- Conduct **pre-contract risk assessments**
- Establish **credible exit and portability strategies**

**BaFin** has identified **concentration risk in non-EU hyperscalers** as a top 2026 priority, with recent outages causing cross-sector disruptions. Yet most SOCs lack real-time visibility into third-party security posture changes that could trigger an exit decision.

This dashboard closes that gap.

---

## Why It Matters

BaFin is actively using the DORA information register for **system-wide analytics** and conducting **deep-dive reviews** into multi-tenant providers. German banks are under pressure to **reduce hyperscaler dependency**. This project demonstrates both **SOC monitoring skills** and **DORA regulatory fluency** — exactly what German financial institutions are hiring for in 2026.

---

## Features

### Dashboard Tabs

| Tab | Description |
|-----|-------------|
| **Overview** | High-level KPIs, recent alerts, and vendor distribution by type / region |
| **Vendor Scorecards** | Per-vendor security scores, concentration, compliance tags, and traffic-light status |
| **Concentration Risk** | Interactive bubble chart showing vendor concentration vs. critical function dependency |
| **Exit Simulator** | Configurable exit scenario modeling with cost/time estimates and migration timeline |
| **Compliance Checklist** | DORA contract clause matrix (Audit Rights, Data Location, Subcontracting, TLPT) with gap analysis |
| **Alerts** | Filterable alert feed (Critical, High, Medium) with status tracking |

### Core Capabilities

- **Security Posture Monitoring** — Real-time tracking of third-party security ratings with traffic-light indicators. Alerts trigger when a vendor's score drops below contractual thresholds or when a new critical vulnerability is disclosed.
- **DORA Contract Clause Tracking** — Per-vendor verification of four mandatory clauses:
  - Audit Rights
  - Data Location (EU residency)
  - Subcontracting Transparency
  - TLPT (Threat-Led Penetration Testing) Support
- **Dynamic Concentration Risk Scoring** — Flags when a single vendor exceeds thresholds (e.g., "60% of critical functions depend on AWS Frankfurt — threshold exceeded"). BaFin priority: non-EU hyperscaler exposure.
- **Exit Scenario Simulation** — Models migration effort, data portability checks, and alternative vendor readiness. Configurable by vendor, scope (full / critical-only / non-critical), target alternative, and risk tolerance.
- **DORA Audit Pack Generator** — One-click export of all evidence for BaFin review, including:
  - ICT Third-Party Register
  - Contract Clause Evidence
  - Exit Strategy Documentation
  - Concentration Risk Analysis

---

## Data Model

The dashboard ships with 7 sample registered ICT third parties:

| Vendor | Type | Region | Criticality | Concentration | Security Score | Status |
|--------|------|--------|-------------|---------------|----------------|--------|
| AWS (Frankfurt) | Cloud Provider | EU | Critical | 60% | 82 | Green |
| Microsoft Azure (Germany) | Cloud Provider | EU | Critical | 25% | 88 | Green |
| Salesforce | SaaS | Non-EU | High | 15% | 74 | Yellow |
| CrowdStrike | MSP | Non-EU | Critical | 40% | 91 | Green |
| SAP Cloud (Frankfurt) | Cloud Provider | EU | High | 20% | 79 | Yellow |
| Google Cloud (Belgium) | Cloud Provider | EU | Medium | 10% | 85 | Green |
| IBM Cloud (Frankfurt) | Cloud Provider | EU | Medium | 5% | 76 | Yellow |

### Alert Examples

| ID | Vendor | Type | Severity | Status |
|----|--------|------|----------|--------|
| 1 | AWS (Frankfurt) | Concentration Risk | Critical | Open |
| 2 | CrowdStrike | Vulnerability (CVE-2026-YYYY) | Critical | Open |
| 3 | Salesforce | Rating Drop (74 < 75) | Medium | Acknowledged |
| 4 | SAP Cloud | Missing TLPT Clause | Medium | Open |
| 5 | AWS (Frankfurt) | Outage (45 min) | High | Resolved |

---

## Tech Stack

- **Frontend:** Pure HTML5 + CSS3 + vanilla JavaScript
- **Dependencies:** None (Google Fonts loaded via CDN)
- **Architecture:** Fully self-contained single file
- **Responsive:** Mobile-friendly layout

---

## Usage

1. Open `dora_dashboard.html` in any modern browser
2. Navigate tabs using the top navigation bar
3. Click vendor cards to open detailed modals with contract clauses, exit readiness, and recent events
4. Use the **Exit Simulator** to model vendor exit scenarios:
   - Select vendor, migration scope, target alternative, and risk tolerance
   - View estimated cost, timeline, data portability, and downtime
5. Click **DORA Audit Pack** to generate BaFin-ready documentation

---

## Regulatory Alignment

| DORA Article | Requirement | Dashboard Feature |
|--------------|-------------|-------------------|
| **Art. 28** | ICT third-party risk management | Vendor register, risk scorecards, alerts |
| **Art. 29** | Concentration risk monitoring | Bubble chart, threshold alerts, BaFin priority flag |
| **Art. 30** | Exit strategy requirements | Exit simulator, data portability, alternative readiness |
| **BaFin 2026** | Non-EU hyperscaler priority | Non-EU exposure KPI, concentration warnings |

---

## File Structure

```
dora_dashboard.html    # Single-file application (HTML + CSS + JS)
```

---

## Browser Support

- Chrome / Edge / Firefox / Safari (latest versions)
- Mobile browsers (iOS Safari, Chrome Mobile)
