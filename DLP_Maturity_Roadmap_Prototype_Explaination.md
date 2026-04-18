# DLP Maturity Journey Simulator — CEO Briefing

---

## What This Application Is

This simulator makes one argument: a DLP program is not a product you install — it is a
discipline you build over 12 months. Every number on screen — the false positive rate
dropping from 87% to 4%, ₹65 Cr in risk avoided, 71 threats caught — is the result of
structured, documented, human-driven work repeated month after month.

The **time-travel slider** at the top of the application lets you move through all 12 months.
Every screen updates as you drag it — KPI tiles, charts, log samples, timelines, role
assignments. Four role buttons in the header (CEO, CISO, SOC Analyst, DLP Admin) show the
same journey from four different vantage points.

---

## Phase 1 — Discovery (Months 1–3)

### Purpose & Impact

Before you can stop data from leaving, you need to understand where it actually goes. Most
organizations deploy DLP in block mode on Day 1 and immediately face two crises: real threats
buried under noise they cannot read, and angry business users whose legitimate workflows are
being interrupted.

Phase 1 prevents both by deploying in **monitor-only mode** — observing everything, blocking
nothing. The team spends three months learning which alerts are genuine risks and which are
the Finance team doing daily reconciliation, the Marketing team running an approved campaign,
or a product SKU that happens to look like an Aadhaar number to an unvalidated regex pattern.

By the end of Month 3, three targeted changes — none requiring a single user to be blocked —
reduce alerts from 8,500 to 6,500 and the false positive rate from 87% to 65%.

---

### How It Looks in the Application

**Drag the slider to Month 1.** The four KPI tiles across the top read:

> **8,500** Total Alerts · **87%** False Positive Rate · **2** True Threats Caught ·
> **₹0.8 Cr** Risk Avoided

Below the slider, the phase label reads *Phase 1 · Discovery*. The CEO headline reads:
*"We have visibility into our data flows for the first time."*

**Switch to the DLP Admin role.** Four insight cards appear at the bottom of the screen.
The first card — **Enforcement Mode** — displays **Monitor Only** in cyan, with the
description *"All 47 policies in observe mode — nothing blocked."* This card is the
single clearest indicator of where the program stands at any given month.

The Tuning Actions Timeline above the insight cards shows exactly **2 entries** (visible
in the Total Entries counter in the timeline header) — nothing else exists yet:

- *Initial deployment in Monitor-Only mode* — DLP Admin —
  "All 47 default policies deployed without blocking. Goal: capture baseline of all data
  movement." Impact: *Baseline established: 8,500 alerts captured.*
- *First triage categorization framework* — SOC L2 —
  "Created 6-category triage taxonomy: TP-Malicious, TP-Negligent, FP-Pattern, FP-Legitimate,
  FP-Test, Policy Mismatch." Impact: *Triage consistency across analyst team.*

No policy changes, no whitelists, no regex work. Just deployment and a triage framework.

**Switch to the SOC Analyst role → Live Log Stream tab.** Eight fixed log cards appear —
the same eight every time you open Month 1. Seven carry a **FALSE POSITIVE** verdict badge,
one carries **TRUE POSITIVE**. The first two cards illustrate the core problem:

- `PCI_DSS_Compliance` firing on `transactions_q1.csv` uploaded to `dropbox.com` by
  `arjun.mehta` (Finance, low risk) — **FALSE POSITIVE**: legitimate Finance reconciliation
  workflow mistakenly flagged
- `PII_PAN_Detection` firing on `vendor_kyc.pdf` going to `wetransfer.com` by
  `priya.sharma` (Marketing, low risk) — **FALSE POSITIVE**: an approved vendor onboarding
  process

These are real business processes. Blocking them on Day 1 would have caused operational
damage with no security benefit.

**Drag to Month 2.** The DLP Admin timeline entry counter moves to **4 entries**. Two new
Month 2 entries have appeared:

- *Top 20 legitimate workflows catalogued* — DLP Admin + Liaisons —
  "Worked with department heads to document approved data flows. Identified 15 destinations
  for whitelisting." Impact: *Foundation for context-aware policies.*
- *Mapped policies to regulatory requirements* — Compliance —
  "Each DLP policy now linked to specific DPDP/GDPR/PCI/HIPAA control objectives."
  Impact: *Compliance traceability established.*

The Enforcement Mode card still shows **Monitor Only** — unchanged from Month 1.

**Drag to Month 3.** The KPI tiles update:

> **6,500** Alerts · **65%** FPR · **7** Threats · **₹2.8 Cr** ROI

The Enforcement Mode card still reads **Monitor Only**. The timeline entry counter now
shows **7 entries** — the 4 from Months 1 and 2, plus three new Month 3 entries:

- *SSN regex tightened — required word boundaries* — DLP Admin —
  "Old pattern `\d{3}-\d{2}-\d{4}` matched product SKUs. New pattern requires word
  boundaries and dash separators." Impact: **−1,200 monthly false positives**
- *Credit card detection enhanced with Luhn check* — DLP Admin —
  "Added Luhn algorithm validation to PCI policy. Eliminates random 16-digit number false
  matches." Impact: **−800 monthly false positives**
- *Whitelisted 15 known-good destinations* — DLP Admin —
  "Approved partner domains, internal SaaS tools, and validated vendor portals added to
  whitelist." Impact: **−700 monthly false positives**

Those three Month 3 changes — made possible by two months of observation — account for
the entire drop from 8,500 to 6,500 alerts and from 87% to 65% FPR.

---

## Phase 2 — Tuning (Months 4–6)

### Purpose & Impact

With the data landscape mapped, selective enforcement begins. The team moves the five most
confident policies to block mode while continuing to refine the rest. This phase delivers the
program's first visible wins — a real exfiltration attempt stopped and documented, negligent
users coached rather than silently blocked, and the false positive rate cut by 75% from its
starting point by the halfway mark.

**By Month 6:** Alerts 4,200 · FPR 22% · Threats caught 25 (cumulative) · ROI ₹12 Cr ·
Analyst hours/week 60 · Compliance posture score 78%.

---

### How It Looks in the Application

**Drag to Month 4.** KPI tiles:

> **5,800** Alerts · **48%** FPR · **12** Threats · **₹4.5 Cr** ROI

The Enforcement Mode card at the bottom of the DLP Admin view changes colour from cyan to
amber and now reads **Selective Block**, with the description *"Top 5 high-confidence
policies actively blocking."* This is the first time the program has blocked anything.
The timeline entry counter shows **9 entries**. Two new Month 4 entries:

- *Top 5 policies moved to BLOCK mode* — DLP Admin + CISO —
  "High-confidence policies (PII to public cloud, source code exfiltration, PHI to USB)
  now actively blocking." Impact: *First real exfiltration attempt blocked: source code to
  personal Dropbox.*
- *Repeat-offender escalation process formalized* — HR Partner —
  "3-strike framework: coaching → manager notification → HR involvement. Documented and
  approved by Legal." Impact: *Defensible disciplinary framework.*

CEO headline: *"First real exfiltration attempt blocked."*

**Switch to the CISO role → Role Activation Swimlane.** At Month 4, the **HR Partner** row
lights up cyan for the first time — dark grey in Months 1–3. This is the application's
visual proof that the right resource is activated at the right time, not at deployment.

**Switch to the SOC Analyst → Triage Simulator.** Click Generate New Incident. The first
incident shown is `IP_Source_Code` firing on `core_engine_v3.zip` uploaded to
`github.com (personal)` by `rohan.gupta` (Engineering, high risk) — severity Critical,
action Blocked. Click **True Positive — Malicious Intent.** Step 2 of the flow indicator
lights up. A tuning ticket is immediately generated, routed to the Insider Threat Team,
priority Critical, SLA 15 minutes.

**Drag to Month 5.** Two new Timeline entries, entry counter moves to **11**:

- *Just-in-time coaching pop-ups deployed* — Security Awareness —
  "When user attempts a borderline action, contextual education appears explaining policy and
  alternatives." Impact: *60% of users self-correct after first coaching.*
- *Marketing department workflow exception* — DLP Admin —
  "Approved bulk customer email pattern for verified marketing campaigns." Impact:
  **−340 monthly false positives.**

In the CISO Swimlane, the **Security Awareness** row lights up cyan for the first time at
Month 5.

**Drag to Month 6.** KPI tiles:

> **4,200** Alerts · **22%** FPR · **25** Threats · **₹12 Cr** ROI

CEO headline: *"Halfway home — false positives down 75%."* The CEO view's FPR trend chart
shows a steep curve from 87% at Month 1 to 22% — well above the dashed green 5% goal
line, but clearly on trajectory. The Before/After comparison right panel (labelled
**CURRENT STATE**) shows: alerts 4,200, FPR 22%, analyst hours 60 hrs/week, business
disruption Low, compliance evidence Maturing.

Two Month 6 Timeline entries, counter moves to **13**:

- *First quarterly policy review* — CISO + DLP Admin —
  "Comprehensive review of all 47 policies. 12 retired, 8 modified, 3 new policies added
  based on emerging risks." Impact: *Policy portfolio rationalized.*
- *UEBA correlation enabled* — DLP Admin —
  "DLP alerts now enriched with user behavior baselines. Risk scores computed per user."
  Impact: *Behavioral anomalies surfaced.*

The **CISO** row in the Swimlane lights up at Month 3 (first activation — Compliance
Officer engagement) and again here at Month 6 for the quarterly strategic review.

---

## Phase 3 — Enforcement (Months 7–9)

### Purpose & Impact

With false positives under 20%, two new capabilities become safe to activate. First,
behavioral analytics — UEBA cross-correlates DLP alerts with HR resignation flags and
identity signals to catch multi-channel insider threats invisible to any single alert.
Second, and most counterintuitively, the biggest single false positive reduction in the
entire program comes not from a policy change but from IT fixing a broken internal tool
that was forcing users into unsafe workarounds.

**By Month 9:** Alerts 2,900 · FPR 9% (first time below 10%) · Threats 51 · ROI ₹33 Cr ·
Analyst hours/week 35 · Disruption: Very Low.

---

### How It Looks in the Application

**Drag to Month 7.** KPI tiles:

> **3,800** Alerts · **18%** FPR · **34** Threats · **₹18 Cr** ROI

The Enforcement Mode card changes to rose-red and reads **Broad Block + UEBA**, with
description *"80%+ policies blocking · Behavioral analytics active."* Timeline counter:
**15 entries**. Two new Month 7 entries:

- *HR + DLP integration live* — Insider Threat Team —
  "Users with resignation flags, performance issues, or access changes get elevated DLP
  scrutiny." Impact: *First insider threat caught: departing employee, 3-channel
  exfiltration.*
- *Print policy contextualized* — DLP Admin —
  "Print monitoring now considers document classification, page count, and time-of-day
  patterns." Impact: **−400 monthly false positives.**

CEO headline: *"Insider risk detection catches resignation-correlated threat."*

In the CISO Swimlane, the **Insider Threat Team** row lights up cyan at Month 7 — dark
grey for the previous six months. Behavioural analytics requires clean signal to work with;
the tuning done in Phases 1 and 2 created that signal.

**Drag to Month 8.** KPI tiles:

> **3,400** Alerts · **14%** FPR · **42** Threats · **₹25 Cr** ROI

Timeline counter: **17 entries**. Two Month 8 entries — the second of which is unique in
the entire program:

- *Fixed broken secure file-share tool* — **IT Operations** —
  "Root cause analysis revealed users emailed sensitive files because the secure tool was
  unusable. IT fixed it." Impact: **−800 monthly false positives. Process improvement win.**
- *Finance reconciliation workflow approved* — Business Process Owner —
  "Daily PCI data reconciliation between Finance and processor formally approved with audit
  logging." Impact: **−600 monthly false positives.**

The IT Operations entry is the only one in all 21 Timeline entries not filed by a security
or compliance function. It is a process fix, not a policy change — and its impact (−800
false positives) exceeds every individual policy tuning action in the program's history.

The **Business Process Owners** row lights up in the CISO Swimlane for the first time at
Month 8.

**Drag to Month 9.** KPI tiles:

> **2,900** Alerts · **9%** FPR · **51** Threats · **₹33 Cr** ROI

FPR breaks below 10% for the first time. Timeline counter: **18 entries**. One Month 9
entry:

- *80% of policies moved to BLOCK enforcement* — DLP Admin —
  "Comprehensive review confirmed enforcement-ready. Remaining 20% kept in alert mode for
  edge cases." Impact: *Broad enforcement achieved without business disruption.*

The Enforcement Mode card reads **Broad Block**.

---

## Phase 4 — Maturity (Months 10–12)

### Purpose & Impact

The program reaches its intended steady state. SOAR automation handles 70% of routine
incidents without analyst involvement. An independent external audit validates controls
against DPDP Act, GDPR, PCI-DSS, and HIPAA — and returns zero findings. The false positive
rate stabilises sustainably below 5%. The team shifts from firefighting to governance.

**By Month 12:** Alerts 1,900 · FPR 4% · Threats 71 · ROI ₹65 Cr · Analyst hours/week 22 ·
Compliance posture score 98% · Audit-Ready: Yes.

---

### How It Looks in the Application

**Drag to Month 10.** Enforcement mode card: **Broad Block + SOAR** in violet, description
*"Full enforcement · SOAR automation handling routine cases."* The **SOC Engineering** row
lights up in the CISO Swimlane for the first time. Timeline counter: **19 entries**:

- *SOAR playbooks for top 10 incident types* — SOC Engineering —
  "Automated triage, enrichment, and remediation for routine incidents. Analysts now focus
  on complex cases." Impact: *70% of incidents handled without human touch.*

**Drag to Month 11.** Timeline counter: **20 entries**:

- *External audit completed — zero findings* — Compliance + Legal —
  "Independent auditors validated DLP program against DPDP, GDPR, PCI-DSS, and HIPAA
  requirements." Impact: *Audit-ready posture confirmed.*

The Audit-Ready Status tile in the CEO view changes to **Yes**.

**Drag to Month 12.** Enforcement Mode card: **Mature Operation** in emerald, description
*"Steady-state · Continuous tuning · Audit-ready."* Timeline counter: **21 entries**.
Last entry:

- *Steady-state operations established* — CISO —
  "Quarterly tuning cadence locked in. Continuous improvement framework operational.
  Year 2 roadmap approved." Impact: *Sustainable program achieved.*

The KPI tiles show the final state:

> **1,900** Alerts · **4%** FPR · **71** Threats · **₹65 Cr** ROI

The **Before/After comparison** in the CEO view shows the full transformation:

| Metric | MONTH 1 — UNTUNED | CURRENT STATE (M12) |
|---|---|---|
| Monthly Alerts | 8,500 | 1,900 |
| False Positive Rate | 87% | 4% |
| Analyst Hours / Week | 160 hrs | 22 hrs |
| Real Threats Detected | 2 / month | 5.9 / month |
| Business Disruption | High | Negligible |
| Compliance Evidence | None | Excellent |

The **ROI Breakdown** shows six cards calculated live from the Month 12 data:

| Business Outcome | Value | How Calculated |
|---|---|---|
| Breach Cost Avoidance | ₹65.0 Cr | roi = 65 |
| Regulatory Fine Avoidance | ₹26.0 Cr | roi × 0.4 |
| Cyber Insurance Savings | 24% | complianceScore 98 × 0.25 |
| Analyst Productivity Gain | 86% | (160 − 22) / 160 × 100 |
| IP Protection Value | ₹56.8 Cr | threats 71 × 0.8 |
| Brand Trust Score | +56 pts | complianceScore 98 − 42 |

The **FPR trend chart** shows the complete 12-month curve — steep early decline through
Phases 1 and 2, levelling below 10% in Phase 3, and a flat mature line comfortably below
the dashed green 5% goal line through Months 10–12.

---

## The Feedback Loop — How Every Triage Decision Becomes a Policy Change

### Purpose & Impact

The false positive rate does not improve by itself. It improves because every time an analyst
correctly identifies a false positive, that identification triggers a specific, documented
policy change preventing the same false positive from recurring. That cycle — triage verdict
to tuning ticket to Forcepoint configuration change to timeline entry — running continuously
across hundreds of incidents per month is the mechanism that moves the program from 87% to 4%.

Without this loop, analysts triage the same false positives indefinitely. With it, every
correctly categorized incident makes the system incrementally smarter. This is what separates
a DLP program that matures from one that stagnates.

---

### How It Looks in the Application — A Complete Walk-Through

**Set the slider to Month 3. Switch to SOC Analyst → Triage Simulator tab.**

The 3-step flow indicator at the top reads **[1·Triage] → [2·Ticket] → [3·Tune]**. Step 1
is lit cyan. This tracks exactly where you are in the cycle.

Click **Generate New Incident.** The application shows a fixed incident from the Month 3
log set: `PII_Aadhaar_Detection` firing on `employee_records.xlsx`, channel SMTP,
destination `gmail.com`, user `sneha.patel` (HR, low risk), severity High, action Audited.
Month 3 is still monitor-only — the Enforcement Mode card confirms this.

As the analyst, you consider the context. HR department. Low-risk user. Personal Gmail
destination is unusual. But you recall from the DLP Admin Timeline that `PII_Aadhaar_Detection`
is using a loose regex (`\d{4}\s?\d{4}\s?\d{4}`) that matches any 12 consecutive digits —
including employee ID numbers and product codes regularly handled by HR. Your assessment:
pattern match error, not a genuine exfiltration.

**Click False Positive — Pattern Match Error.**

Step 2 lights up in the flow indicator. The result panel appears immediately below the
incident card:

> *Action triggered: Refine Detection Regex to Eliminate Pattern Collisions*
> *Policy change: Loose pattern (high collision) → Validated pattern (low collision)*
> *Tuning ticket auto-generated and routed to DLP Admin*
> *Projected impact: −120 alerts/month · −1.4% FPR*

Below the triage panel, the Tuning Tickets Generated section shows a new card:

```
TKT-2026-03-1001 · M3 · Medium priority · SLA: 2 business days
Refine Detection Regex to Eliminate Pattern Collisions
verdict:         False Positive — Pattern Error
policy:          PII_Aadhaar_Detection
routed to:       DLP Admin
forcepoint path: Main → Policies → Content Classifiers →
                 [Classifier Name] → Pattern Definition
change:          Loose pattern (high collision) →
                 Validated pattern (low collision)
projected:       −120 alerts/mo · −1.4% FPR
```

The Cumulative Impact Meter shows: **−120 alerts/month · −1.4% FPR · −6.0 analyst
hours/week.**

**Click View Full Implementation Details** on the ticket card.

The enterprise modal opens. This is everything the DLP Admin needs to apply the change
safely — no back-and-forth, no ambiguity.

**Section 2 — Approval Workflow** shows a four-stage pipeline. SOC is green (completed).
DLP Admin is cyan and glowing (action required here). Peer Review and CAB Change Advisory
Board are grey (pending). The admin cannot push this to production alone — peer review and
change board approval are enforced by the ticket structure itself.

**Section 3 — Pre-Change Checklist** shows four items to check off before touching any
policy in Forcepoint. Click each — it strikes through and turns grey. These checkboxes are
the documented evidence of due diligence that an external auditor expects to see.

**Section 4 — Configuration Diff** shows the exact policy change in Forcepoint YAML:

```
− classifier_id: PII_AADHAAR_LOOSE
− regex: \d{4}\s?\d{4}\s?\d{4}
− validation: none
  # Problem: matches phone numbers, invoice IDs, product SKUs

+ classifier_id: PII_AADHAAR_STRICT_V2
+ regex: \b[2-9]\d{3}[\s-]?\d{4}[\s-]?\d{4}\b
+ validation: verhoeff_checksum       # MOSIP standard
+ context_keywords:
+   required_one_of: [aadhaar, uid, आधार, identity]
+   exclusion_keywords: [invoice, sku, phone, tracking]
+ confidence_threshold: 0.85
```

The old pattern matched any 12-digit sequence. The new pattern matches only numbers
starting with 2–9 (all Aadhaar numbers begin with 2–9), validates the Verhoeff checksum
every genuine Aadhaar carries, and requires the word "aadhaar" or "uid" to appear nearby.
An employee ID or product code cannot pass all three tests. The **Copy** button places
this directly on the clipboard for pasting into Forcepoint Policy Manager.

**Section 5 — Forcepoint UI Navigation** gives the DLP Admin eight numbered steps with
exact console menu paths highlighted in cyan — `Main → Policies → Content Classifiers`,
`Edit Classifier`, `Pattern Definition tab`, `Validation → Verhoeff Checksum`,
`Pattern Tester → Run Validation`, deploy to `Test Group First`, then after 24 hours
`Promote to Production`. A junior admin can execute this without additional documentation.

**Section 6 — Validation** provides the CLI test command. **Section 8 — Rollback Plan**
confirms a five-minute recovery path if the change introduces unexpected false negatives
after deployment.

**Click Mark as Applied** in the modal footer.

The modal closes. The ticket card shows status **Resolved.** Step 3 of the flow indicator
lights up. **Switch to the DLP Admin role.**

The timeline entry counter — which showed **7** before — now shows **8**. At the very top
of the Tuning Actions Timeline, above all 21 pre-defined program entries, is a new entry
with a cyan left border and a cyan **"From your triage"** badge:

```
M3 · DLP Admin
Refine Detection Regex (PII_Aadhaar_Detection)
Triggered by analyst triage of incident INC-2026-03-1003
→ Impact: −120 monthly alerts, −1.4% FPR
```

The **From Triage** counter in the timeline header, which showed 0, now shows **1**.

This entry now sits in the same audit trail as the CISO-approved quarterly review at
Month 6 and the externally validated audit completion at Month 11. A single analyst triage
decision has become a permanent, documented program record.

That is one cycle of the feedback loop. One analyst. One verdict. One configuration change.
One timeline entry. −120 false positives eliminated every month going forward.

The FPR curve in the CEO view — 87% in Month 1 to 4% in Month 12 — is the accumulated
result of that loop running continuously for 12 months. Not automation. Not a tool fixing
itself. Disciplined people, structured process, every observation closing back into a
documented change. That is what this application demonstrates.
