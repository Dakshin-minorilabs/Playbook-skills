# Playbook-skills

A curated collection of specialized agent skills for generating hyper-personalized, fully-cited, sales-ready **Account-Based Marketing (ABM) deal dossier PDF playbooks** for target accounts.

---

## 📌 Overview

This repository contains ready-to-use `.skill` packages designed for AI agents (such as Claude / Antigravity Agentic Assistant). Given just a target company's domain URL, these skills execute an automated multi-step research and synthesis workflow to produce an agency-grade 10-section PDF playbook tailored for sales reps, SDRs, and account executives.

By default, playbooks are written from the perspective of **PeopleSocial** (by EvonSys)—an employee advocacy and social selling platform—though seller details can be overridden for any B2B SaaS product.

---

## 📦 Available Skill Packages

| Skill Package | Version | Status | Description |
| :--- | :---: | :---: | :--- |
| **[`abm-account-playbook-v3.skill`](file:///c:/Users/daksh/OneDrive%20-%20MinoriLabs/Playbook-skills/abm-account-playbook-v3.skill)** | **v3** | **Production (Recommended)** | Incorporates all v2 improvements plus refinements from the Sept 17, 2026 demo-review call. Enforces a ≥500 employee headcount floor, strict 1-page-per-section length cap, Marketing/HR persona prioritization, per-message outbound citations, and a negative signal tact rule. |
| **[`abm-account-playbook-v2.skill`](file:///c:/Users/daksh/OneDrive%20-%20MinoriLabs/Playbook-skills/abm-account-playbook-v2.skill)** | **v2** | Superseded | Introduces account qualification gates, directed 8-step research checklist, stakeholder confidence heat maps, signal-grounded timelines, Sales Velocity metric, and mandatory Apollo API multi-threading. |
| **[`abm-account-playbook.skill`](file:///c:/Users/daksh/OneDrive%20-%20MinoriLabs/Playbook-skills/abm-account-playbook.skill)** | **v1** | Baseline | Initial baseline release defining the core 10-section ABM playbook structure and PeopleSocial seller profile. |

> [!TIP]
> Always use **`abm-account-playbook-v3.skill`** for new account playbook generation requests.

---

## 🗝️ Core Features & Capabilities (v3)

### 1. Account Qualification Gate (§0)
Before spending execution cycles building a playbook, the skill evaluates the target company against ICP parameters:
- **Headcount Floor**: ≥500 employees (multi-stakeholder complexity required).
- **Target Geographies**: US (90–95% primary target), MENA (5–10% secondary target).
- **Target Industries**: FinTech / Financial Services (Primary), e-Commerce, IT Services, Retail.

### 2. Directed Research & Mandatory Data Sources (§3)
- **8-Step Directed Checklist**: Fetches company leadership, press releases, tech stack signals, career boards, financial indicators, and industry news.
- **Apollo API Integration**: Mandatory department-level contact mapping for multi-threading and identifying key decision-makers and escalation contacts.
- **Confidence Tagging**: Every claim tagged as **High** (company site/press), **Medium** (aggregator profiles), or **Low/UNVERIFIED** (inference).

### 3. The 10-Section Deal Dossier Structure (§6)
Each generated playbook strictly contains 10 sections built in standard order:

1. **Account Fit Score & Firmographic Profile** – Concrete 3–5 parameter scoring (headcount tier, industry, geography, M&A/growth).
2. **Buying Committee & Stakeholder Heat Map** – Departmental mapping focusing on **Marketing** and **HR** functions, with confidence tags & red/green heat maps.
3. **Strategic Business Drivers & Pain Hypotheses** – 3 core business challenges connected to market signals.
4. **Intent Signals & "Why Now" Triggers** – Actionable timing events with a **Tact Rule** (never quote raw negative figures in outbound copy; reframe around opportunity).
5. **Value Proposition Map & ROI Framing** – PeopleSocial feature alignment with ranges-not-guarantees planning estimates.
6. **Personalized Outbound Sequences** – Multi-touch cold email and LinkedIn templates with **per-message factual citations**.
7. **Discovery Guide & Diagnostic Questions** – Consultative discovery questions tailored to buying committee roles.
8. **Battle Cards & Objection Handling** – Competitor counters, top 5 objection handlers, and internal-to-external translation guidelines.
9. **Scoped Pilot Design & Participant Sequence** – Phased pilot plan with explicit participant sequencing (who owns step 1 and why).
10. **Deal Execution Plan & Sales Velocity Metric** – Milestone gates, risk register, mutual action plan, and auditable Sales Velocity callout:
    $$\text{Sales Velocity} = \frac{\text{Qualified Opps} \times \text{Average Deal Value (ACV)} \times \text{Win Rate}}{\text{Sales Cycle Length}}$$

---

## 🎨 Visual Design & Layout Rules (§4 & §5)

- **Color System**: Dark Ink gradient (`#0A2620` → `#123B30`) for covers/breakers, Emerald Teal accent (`#17B37C`), near-black body text (`#15191C`), zebra striping (`#F6F8F7`).
- **Typography**: Embedded web fonts (Inter or Manrope) with a strict, consistent type scale.
- **Strict Length Cap**: Exactly **1 page per section** (10 content pages max + cover/TOC) for optimal SDR usability.
- **Page Break Rules**: CSS `break-before: page` enforced on Table of Contents and every Section Breaker page.

---

## 🔄 Relevance AI Synchronization (§10)

This skill repository works in parallel with a twin **Relevance AI Agent** build:
- **Shared Standards**: Shared seller profile (PeopleSocial), voice guide, 10-section structure, and formatting integrity rules.
- **Relevance AI Stack**: Uses Google Search, Firecrawl web scraper, Apollo API Call, HTML 2 PDF generator, and Knowledge Tables (`sales_marketing_pdf_2`, `personalized_emails_samples_docx`, `playbook_pdf_pdf_1`).

> [!IMPORTANT]
> Any updates to seller positioning, proof points, or section rules should be mirrored in both this skill repository and the Relevance AI agent prompt.

---

## 🚀 How to Use

1. **Extract or Load Skill**: Unpack the `.skill` archive (e.g., `abm-account-playbook-v3.skill`) into your agent's skills directory.
2. **Provide Target Input**:
   ```text
   Generate an ABM account playbook for https://examplecompany.com
   ```
3. **Output**: The agent executes the directed research phase, verifies inputs, and compiles a styled, agency-grade PDF deal dossier ready for sales execution.

---

## 📋 Version History

- **v3 (Sept 17, 2026)**: Added ≥500 headcount floor, 1-page-per-section length cap, Marketing/HR persona prioritization, per-message citation rule, negative signal tact rule, and Instagram/LinkedIn excitement feature emphasis.
- **v2 (Sept 17, 2026)**: Added qualification gate, 8-step directed research checklist, stakeholder confidence heat map, signal-grounded timelines, mandatory Apollo integration, and Sales Velocity calculation.
- **v1 (Sept 16, 2026)**: Baseline skill release establishing the 10-section ABM dossier framework and PeopleSocial default profile.