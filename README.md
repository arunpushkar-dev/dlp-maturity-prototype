# DLP Maturity Journey Simulator

A browser-based interactive simulator demonstrating how a Forcepoint DLP programme matures from initial deployment — 8,500 alerts, 87% false positive rate — to production maturity — 1,900 alerts, 4% false positive rate — over 12 months.

Built as a **single HTML file**. No installation. No server. No dependencies to install. Download and open in a browser.

---

## Quick Start — Three Steps

### Step 1 — Download

Click the green **Code** button on this page → **Download ZIP** → extract the ZIP.

You will find one file:

```
dlp-maturity-prototype_application_poc.html
```

### Step 2 — Open in your browser

Double-click `dlp-maturity-prototype_application_poc.html`.

It opens in your default browser. If it does not, right-click → **Open with** → Chrome, Edge, Firefox, or Safari.

### Step 3 — Use the slider

Drag the **month slider** at the top from Month 1 to Month 12. Every number, chart, log, and timeline entry on screen updates instantly.

> **Internet connection required** for first load only — the application fetches fonts and charts from public CDNs (Google Fonts, Chart.js). Once loaded, all interaction is local. Nothing is sent to any server.

---

## Browser Compatibility

| Browser | Status |
|---|---|
| Chrome 100+ | ✅ Recommended |
| Edge 100+ | ✅ |
| Firefox 100+ | ✅ |
| Safari 15+ | ✅ |
| Internet Explorer | ❌ Not supported |

---

## What the Application Does

The simulator shows a 12-month DLP maturity programme from four different role perspectives. Every screen updates as you move the month slider — metrics, charts, logs, timelines, and narrative all reflect the selected month.

---

## The Month Slider — Primary Control

The slider at the top of every screen runs from **Month 1 to Month 12**.

- **Drag** left or right to move between months
- **Click any month marker** (M1 through M12) to jump directly to that month
- Watch the four KPI tiles update as you move:

| KPI | Month 1 | Month 12 |
|---|---|---|
| Total Alerts | 8,500 | 1,900 |
| False Positive Rate | 87% | 4% |
| True Threats Caught | 2 | 71 |
| Risk Avoided | ₹0.8 Cr | ₹65 Cr |

---

## The Four Role Views

Four buttons in the header switch between role-specific perspectives.

---

### CEO / Board

**Best for:** Board presentations, investment justification, programme progress reviews.

**What to look at:**

| Element | What it shows |
|---|---|
| Executive headline | One-sentence narrative for the selected month — changes every month |
| FPR trend chart | 12-month false positive rate curve with 5% goal line |
| Before/After comparison | Month 1 baseline vs current month across 6 metrics |
| ROI Breakdown | 6 business outcome cards calculated live from current month data |
| 4 big metric tiles | Risk reduction %, incidents prevented, compliance score, audit-ready status |

**Recommended demo path:**

1. Start at Month 1 — read the headline, note the KPIs
2. Drag slowly to Month 6 — pause and read: *"Halfway home — false positives down 75%"*
3. Drag to Month 12 — read the final headline
4. Scroll to Before/After — read across all six rows
5. Scroll to ROI Breakdown — walk through the six business outcome cards

---

### CISO

**Best for:** Programme health reviews, resourcing decisions, quarterly executive briefings.

**What to look at:**

| Element | What it shows |
|---|---|
| Alert Volume by Category | Donut chart — PII / PCI / PHI / IP / Confidential distribution |
| Channel Risk Distribution | Horizontal bar — Email / Cloud / USB / Print / Web |
| Maturity Dashboard | Multi-axis chart — all 3 key metrics across 12 months simultaneously |
| Role Activation Swimlane | Which teams are active each month — watch new rows light up as the programme matures |

**Key observation in the Swimlane:**

Move the slider month by month and watch the rows light up:
- **Month 1** — only DLP Admin and SOC Analyst are active
- **Month 4** — HR Partner activates for the first time
- **Month 5** — Security Awareness activates
- **Month 7** — Insider Threat Team activates
- **Month 8** — Business Process Owners activate
- **Month 10** — SOC Engineering activates
- **Month 12** — all 11 roles have been active at the right time

Each activation is deliberate — no team is involved before the programme produces the signal quality their work requires.

---

### SOC Analyst

**Best for:** Training sessions, triage workflow demonstrations, analyst onboarding.

Three tabs are available.

#### Tab 1 — Live Log Stream

Eight fixed Forcepoint DLP log cards for the selected month. Each card shows:

- Incident ID, severity badge, data category
- User name, department, risk level
- Policy triggered, channel, destination, file name, data type
- Verdict badge — **TRUE POSITIVE** or **FALSE POSITIVE**

The verdict distribution matches the month's FPR. At Month 1, seven of eight cards are false positives. At Month 12, all eight are true positives.

#### Tab 2 — Triage Simulator

The core interactive feature. Demonstrates the complete feedback loop from analyst triage decision to DLP Admin policy change.

**How to use it — step by step:**

**Step 1** — Click **→ Generate New Incident**

A realistic DLP incident appears. Read the full details: user, department, risk level, channel, destination, policy triggered, file name, data type detected, and action taken.

**Step 2** — Choose a verdict

Click one of the four verdict buttons:

| Button | When to use it |
|---|---|
| ▲ True Positive — Malicious Intent | Deliberate exfiltration attempt |
| ▲ True Positive — Negligent / Accidental | Genuine violation by a careless user |
| ▼ False Positive — Pattern Match Error | Detection regex matched something it should not |
| ▼ False Positive — Legitimate Business Use | Real approved workflow incorrectly flagged |

**Step 3** — Read the result panel

A result panel appears below the incident showing:
- The action triggered
- The policy change — before state → after state
- Projected impact: alerts reduced per month, FPR delta, analyst hours saved

**Step 4** — Scroll down to the generated ticket

A tuning ticket appears in the **Tuning Tickets Generated** section with:
- Ticket ID, priority, SLA, owner, Forcepoint console path
- Policy change summary
- Projected impact metrics
- Two buttons: **View Full Implementation Details** and **Apply Tuning**

**Step 5** — Open the enterprise ticket modal

Click **View Full Implementation Details**. The modal contains eight sections:

| Section | Contents |
|---|---|
| §1 Source Incident | The triggering event — full details |
| §2 Approval Workflow | 4-stage pipeline: SOC → DLP Admin → Peer Review → CAB |
| §3 Pre-Change Checklist | Click each checkbox to mark as completed |
| §4 Configuration Diff | Forcepoint YAML — red minus lines (before), green plus lines (after). Copy button included |
| §5 Forcepoint UI Navigation | Numbered click-by-click steps with exact console menu paths |
| §6 Validation Command | CLI test command with copy button |
| §7 Impact Forecast | 3 metric cards: alerts reduced, FPR%, analyst hours saved |
| §8 Rollback Plan | Emergency procedure if the change causes problems |

The modal footer has three buttons:
- **Close** — closes without action
- **Export Change Request** — downloads a `.txt` file formatted for ServiceNow/Jira/CAB submission
- **✓ Mark as Applied** — resolves the ticket and pushes the action to the DLP Admin timeline

**Step 6** — Click Mark as Applied, then switch to DLP Admin

The modal closes. The ticket shows **Resolved**.

Switch to the **DLP Admin** role. At the top of the Tuning Actions Timeline — above all 21 pre-defined programme entries — is your analyst-generated entry with a cyan **"From your triage"** badge. The **From Triage** counter in the timeline header has incremented from 0 to 1.

This is the closed feedback loop: analyst observation → tuning ticket → DLP Admin action → programme timeline entry.

#### Tab 3 — Triage Categorization

A donut chart showing how incidents distribute across six triage categories for the selected month. The distribution shifts dramatically between Month 1 (heavily false positive) and Month 12 (predominantly true positive).

---

### DLP Admin

**Best for:** Change management demonstrations, audit evidence reviews, programme planning.

**What to look at:**

**Enforcement Mode card** (first of four insight cards at the bottom)

Shows the current enforcement mode with colour coding:

| Mode | Colour | Months |
|---|---|---|
| Monitor Only | Cyan | 1–3 |
| Selective Block | Amber | 4–6 |
| Broad Block + UEBA | Rose | 7–8 |
| Broad Block | Rose | 9 |
| Broad Block + SOAR | Violet | 10 |
| Mature Operation | Emerald | 11–12 |

**Tuning Actions Timeline**

Shows every policy change made through the selected month. The header shows two counters — **Total Entries** and **From Triage**.

- Pre-defined programme entries have a standard blue circular month marker
- Analyst-generated entries (from the Triage Simulator) appear at the top with a cyan left border and a **"From your triage"** badge
- At Month 12, the timeline shows all 21 programme entries plus any analyst-generated entries from your session

**Top Noisy Policies chart** — the five highest-alert-volume policies, the primary tuning targets at any given month.

**Tuning Backlog Health chart** — open versus resolved tickets across all 12 months.

---

## Recommended Demo Sequences

### 10-minute CEO presentation

| Step | Action | What to say |
|---|---|---|
| 1 | Load app, stay on CEO view, Month 1 | "This is what DLP looks like on Day 1 — 8,500 alerts, 87% false positives. Our SOC team would burn out in weeks." |
| 2 | Drag slider to Month 4 | "First real exfiltration blocked — a departing engineer stopped uploading source code to personal GitHub. The investment paid for itself here." |
| 3 | Drag to Month 6 | "Halfway point — false positives down 75%, real threats visible, team not drowning." |
| 4 | Drag to Month 12 | "Goal achieved. 4% false positives. 71 threats caught. ₹65 Cr avoided." |
| 5 | Scroll to Before/After | Walk through the six rows — read each pair of numbers |
| 6 | Scroll to ROI Breakdown | "These are the six business outcomes the programme delivered." |

### 20-minute security team walkthrough

| Step | Action |
|---|---|
| 1 | CISO view → Swimlane at Month 1, Month 6, Month 12 — discuss each activation |
| 2 | SOC view → Live Logs at Month 1 — discuss the two false positive examples |
| 3 | SOC view → Triage Simulator — generate and triage three incidents with different verdicts |
| 4 | Open the FP-Pattern ticket modal — work through all 8 sections, click checklist, copy config |
| 5 | Mark as Applied → switch to DLP Admin → show the badge in the timeline |
| 6 | DLP Admin → Enforcement Mode card → drag from Month 1 to Month 12 watching mode change |

### 15-minute audit/compliance demonstration

| Step | Action |
|---|---|
| 1 | DLP Admin view → Month 12 → show timeline with 21 entries — this is the audit trail |
| 2 | Open any triage ticket modal — show the 4-stage approval workflow and pre-change checklist |
| 3 | CEO view → Audit-Ready Status tile — show it reading "Yes" from Month 11 |
| 4 | CEO view → Compliance Posture Score — 98% at Month 12 |
| 5 | DLP Admin timeline → Month 11 entry — "External audit completed — zero findings" |

---

## Frequently Asked Questions

**Does this connect to a real DLP system?**

No. All data is synthetic, generated entirely in the browser. It demonstrates the approach and workflow — it does not integrate with Forcepoint or any other DLP product.

**Is any data saved or transmitted?**

No. The application uses no cookies, no localStorage, and no server communication. Triage tickets generated during a session are lost when the page is closed or refreshed. Every session starts fresh.

**Can I use this offline?**

Partially. The application logic and all data are entirely self-contained. The fonts (Google Fonts) and charts (Chart.js) load from external CDNs and require an internet connection. Load the page once with internet access — the browser may cache resources for subsequent offline use.

**Can I present this directly from my laptop in a meeting?**

Yes. Load the page before the meeting so fonts and charts are cached. After that, no network connection is required during the presentation itself.

**Can I modify the data?**

Yes. Open the file in any text editor. The data objects are clearly labelled in the JavaScript section:
- `monthlyData` — all 12 months of programme metrics and narrative
- `tuningActions` — the 21 pre-defined timeline entries
- `fixedLogs` — the 96 log cards (8 per month)
- `verdictPlaybook` — the four Forcepoint change packages

**How do I host this on GitHub Pages?**

Push `dlp-maturity-prototype_application_poc.html` to your repository. Go to **Settings → Pages**, set the source branch, and access the file at:

```
https://yourusername.github.io/repository-name/dlp-maturity-prototype_application_poc.html
```

---

## File Structure

```
dlp-maturity-prototype_application_poc.html      ← The entire application
README.md                  ← This file
```

One file. Open it. Done.

---

## Technical Summary

| Property | Detail |
|---|---|
| Type | Single-file HTML application |
| Framework | None — vanilla HTML, CSS, JavaScript |
| External dependencies | Google Fonts (typography), Chart.js 4.4.0 (charts) |
| Backend | None |
| Data storage | None — all in-memory, resets on refresh |
| Build step | None required |
| File size | ~135 KB |

---

## Licence

Provided for educational and demonstration purposes. Synthetic data only. Does not represent any specific organisation's security posture or operational data.
