# Designing for Invisible UI

> A design research interactive guide for **headless AI agents** — AI systems that operate autonomously without a user-facing interface. Built as a **5-panel interactive stepper** (`index.html`) using the IBM Predictable Delivery design language, with a companion **UXR concept testing plan** (`uxr_plan.html`).

---

## Project Overview

| Property | Value |
|---|---|
| **Format** | 5-panel interactive stepper (`index.html`) + UXR plan (`uxr_plan.html`) |
| **Theme** | IBM Predictable Delivery — white + light blue-grey, IBM Plex Sans 300, `#0f62fe` accent |
| **Panels** | 0 Overview · 1 What & Why · 2 Characteristics · 3 Four Pillars · 4 Directions & Gallery |
| **Pillars explored** | 4 (Scope & Policy · Trace View · Contextual Chat · Agent Identity) |
| **Design directions** | 5 (derived from the four pillars) |
| **Navigation** | Fixed top nav + stepper progress bar; `goToStep(n)` JS-driven panel switching |
| **Flow label** | Recognition → Words → Agreement → Evidence |
| **Live URL** | https://jayakrishnakaimal.github.io/JK_Demo/ |

---

## Design Team

| Name | Role |
|---|---|
| Jayakrishna Kaimal | Design Manager |
| Divine Antony | Design Lead |
| Drron Sharma | UX Designer |
| Abhiram CS | UX Designer |
| Mahima Shrivastava | UX Designer |

---

## Page Structure — 5-Panel Stepper

Each panel is a full-viewport section (`.panel`). Only the active panel is visible; transitions are driven by `goToStep(n)`. A fixed **stepper bar** beneath the top nav shows the current step via filled indicator dots.

| Panel | Step Label | Content Summary |
|---|---|---|
| `panel-0` | Overview | KPI metrics, UX paradigm shifts grid, animated MacBook SVG illustration in right rail |
| `panel-1` | What & Why | Immune System analogy, VS toggle table, competitor positioning cards |
| `panel-2` | Key Characteristics | 4-tab switcher + live agent terminal demo in right rail |
| `panel-3` | Four Pillars | 4-pillar nav with interactive SVG architecture diagram + pillar-synced mock cards |
| `panel-4` | Directions & Gallery | 5 expandable direction cards + team grid + Design Gallery + direction micro-interactions in rail |

### Layout per panel
Every panel uses a **two-column split**:
- **Left column (`.main-col`)** — primary content, scrollable
- **Right column (`.rail-col`)** — persistent illustration, demo, or diagram

### Navigation
- **Top nav** — fixed 48px bar; brand label · "Today" tab
- **Stepper bar** — 5 step items with labels; active step filled blue, completed steps outlined
- **Back / Next buttons** — `btn-back` / `btn-forward` at bottom of each panel calling `goToStep(n)`

---

## Panel 0 — Overview

**Left column:**
- Condition label: `Likely condition · Designing for Invisible UI`
- Headline: *"Designing for Invisible UI"* (weight 300)
- Body: "When AI agents work autonomously in the background, the interface disappears. This research explores how designers can create systems built on trust, transparency, and control — without a visible UI driving the work."
- Signal row:
  - Badge: **"Not a UI problem"**
  - Text: "This is a system design condition the team can address."
- 3 KPI metric boxes:

| Metric | Value | Status |
|---|---|---|
| Pillars explored | 4 | ● Complete |
| Design directions | 5 | Derived from pillars |
| Team members | 5 | IBM Design · INI |

- Navigation chips → `goToStep(1–4)`: *What is headless AI?* · *Key characteristics* · *Four pillars* · *Design directions*
- Section heading: **"Rethinking the fundamentals of UX"** — 4 paradigm shifts:

| # | Dimension | Traditional framing | Shifts to |
|---|---|---|---|
| 01 | Control | Human controls every step | goal-setting |
| 02 | Timing | Synchronous loops — immediate feedback | async operation |
| 03 | Visibility | Everything on screen — invisible = anti-pattern | background execution |
| 04 | Design Focus | Arranging visual elements | orchestrating behaviour |

**Right rail:**
- Step marker: **01** / *"Canvas view"*
- Animated **MacBook SVG** illustration (see below)
- **"What is Invisible UI?"** — the agent acts, decides, and completes tasks in the background, surfacing only when a human decision is needed or something goes wrong.
- **Core Principles** list:
  1. **Event, not request** — agents wake from system signals, not user input
  2. **Always running** — continuous operation, no human trigger
  3. **Actions over answers** — output is a change in the world, not a chat response
  4. **Escalate at the edges** — humans only for high-stakes decisions
- Quote: *"The best interface is no interface — until the moment a human truly needs to be there."*

### MacBook SVG illustration
`viewBox="0 0 340 252"` — Inline SVG of a MacBook with a live canvas dashboard on screen.

**Screen layout (clipped to `x=18 y=14 w=304 h=192`):**

| Zone | Content |
|---|---|
| Top nav | Brand icon · Canvas tab (active blue) · Agentic trace tab · Policy & Permissions tab · two utility icons |
| Left — KPIs | Confidence score 95% · Fleet health 94% · Breach tags · Heartbeat waveform |
| Left — Canvas | Greeting "Hello Fiona, Good morning" · 4 query chip shapes |
| Right (x=197 divider) | Card 1: restart line (1200 / 87% / 2.1% · Approve / Escalate) |
| Right | Card 2: chronic alert card with Approve / Escalate |
| Right | Card 3: activity timeline with animated area chart and 3 event dots |

**Animated elements (SMIL `<animate>`):**

| Element | Animation | Duration |
|---|---|---|
| Brand icon inner circle | `opacity` 0.7 → 0.3 → 0.7 | 2.5s loop |
| Confidence value red bar | `opacity` 0.8 → 0.3 → 0.8 | 3s loop |
| Card 1 Approve button | `opacity` 1 → 0.75 → 1 | 2.8s loop |
| Card 2 Approve button | `opacity` 1 → 0.75 → 1 (begin 0.9s) | 2.8s loop |
| Timeline dot (yellow) | `r` 2.5 → 3.5 → 2.5 | 2s loop |
| Timeline dot (red) | `r` 2.5 → 3.5 → 2.5 (begin 0.7s) | 2s loop |
| Timeline dot (purple) | `r` 2.5 → 3.5 → 2.5 (begin 1.4s) | 2s loop |
| SVG root | CSS `mac-fadein` — fade + translateY(6px) | 0.6s once |

**CSS keyframes defined for the MacBook SVG:**

| Name | Effect |
|---|---|
| `mac-fadein` | Entrance — opacity 0→1, translateY 6px→0 |
| `mac-pulse` | Opacity 1 → 0.4 → 1 (defined but reserved) |
| `mac-dot` | `r` 2.5 → 3.5 → 2.5 (defined but reserved) |
| `mac-chip` | Opacity + translateX(-4px) entrance (defined but reserved) |

---

## Panel 1 — What & Why

**Left column:**
- Condition label: `Pattern named · What & Why`
- Heading: *"What are Headless AI Agents?"*
- Definition: AI systems operating autonomously without a user-facing interface; they work in the background, make decisions, and take actions without human initiation at every step.
- Quote: *"Before we commit to design — does the agent have a named user, measurable outcome, and evidence of a problem worth solving?"*
- **Immune System Analogy** (two-column):

| Immune System | Headless AI Agent |
|---|---|
| Monitors body functions continuously | Monitors systems continuously |
| Detects threats automatically | Detects anomalies automatically |
| Responds without conscious thought | Responds without user prompts |
| Escalates when overwhelmed | Escalates complex issues |
| Learns from past encounters | Learns from patterns |

- **VS Toggle table** — CSS switch toggles between *Traditional Chat AI* and *Headless AI Agent* columns:

| Dimension | Traditional Chat AI | Headless AI Agent |
|---|---|---|
| Trigger | Request/response loop; waits for user input | Event-driven; webhooks, cron, DB changes, queues |
| State | Conversational state across the session | Fresh context each invocation; no history |
| Output | Natural-language text | Actions — API calls, DB writes, notifications |
| Human role | Oversight and approval at every step | Autonomous continuous operation |

**Right rail:**
- Badge: **"Ready to use"**
- Step marker: **02** / *"Do this next"*
- Section: **"Who's building headless AI"**
- Competitor cards:

| Company | Tag | Summary |
|---|---|---|
| Salesforce Agentforce | `CRM` | Autonomous customer-service, sales follow-up, and case-routing agents triggered by CRM events |
| ServiceNow AI Agents | `ITSM` | Background agents that triage incidents, resolve known issues, and escalate when policy thresholds are breached |
| Microsoft Copilot Studio | `Enterprise` | Agents monitoring Microsoft 365 signals and completing workflows across Teams, Outlook, and Dynamics |
| Cisco ThousandEyes AI | `Network` | Observability agents detecting network degradation, correlating root causes, and auto-remediating without NOC intervention |

---

## Panel 2 — Key Characteristics

**Left column — 4-tab switcher:**

| Tab | Title | Real-world Example |
|---|---|---|
| `ev` | Event Driven | Network agent triggers on CPU > 85%, reroutes load, logs action |
| `au` | Autonomous | Security agent monitors 50+ apps, revokes stale permissions 24/7 |
| `ac` | Action Oriented | Invoice agent extracts PDF data, writes to DB, schedules payment |
| `co` | Context Building | Lead enrichment agent queries LinkedIn + Crunchbase from scratch |

Each tab reveals traits and a real-world example box.

**Tab: Event Driven**
- Triggered by system, not user
- Timing owned by the event
- Common sources: Stripe, GitHub, PagerDuty, Kafka, SQS, cron, CDC, IoT
- Design the event payload, not the form

**Tab: Autonomous**
- Runs without prompting
- Acts first, reports after
- Escalates at the edges
- Leaves a record, not a conversation

**Tab: Action Oriented**
- Output is a system change, not a message
- Actions have a risk gradient (read / write / destructive)
- Reversibility is a first-class design concern
- Notification is the agent's only voice

**Tab: Context Building**
- No persistent memory — fresh every run
- Sources: APIs, databases, events, graphs
- Context quality determines decision quality
- The triggering event is the root context

**Right rail — Live Agent Terminal Demo:**
- Dark terminal card (`#0a0a0a` background, green `#00ff88` text)
- Header: `network-agent v2.4.1` · Running badge · Pause · Replay buttons
- Three auto-running scenarios cycling automatically:
  1. **Scenario A** — Network anomaly detection and rerouting
  2. **Scenario B** — Permission outside scope → escalation
  3. **Scenario C** — Context failure with graceful degradation
- Each scenario streams log lines with typed animation, timestamped with `HH:MM:SS.cc`

---

## Panel 3 — Four Pillars

**Left column — 4-pillar nav:**

Pill button bar (`1 Scope & Policy` · `2 Trace View` · `3 Contextual Chat` · `4 Agent Identity`). Clicking a pill switches the pillar detail panel and syncs the rail mock card and architecture SVG.

### Pillar 1 — Scope & Policy
> *"Think of the Agent Policy Layer as the agent's immune system blueprint — established before it begins operating."*

- **Goal definitions** — What is the agent solving for?
- **Guardrails** — What is it never allowed to do?
- **Escalation rules** — When must it pause for human approval?
- **Scheduling** — Trigger-based, continuous, or on-demand

**Rail mock — Permission Matrix (`network-agent v2.4.1`):**

| Permission | Description | Badge |
|---|---|---|
| Read telemetry | Instana · Prometheus | `Auto` |
| Read CMDB | Asset inventory | `Auto` |
| Restart pods | Non-protected only | `Ask` |
| Modify BGP policy | Route changes | `Approval` |
| Cross-tenant QoS | Bandwidth shaping | `Approval` |

Design principle: *"The permission matrix is the product specification."*

---

### Pillar 2 — Trace View
> *"Think of traces as the agent's thought journal — they reveal how it happened, not just what happened."*

- Current state · Step-by-step trace · Decision nodes · Interrupt flags · Confidence indicators

**Rail mock — Live Trace (`invoice-processor · run #0091`):**

```
✓  Received invoice PDF          [Done]
✓  Extracted vendor + amount     [Done]
⚑  Auto-approve or escalate?    [Node]
⏸  Paused — awaiting input      [Blocked]
```

Design principle: *"Traces show timestamps, outcomes, and confidence."*

---

### Pillar 3 — Contextual Chat
> *"The agent pauses at critical decision points, requests human input, then proceeds while anchored to its trace."*

- Activated contextually · Edits to live run · Mid-run policy changes · Anchored to trace

**Rail mock — Chat exchange:**

```
Agent:  Anomalous vendor #4821 — $94,200 exceeds auto-approve threshold.
You:    Flag for review. Continue the other 31.
        ✓ Resumed · #4821 flagged · 31 invoices processing
```

Design principle: *"Chat is an emergency hatch used only when the agent is blocked."*

---

### Pillar 4 — Agent Identity
> *"Trust and accountability must answer who acted, what policy applied, when it ran, and why permission was granted."*

- Name, version, policy · Audit trail · Authorization provenance · Active session context

**Rail mock — Identity card (`compliance-monitor`):**

```
compliance-monitor v2.4.1  Policy: corp-access-v3   [Verified]
Auth: admin@corp.co  2025-07-10 · security-admin    [Traced]
Watching 52 sessions · Active since 09:00            [Running]
Audit log: 247 entries · Exportable · Immutable      [Sealed]
```

Design principle: *"Identity makes accountability visible."*

**Right rail (all pillars):**
- Badge: **"Agreement visible"**
- Step marker: **04** / *"Owner + follow-up"*
- Interactive SVG architecture diagram — always visible, shows the four pillars as labelled nodes with animated orbit rings, pulse rings, beam dots, and connector lines
- Pillar-synced mock card below switches to match the active pillar

---

## Panel 4 — Directions & Gallery

### Design Directions (5 expandable cards)

Each card expands on click via CSS `max-height` transition to reveal a real-world example.

| # | Direction | Summary |
|---|---|---|
| 01 | Design Logic, Not Layout | Focus on goals, constraints, permissions, and escalation paths — not visual arrangement |
| 02 | Build Interfaces That Flex and Deform | Ambient by default; detailed diagnostics surface only when needed |
| 03 | Proactive by Default, Verify at the Edges | Let agents handle routine tasks; involve humans only for irreversible/high-impact decisions |
| 04 | Make "Presence" the New Aesthetic | Subtle signals confirm the system is functioning — noticed only when attention is needed |
| 05 | Test for Trust, Not Just Usability | Metrics must reveal how much users trust the system, feel in control, and choose to delegate |

### Paradigm Card
> *"The designer's job is no longer to arrange elements — it is to orchestrate trust, transparency, and control."*
> — IBM Design Research · 2025

### Team Grid
Five avatar cards with gradient initials circles.

### Design Gallery
4-column grid (`ini1.png`–`ini4.png`). Each tile: hover overlay, tag pill, number badge, title + description.

| # | File | Title | Tag | Description |
|---|---|---|---|---|
| 1 | `ini1.png` | Canvas — Main Dashboard | Invisible UI | Ambient confidence · fleet health · activity timeline |
| 2 | `ini2.png` | Agentic Trace — Escalation View | Trace View | Decision reasoning · confidence trajectory · approval gates |
| 3 | `ini3.png` | Policy & Permissions — Studio | Scope & Policy | Composite score · permission matrix · posture radar |
| 4 | `ini4.png` | Policy & Permissions — Full Scroll | Scope & Policy | Extended categories · model knobs · posture projection |

**Lightbox** (`#gallery-lightbox`): dark cinema-style (`#111`), `min(92vw, 1400px)` width, prev/next nav, counter, keyboard support (Esc / ←→).

---

## Direction Micro-Interaction Rail (Panel 4)

The right rail contains a **"Live micro-interaction"** panel with 5 numbered tabs — one per design direction. Each tab activates an independent animated scene.

| Tab | Scene | What it demonstrates |
|---|---|---|
| **01** | Rule engine | 5 policy rules evaluated sequentially (idle → running → pass/fail), ending in a blocked-policy verdict. Click *↺ Replay* to re-run. |
| **02** | Flex & deform | Ambient fleet view (green pulse, KPIs) auto-expands into an alert card after 1.8 s. Approve resolves and collapses back to ambient. |
| **03** | Proactive / verify | Thinking dots while agent "prepares", then a proposed action card (action / impact / rollback). Approve → green done state. Reject → restarts. |
| **04** | Presence aesthetic | Dark `network-intelligence` UI with expanding pulse ring, cycling status text, uptime/agents/escalation KPIs, animated activity bars (update every 1.8 s). |
| **05** | Trust meter | 5 autonomy levels (Supervised → Autonomous) each updating the trust bar fill, delegation rate, overrides/day, comprehension, and a contextual insight. |

**Rule engine evaluation results:**

| Rule | Result | Badge |
|---|---|---|
| Check: anomaly score ≥ 0.80 | Pass | `PASS` |
| Guardrail: cross-tenant scope? | Fail | `NO` |
| Permission: reroute_traffic | Pass | `APPROVED` |
| Escalation: impact > medium? | Fail | `NO` |
| Schedule: run window active? | Pass | `ACTIVE` |

Final verdict: *"⛔ Policy blocked — 2 guardrails failed. Escalating."*

**Trust meter levels:**

| Level | Bar fill | Delegation rate | Overrides/day | Comprehension | Insight |
|---|---|---|---|---|---|
| Supervised | 10% | 12% | 18 | Low | User reviews every action — trust is not yet established. |
| Assisted | 30% | 34% | 11 | Developing | User accepts suggestions but still validates each step. |
| Delegated | 58% | 67% | 4 | Moderate | Agent handles full workflows. User audits the summary. |
| Collaborative | 74% | 79% | 2 | High | Human handles judgement calls; agent owns execution. |
| Autonomous | 96% | 97% | 0 | Full | Full autonomy granted. UI serves as flight recorder only. |

Rail order (top → bottom):
1. `Condition restored` badge
2. **05** / *"Evidence in work"* step marker
3. Live micro-interaction panel (5 tabs)
4. Blockquote — *"Designing for invisible UI is a paradigm shift…"*

---

## Dark Footer

Background: `#161616`

| Element | Content |
|---|---|
| Brand | `Headless AI` |
| Flow breadcrumb | Recognition → Words → Agreement → Evidence |
| Credit | Designed & developed by **JK** with **Bob** |
| Action | "Start again" button → `goToStep(0)` |

---

## UXR Plan — `uxr_plan.html`

A companion **concept testing plan** for validating the three novel UI surfaces (Canvas, Agentic Trace, Policy & Permissions) with 12 participants across three segments. Styled with IBM Carbon Design System tokens (`--cds-*`) and BEM class naming (`bx--`).

### Header navigation

| Link | Destination |
|---|---|
| IBM Network Intelligence (brand) | `#top` — scrolls to page header |
| Research | `#top` — current active page |
| Headless *(right corner)* | `index.html` — navigates to the main interactive guide |

### Sections (11 total)

| # | Section | Component pattern |
|---|---|---|
| 01 | Background & context | Screen card grid (5 screens) |
| 02 | Research objectives | 6-card grid — RO-1 through RO-6 |
| 03 | Key research questions | 2-col KRQ grid — 4 clusters, ordered lists |
| 04 | Participant criteria | Structured list — 3 segments + screener |
| 05 | Tasks & discussion guide | Interactive accordion — 5 tasks with scenario / task / probes |
| 06 | Success metrics | 6-cell metric card grid with large value display |
| 07 | Study timeline | Progress steps — 5 weeks, green ✓ complete, blue ◉ in-progress |
| 08 | Analysis framework | Dark-header code table — 6 analysis phases |
| 09 | Discussion guide outline | Guide outline — 7 time-keyed rows |
| 10 | Risks & mitigations | Code table — 6 risks with likelihood/impact/mitigation |
| 11 | Deliverables | Structured list — 7 deliverables with status tags |

### Study at a glance

| Property | Value |
|---|---|
| Study type | Moderated concept test, remote |
| Session length | 60 min + 10 min debrief |
| Participants | n = 12 (3 segments) |
| Timeline | 6 weeks |
| Screens tested | 5 (Canvas · Agentic Trace × 2 · Policy Studio · Digital Twin) |
| Primary tool | Zoom + Maze hi-fi prototype |

### Research objectives summary

| ID | Objective | Primary tag |
|---|---|---|
| RO-1 | Mental model alignment | Mental model |
| RO-2 | Trust & confidence signals | Trust |
| RO-3 | Oversight & control | Control |
| RO-4 | Transparency of reasoning | Transparency |
| RO-5 | Permission & policy usability | Policy |
| RO-6 | Pre-flight & digital twin value | Simulation |

### Success metrics

| Metric | Threshold |
|---|---|
| Task completion rate | ≥ 80% |
| SEQ score (trust tasks) | ≥ 5.5 / 7 |
| Mental model alignment | ≥ 70% |
| Policy configuration accuracy | ≥ 75% |
| Transparency legibility | ≥ 65% |
| Pre-flight approval intent | ≥ 60% |

---

## Design System — Token Reference

| Token | Value | Usage |
|---|---|---|
| `--blue` | `#0f62fe` | Primary accent, active states, links |
| `--blue-h` | `#0043ce` | Hover state for blue elements |
| `--blue-lt` | `rgba(15,98,254,.08)` | Pill backgrounds, highlight fills |
| `--green` | `#24a148` | Success badges, confirmed states |
| `--green-lt` | `#d4edda` | Auto badge background |
| `--amber` | `#f1c21b` | Warning nodes in trace |
| `--red` | `#da1e28` | Blocked/error states |
| `--text` | `#161616` | Primary text |
| `--sub` | `#525252` | Secondary / body copy |
| `--muted` | `#8d8d8d` | Labels, metadata |
| `--border` | `#e0e0e0` | All dividers and card borders |
| `--bg` | `#ffffff` | Page background |
| `--surface` | `#f4f4f4` | Section backgrounds, example boxes |
| `--rail` | `#f0f4f8` | Light blue-grey right rail surface |
| `--signal` | `#e8f5d0` | Soft green signal / success tint |

### Carbon Design Tokens (`uxr_plan.html`)

| Token | Value | Usage |
|---|---|---|
| `--cds-background` | `#ffffff` | Page background |
| `--cds-background-inverse` | `#161616` | Header, footer, dark surfaces |
| `--cds-layer-01` | `#f4f4f4` | Section layer backgrounds |
| `--cds-interactive` | `#0f62fe` | Links, active states, eyebrow labels |
| `--cds-text-primary` | `#161616` | Primary text |
| `--cds-text-secondary` | `#525252` | Body copy, table cells |
| `--cds-border-subtle-01` | `#e0e0e0` | Card and table borders |

### Typography
- **Font:** IBM Plex Sans (300 · 400 · 600 · 700) via Google Fonts
- **Large headings:** `font-weight: 300`, `clamp()` — ultra-thin IBM style
- **Blockquotes:** `font-weight: 300`, italic, `4px` solid blue left border
- **Section labels:** `font-size: .72rem`, weight 700, uppercase, letter-spacing `.1em`, blue

---

## JavaScript Behaviours

| Function | Purpose |
|---|---|
| `goToStep(n)` | Activates panel `n`, updates stepper dots, breadcrumb, resets char tabs, triggers agent demo on panel 2, triggers flex/deform alert on panel 4 |
| `toggleVS(sw)` | Switches panel 1 comparison table between Traditional and Headless columns |
| `setAutoLevel(n)` | Selects autonomy-spectrum level, updates title/body/impl with animation |
| `selectAction(type, el)` | Activates action-type card, populates design-consideration checklist |
| `selectCtx(type, el)` | Activates context-source node, populates title/description/chips/note |
| `ts()` | Returns current time as `HH:MM:SS.cc` |
| `setStatus(txt, pulse)` | Updates live-agent status text and pulse class |
| `addLine(entry)` | Appends a timestamped tagged log line to the agent terminal |
| `runNext()` | Processes next event in agent sequence, schedules following event |
| `agentPause()` | Pauses / resumes agent sequence, updates button icon |
| `agentReplay(auto)` | Clears log, starts next agent sequence |
| `agentStart()` | Resets and starts agent demo from waiting state |
| `paSelect(el)` | Activates pillar card, highlights connector line, pulses core ring, syncs nav |
| `openLightbox(idx)` | Opens gallery lightbox for item `idx`, locks scroll |
| `closeLightbox()` | Closes gallery lightbox, restores scroll |
| `closeLightboxIfBackdrop(e)` | Closes lightbox when backdrop is clicked |
| `lbNavigate(dir)` | Moves forward/back through gallery items |
| `renderLightbox()` | Updates lightbox title/tag/caption/counter/image/nav visibility |
| `dmiRunRules()` | Resets and sequentially evaluates 5 policy rules, shows verdict |
| `dmiReplay()` | Re-runs rule engine animation |
| `dfdTriggerAlert()` | Shows ambient state, auto-expands CPU alert after 1.8 s |
| `dfdApprove()` | Resolves alert as approved, returns to ambient after 1.4 s |
| `dfdDismiss()` | Hides expanded alert, restores healthy ambient state |
| `dpvReset()` | Resets proactive-verify flow to thinking state, reveals action card after 2.2 s |
| `dpvApprove()` | Shows completion state |
| `dpvReject()` | Returns to thinking state, re-presents action card after 2.2 s |
| `dprInit()` | Generates activity bars, starts bar randomization (1.8 s) and label cycling (2.4 s) |
| `dtrSet(lv, el)` | Selects autonomy level, updates trust bar fill, metrics, and insight |

---

## CSS Keyframe Animations

| Name | Effect | Used in |
|---|---|---|
| `mac-fadein` | Opacity 0→1 + translateY(6px)→0 | MacBook SVG root entrance |
| `mac-pulse` | Opacity 1 → 0.4 → 1 | MacBook SVG (defined, reserved) |
| `mac-dot` | `r` 2.5 → 3.5 → 2.5 | MacBook SVG (defined, reserved) |
| `mac-chip` | Opacity + translateX(-4px) entrance | MacBook SVG (defined, reserved) |
| `ad-fadein` | Fade + translateY shift into view | Live agent log rows |
| `ad-pulse` | Scale/opacity pulse | Agent status indicator |
| `dreRowPulse` | Opacity 0.7 → 1 alternate | Rule engine rows during evaluation |
| `dfdPulse` | Box-shadow pulse (green) | Flex/deform ambient dot |
| `dfdExpand` | Opacity 0→1 + translateY(-6px)→0 | Alert / summary card entrance |
| `dpvBounce` | Scale 0.5 → 1 → 0.5 with opacity | Proactive-verify thinking dots |
| `dprRing` | Scale 1 → 2.4, opacity 0.8 → 0 | Presence aesthetic pulse ring |
| `fadein` | General opacity fade-in | Panel/content elements |
| `pa-spin` | Rotates dashed orbit stroke | Pillar architecture orbit rings |
| `pa-ring` | Expand + fade pulse rings from core | Pillar architecture core |
| `pa-core-breath` | Expand/contract core ring + stroke opacity | Pillar architecture core |
| `pa-orb-blink` | Opacity pulse on status orbs | Pillar architecture core orbs |
| `pa-orbit-travel` | Moves traveller along orbit path | Pillar architecture beam dots |

---

## `headless.html` — Headless AI Dashboard

> A fully interactive, pixel-perfect prototype of a **Headless AI Operations Dashboard** built from design screenshots. Full-screen layout with a frosted-glass body gradient and three main tab views.

### Overview

| Property | Value |
|---|---|
| **File** | `headless.html` |
| **Theme** | Frosted glass over blue-grey gradient body; white panels with `backdrop-filter: blur(12px)` |
| **Body gradient** | `linear-gradient(160deg, #f8fafd → #f3f6fb → #ddeaf5 → #b8d4e8 → #9ec8e0)` fixed |
| **Font** | `-apple-system, "Segoe UI", system-ui, sans-serif`; `-webkit-font-smoothing: antialiased` |
| **Tabs** | Canvas · Agentic Trace · Policy & Permissions |
| **Right panel** | Visible on Canvas tab only; hidden on Agentic Trace + Policy tabs |
| **Live URL** | https://jayakrishnakaimal.github.io/JK_Demo/headless.html |

---

### Top Navigation

| Element | Detail |
|---|---|
| Logo | Hub-and-spoke SVG on white circle with blue border |
| Dropdown | Japan region selector |
| Tab bar | Canvas · Agentic Trace · Policy & Permissions — `switchTab()` driven |
| Right icons | Person icon · **Globe button** (`.nav-icon-btn--globe`) |

#### Globe button (settings)
- 36×36px, gradient background `#eff6ff → #dbeafe`, blue border `#93c5fd`
- SVG: radial-gradient filled sphere (`#dbeafe → #93c5fd`), meridian/latitude paths, specular dot
- Hover: scale 1.08, glow ring `rgba(59,130,246,0.18)`, darker border
- Active (`.settings-active`): solid blue gradient `#2563eb → #1d4ed8`, white SVG paths
- Toggles the **Global Network Map** side panel (`.settings-panel`)

---

### Stats Bar

| Stat | Icon | Value | Style |
|---|---|---|---|
| Confidence score | Stick-figure SVG | **95%** | `font-weight:300`, dark green `#1a6334` |
| Agent fleet health | ECG sparkline SVG | **94%** | same |
| Badges | Auto-resolved · Escalation · Fix failed | — | coloured pill badges |

---

### Global Network Map Panel (`.settings-panel`)

Opens as a 500px right-hand slide-in panel when the globe button is clicked. Contains the orthographic 3D globe + anomaly detection list.

#### 3D Orthographic Globe (`#gmapCanvas`, 300px tall)

The globe renderer replaced a flat equirectangular map. It is a fully custom canvas renderer:

| Feature | Detail |
|---|---|
| **Projection** | Orthographic — `geoToOrth(lon, lat, R, cx, cy)` returns `[x, y, dot]`; `dot < 0` = behind globe (hidden) |
| **Auto-spin** | `globeLon += 0.10°/frame` (`GLOBE_SPIN_DEG`) — pauses on mouse drag, toggleable by double-click |
| **Star field** | 90 randomised `{x, y, r, a}` points drawn each frame behind globe |
| **Atmosphere** | Radial gradient halo `rgba(96,165,250,0.18 → 0)` at `R × 1.18` |
| **Ocean sphere** | Radial gradient: `#1e4d8c → #0d2d5e → #060f1e` centred off-axis for depth |
| **Clip** | `ctx.clip()` to globe disc before drawing graticule + continents |
| **Graticule** | Meridians every 30° + parallels every 30° in `rgba(96,165,250,0.08)`; equator in `rgba(96,165,250,0.22)` |
| **Continents** | `COAST_POLYS` lon/lat arrays projected via `geoToOrth`, filled `#1e3d6e`, stroked `rgba(120,180,255,0.5)` |
| **Gloss** | Radial gradient overlay upper-left `rgba(255,255,255,0.14 → 0)` for 3D sheen |
| **Rim** | 2px stroke `rgba(10,20,40,0.55)` around globe edge |
| **Edges** | Great-circle arcs via 40-sample Slerp (`drawArc()`); `Math.acos` clamped to `[-1,1]` to prevent NaN |
| **Nodes** | Dots only on visible hemisphere (`dot > 0`); labels when `dot > 0.25` |
| **Packets** | Animated dot along straight lon/lat lerp (not true great-circle) |
| **Drag** | `mousemove` delta → `globeLon += dx * 0.4`, `globeLat -= dy * 0.4` (clamped ±85°) |
| **Zoom** | Wheel / `+`/`-` buttons adjust `globeZoom` (`0.5–3`); reset (`⌂`) restores `globeLon=20, globeLat=15, globeZoom=1` |

#### Globe state variables

| Variable | Default | Purpose |
|---|---|---|
| `globeLon` | `20` | Camera centre longitude |
| `globeLat` | `15` | Camera centre latitude |
| `globeZoom` | `1.0` | Radius multiplier |
| `_globeSpinOn` | `true` | Auto-spin toggle |
| `GLOBE_SPIN_DEG` | `0.10` | Degrees per frame |

#### Panel header
- Title: globe SVG icon + "Global Network Map"
- **Maximize button removed** — only the close button (✕) remains
- Region filter chips: All · APAC · EMEA · AMER · Japan

#### Anomaly Detection list
- Below the globe + map legend
- Pulsing red badge count (`anomalyBadge`)
- "Scan now" button (`runAnomalyScan()`) with spinning icon
- Draggable anomaly items drop onto canvas

---

### Canvas Tab

- Full-viewport gradient canvas area with floating ambient orbs + mouse-tracking glow
- Greeting text: *"Good morning, Jayakrishna"* with agent status line
- 3 quick-action buttons that open an interactive inline chart panel (`#qaPanel`):
  - **"What's causing the latency spike?"** → `handleQuickAction('latency', this)`
  - **"Show me cluster C4 status"** → `handleQuickAction('c4', this)`
  - **"Run root cause analysis"** → `handleQuickAction('rca', this)`
- **Right panel** (always visible on Canvas): three draggable action cards + Activity Timeline
  - Card 1 (`data-card="restart"`): Restart line card — P1, approve/escalate
  - Card 2 (`data-card="chronic"`): CHRONIC TVM-EDGE-04 — P2, 4th failure
  - Card 3 (`data-card="timeline"`): Activity Timeline — draggable with 6h event summary
  - All three cards have drag-hint label + 4-dot handle icon

#### Quick-Action Panel (`#qaPanel`)

Slides up over the canvas viewport (`position:absolute; inset:15px` when `.visible`) with frosted glass background (`rgba(248,250,253,0.97)` + `backdrop-filter:blur(16px)`).

**Layout:** Left sidebar (232px, `.qa-insight`) of coloured KPI cards + insight note · Right chart area (flex:1)

#### qa-insight sidebar design
- **Background:** `linear-gradient(170deg, #f0f7ff → #f5f3ff → #fdf4ff)` — pale blue-violet-pink
- **Top accent stripe** (3px): `linear-gradient(90deg, #3b82f6 → #8b5cf6 → #ec4899)` — blue to violet to pink
- **Inner wrapper** `.qa-insight-inner` — `padding:16px 16px 18px`, `gap:12px`
- **Section title** `.qa-insight-section-title` — 9px uppercase, `#9ca3af`

Each KPI card (`.qa-insight-kpi`) has:
- Colour variant class (`kpi-red` / `kpi-amber` / `kpi-green` / `kpi-blue` / `kpi-violet`) setting `--kpi-accent` CSS var, matching border, and diagonal gradient background
- 3px left accent bar (`::before` pseudo, `var(--kpi-accent)`)
- Mini SVG icon + bold status badge row (`.qa-insight-kpi-icon`)
- Label (10px, uppercase) + large value (26px, weight 300)
- **Trend micro-badge** (`.qa-insight-trend.up/.down/.ok`) — coloured pill below the value

| Colour variant | CSS class | Accent | Border | Used for |
|---|---|---|---|---|
| Red | `kpi-red` | `#ef4444` | `#fee2e2` | Peak / high-alert values |
| Amber | `kpi-amber` | `#f59e0b` | `#fef3c7` | Warning / average values |
| Green | `kpi-green` | `#10b981` | `#d1fae5` | Healthy / SLA / confidence |
| Blue | `kpi-blue` | `#3b82f6` | `#dbeafe` | Scan / informational |
| Violet | `kpi-violet` | `#8b5cf6` | `#ede9fe` | Aggregate / avg health |

**Insight note** (`.qa-insight-note`): glass card, violet left border `#6366f1`, `backdrop-filter:blur(4px)`

| Button | Title | Tag | Chart type | KPI cards |
|---|---|---|---|---|
| Latency spike | Latency Analysis | Live · 5s refresh | Multi-line time-series (30 min) | Peak 284ms (red) · Avg 142ms (amber) · SLA 200ms (green) |
| Cluster C4 | Cluster C4 Status | 12 / 13 Healthy | Horizontal bar chart (13 nodes) | 12 healthy (green) · 1 degraded (amber) · Avg 97% (violet) |
| Root cause | Root Cause Analysis | 72h window | Stacked area chart (72h) | 4 820 events (blue) · 3 root causes (amber) · 91% confidence (green) |

**Chart interactions:**
- All charts: hover tooltip (`#qaTooltip` fixed dark pill) showing values at cursor position
- **Latency chart:** 3 coloured lines (Agent-04 red, Agent-06 amber, Agent-02 blue), SLA dashed green line at 200ms, vertical crosshair on hover (`#qaCross`)
- **C4 bar chart:** 13 horizontal bars with background track, red dashed minimum threshold at 80%, per-bar hover with name + health % + status
- **RCA stacked area:** 3 stacked areas (Hardware red, Config Drift amber, Load Spike blue) over 13 × 6h steps, per-column hover with breakdown values
- Close button (✕) calls `closeQaPanel()` — hides panel + clears active button state

#### Drag-and-Drop Action Cards → Canvas (`#dropPanel`)

All three right-panel cards (`restart`, `chronic`, `timeline`) are draggable onto the canvas viewport. While dragging, the canvas shows a **pulsing blue dashed border** ("Drop here to expand"). On drop, `#dropPanel` appears (`position:absolute; inset:15px`, scale-in transition) with four sections:

| Section | Content |
|---|---|
| **Key Metrics** | 4 large thin-number KPI cards coloured by status |
| **Classification** | Coloured pill tags (fault type, pattern, escalation path) |
| **Agent Reasoning Trace** | 5 numbered steps with full narrative |
| **Confidence Breakdown** | Animated bars fill from 0% on drop, colour-coded per factor |

| Card | Severity | Metrics | Actions |
|---|---|---|---|
| `restart` | P1 | Blast radius 1 200 subs · Confidence 87% · Recovery < 8 min | Approve restart · Escalate to L2 |
| `chronic` | P2 | 4 failures this week · Avg interval 3.1h · RCA confidence 91% | Approve replace · Page on-call |
| `timeline` | INFO | 40 events · 33 auto-resolved · 4 escalated · 3 active | Export report · Page on-call |

#### AI Voice / Chat Panel (`#aiPanel`) — `10.png`

Opened via the **gradient mic trigger button** (bottom-right corner of canvas, `position:absolute; bottom:44px; right:28px`).

**Idle state** (matches `10.png` exactly):
- Blue-gradient background (`linear-gradient(160deg, #eef4fb, #ddeaf5, #c8dff0)`)
- Centred blue-purple gradient sphere (`130px`) inside a white ring (`170px`) with ambient radial glow
- *"Ask me anything"* (22px, weight 300) · *"Click on the mic to speak"* (13px muted)
- 5 suggestion chips in **quick-btn style** (white frosted, `border-radius:4px`, blue hover lift)

**Listening state** (`.listening` class on `#aiPanel`):
- Orb shows two staggered ripple rings (CSS `@keyframes ripple`)
- 5-bar waveform bounces below the orb (`@keyframes dotBounce`)
- Ambient glow pulses faster (1.2s vs 3s idle)
- Title → *"Listening…"* / subtitle → *"Speak now"*
- Mic button pulses (`@keyframes voicePulse`)
- Uses **Web Speech API** (`SpeechRecognition`) — falls back to demo simulation on unsupported browsers

**Chat mode** (`.has-chat` class):
- Orb compacts to top; chat messages fill centre (`flex:1`, `overflow-y:auto`)
- Suggestion chips hidden
- User bubbles: white frosted glass, right-aligned, `F` avatar (blue circle)
- Agent bubbles: blue-tinted frosted glass, left-aligned, `AI` avatar (gradient circle)
- Typing indicator: 3 bouncing dots (`@keyframes typeDot`) before response
- Responses include coloured **KPI chips** (`green`/`amber`/`red`/default indigo)

**5 canned responses (keyword-matched):**

| Keyword | Response topic |
|---|---|
| `latency` | TVM-EDGE-04 port 4/2 spike — peak 284ms, confidence 87%, recovery < 8 min |
| `c4` / `cluster` | Cluster C4 — 12/13 healthy, Agent-06 soft breach 61% |
| `root cause` / `rca` | 72h analysis — hardware 47%, config drift 31%, load spike 22% |
| `case` / `week` | 40 cases — 33 auto-resolved, 4 escalated, 3 active |
| `confidence` / `score` / `health` | 95% confidence, 94% fleet health, SLA 80% threshold |
| *(default)* | General telemetry status + TVM-EDGE-04 note |

---

### Agentic Trace Tab (`02.png`)

| Element | Detail |
|---|---|
| Stats row | 100/120 cases · 10 escalations · 82% auto-resolve · 6 pending |
| Search | Live filter by case name/ID |
| Filters | 4 dropdowns: Status · Agent · Priority · Time range |
| Cases table | 10 rows — name, case ID, tag, agent, priority badge, outcome badge, timestamp |
| Row interaction | Click → opens full-page **Case Detail** view (replaces old drawer) |
| `Esc` / back arrow | `closeCaseDetail()` returns to trace list |

**Cases data** (10 rows):

| ID | Name | Agent | Priority | Outcome |
|---|---|---|---|---|
| C-2840 | BGP-flap dampened | Route Guard Agent | P1 | Auto resolved |
| C-2839 | Memory leak contained | Memory Sentinel | P2 | Auto resolved |
| C-2838 | Cert expiry pre-empted | Cert Watcher | P2 | Auto resolved |
| C-2837 | Disk saturation halted | Storage Agent | P1 | Escalation |
| C-2836 | Latency spike rerouted | Traffic Agent | P2 | Auto resolved |
| C-2835 | Node cordon applied | Infra Agent | P1 | Auto resolved |
| C-2834 | Pod OOMKill recovered | Memory Sentinel | P2 | Fix failed |
| C-2833 | DNS resolution fixed | Net Agent | P3 | Auto resolved |
| C-2832 | TLS handshake retried | Cert Watcher | P3 | Auto resolved |
| C-2831 | CPU throttle adjusted | Perf Agent | P2 | Escalation |

---

### Case Detail Page (`#caseDetailPage`) — `11.png` · `12.png`

Full-page overlay that slides over the Agentic Trace tab (`position:absolute; inset:0` inside `#tab-agentic`) so the top nav remains visible. Opened by `openCaseDetail(idx)`, closed by `closeCaseDetail()`.

**Layout:** `#cdMain` (flex:1, scrollable) + `#cdSidebar` (340px fixed right)

#### Main panel — left column

| Section | Detail |
|---|---|
| **Back button** | `← Back to cases` — calls `closeCaseDetail()` |
| **Case header** | Case name (h1, 22px/600) · outcome badge · case ID + timestamp |
| **Confidence chart** | SVG with gradient area fill + animated line draw-in (0.9s cubic-bezier). Clip-path `<rect>` animates `width: 0 → 420` on open. Y-axis 50–100%, 10 data points per case |
| **Approval gates bar** | `#cdGatesBar` animates width 0 → % of gates passed (120ms delay, 0.5s transition). Label shows "N / M gates passed" |
| **Gate ledger row** | Single `cd-ledger-row` card: green (`#f0fdf4` / `#bbf7d0`) or red-tinted (`#fef2f2` / `#fecaca`) depending on `ledgerPass`. Icon circle: green `#22c55e` or red `#ef4444`. |
| **Decision reasoning** | 3–5 numbered steps (`cd-reason-step`), each with icon, title, and narrative text drawn from `caseDetailData` |
| **Impact badge** | Amber pill: "~1 200 users" or "~600 users" etc. |

#### Sidebar — right column (340px)

**Escalation / Action card** (`.cd-side-card`) — matches `12.png` exactly:

| Property | Value |
|---|---|
| Background | `#fdfaf0` (warm cream) |
| Border | `1px solid #dbb84a` (gold) |
| Border radius | `8px` |
| Title | `15px / 600`, `#1a1a1a` |
| Time | `13px / #9ca3af`, right-aligned, baseline-aligned with title |
| Case ID | `13px / #6b7280` below title row |
| Divider | `<hr class="cd-side-divider">` — `1px solid #ebe3c0`, `margin:14px 0 16px` |
| Name | `17px / 400 / #111827` (the case title) |
| Sub-line | `13px / #d97706` amber — expires · tier · confidence |

**Action buttons** (`.cd-side-btns`) — always visible, labels set by `openCaseDetail` based on case outcome:

| Outcome | Approve button | Deny button |
|---|---|---|
| Escalation (`showApprove:true`) | **Approve** | **Deny** |
| Auto resolved | **Mark reviewed** | **Reopen** |
| Fix failed | **Retry fix** | **Escalate** |
| Other | **Approve** | **Dismiss** |

**Button micro-interactions** (ripple + spinner → success):
- **Click** → `_cdRipple()` spawns a `.cd-ripple` span at click coordinates (`cdRipple` animation, 0.55s ease-out, scale × 4)
- **Loading state** → spinner (`btnSpinRot` 0.7s) + "Processing…"; opposite button dims to `opacity:0.4` and disabled
- **Approve success** → green `#16a34a` + "✓ Approvedd" + `successPulse` scale animation → toast → `closeCaseDetail()` 1s later
- **Deny dismissed** → grey `#f9fafb / #6b7280` + "dismissed" text → toast → `closeCaseDetail()` 900ms later

**Inline AI chat** (`.cd-chat-box`):
- Compact chat widget below the action card; user `F` avatar + agent `AI` avatar
- 4 suggestion chips (canned questions about the case)
- Keyword-matched responses from `cdChatResponses` object (5 keys + default)
- Typing indicator (`.cd-chat-typing`) with 3 bouncing dots before agent reply

#### `caseDetailData` (10 entries, mirrors `casesData`)

Each entry provides: `sideTitle`, `sideTime`, `sideSub`, `showApprove`, `confidence[]` (10 data-points), `reasoningSteps[]`, `gatesPassed`, `gatesTotal`, `gateRule`, `gateRuleId`, `ledgerPass`, `ledgerName`

---

### Policy & Permissions Tab (`04.png` · `06.png`)

#### Header
- **Operating mode · Balance** — description text
- Buttons: Edit operating mode · Change operating mode

#### Composite Score row
- Donut chart: **85/100** in `#2563eb`
- Summary text explaining composite score
- Trend sparkline (Jan–Jul, Jun highlighted blue)

#### Left panel — Studio / Configuration Testing tabs

**Active tab style:** Blue border box (`border-color: #2563eb`), `border-bottom-color: transparent`

**Studio tab** — flat permission list (no card wrapper):

| Section | Permission | Badge |
|---|---|---|
| Observability | Read telemetry | Auto (green) |
| Observability | Read CMDB / topology | Auto (green) |
| Remediation | Restart pods | Ask (blue) |
| Remediation | Cordon nodes | Ask (blue) |
| Network | Modify BGP policies | Approval (grey) |
| Network | QoS shaping | Approval (grey) |
| Data | Cross-tenant correlation | Approval (grey) |

Badge cycle on click: `Auto → Ask → Approval → Auto`

**Configuration Testing tab** (`09.png`) — Digital Twin Simulator:

| Element | Detail |
|---|---|
| Layout | `ct-left: 600px` fixed · `ct-right: flex:1` |
| Left | 5 scenario cards (Fiber cut, Power surge, BGP storm, DDoS mitigation, Rolling upgrade) |
| Right | Network topology SVG (7 nodes + edges) · Animated result panel |
| Scenario card click | Runs `runConfigTest(scenario)` — spinner → `renderCTResult()` with metric count-up |
| Metrics | Recovery time · Agent decisions · Services protected · Confidence score |
| pp-right visibility | Hidden when Configuration Testing tab is active (`switchPPTab` hides it) |

#### Right panel — `.pp-right`

| Element | Style |
|---|---|
| Panel width | `340px` |
| Background | `#ffffff` solid white |
| Padding | `32px` |
| Title "Model & remediation knobs" | `18px`, `font-weight:500`, `color:#111827` |
| Knob rows | `padding: 5px 0`, `border-bottom: 1px solid #f3f4f6` |
| Knob label | `14px`, `#374151`, `font-weight:400` |
| Knob number (80, 12, 2) | `28px`, `font-weight:300`, `color:#166534` dark green |
| `%` unit | Same `28px` green (`.pp-knob-unit`) |
| `acts/min` / `level` unit | `13px` grey `#6b7280` (`.pp-knob-unit-word`) |
| Divider `<hr>` | `1px solid #f0f1f3`, `margin:0` |
| "Posture Projection" | `16px`, `font-weight:400`, `padding-top:10px` |
| "Under balanced" | `13px`, `#6b7280`, `margin-bottom:0` |

**Knob values:**
```
Model confidence gate    80%
Action rate limit        12  acts/min
Blast radius cap          2  level
```

#### Radar chart — `initRadar()` (JS-drawn SVG)

| Property | Value |
|---|---|
| Element | `<svg id="radarSvg">` drawn by `initRadar()` on `DOMContentLoaded` |
| Centre | `cx=160, cy=195` |
| Max radius | `R=115` |
| Axes | 8 axes at 45° steps; `pt(v, angleDeg)` formula |
| Grid rings | 4 concentric octagons at 25/50/75/100% |
| Axis labels | `10.5px`, `#9ca3af` |

**8 axes (clockwise from top):**
Risk Exposure · Time to remediate · Tool calls / task · Autonomy · Human review load · Reversibility · Blast radius · Compliance

**3 series:**

| Key | Name | Colour | Fill | Dots |
|---|---|---|---|---|
| `blue` | Balanced | `#60a5fa` | `rgba(147,197,253,0.28)` | ✓ |
| `yellow` | Baseline | `#f59e0b` | `rgba(253,211,77,0.38)` | — |
| `red` | Reversibility | `#f87171` | `rgba(252,165,165,0.33)` | ✓ |

**Interactions:**
- **Polygon hover** → hovered series brightens (`stroke-width` 1.6→2.4, full fill opacity), others dim to `opacity:0.25`
- **Mousemove** → floating dark tooltip: series name + nearest axis label + `%` value (`position:fixed`)
- **Legend click** → toggles series visibility (polygon + dots fade; legend item → `opacity:0.35`)
- **Mouse leave SVG** → tooltip hides

#### Note text
> "More autonomy and tool usage means less compliance and blast-radius containment. The compliance-heavy profile gains safety but sacrifices speed and independence."

---

### QA Chart Micro-Interactions (5 effects + skeleton loader)

All 6 layers are wired through the `handleQuickAction` wrapper pattern (overrides the original function via `_origHandleQuickAction`).

#### Skeleton loader (effect 6 — fires first)
When a quick-action button is clicked, a `.qa-skeleton` overlay is injected into `#qaChartWrap` **before** the chart renders:
- 20 grey bars (`#e5e7eb → #d1d5db`) at staggered heights, with `skeletonPulse` (0.55 ↔ 1.0 opacity, 1.1s ease-in-out) and staggered `animation-delay` per group of 5
- Centred SVG spinner (`stroke-dasharray:45 20`, `spinnerRot` 0.8s linear infinite) over the bars
- Chart renders after **620ms**; skeleton fades out (`opacity:0`, 320ms) then is removed from DOM

#### Effect 1 — Mouse trail canvas
- `<canvas class="qa-trail-canvas" id="qaTrailCanvas">` sits `position:absolute; inset:0; z-index:2` over the SVG
- `initTrailCanvas()` sizes it to `wrap.clientWidth × wrap.clientHeight`; `ResizeObserver` resizes on layout change
- `_drawTrail()` RAF loop: each frame clears canvas, filters points by `a > 0.02`, draws circles with `rgba(rgb, a)`, decays `a *= 0.88` and `r *= 1.04`
- 4-colour palette: indigo `99,102,241` · blue `59,130,246` · green `16,185,129` · amber `245,158,11`
- Points capped at 60

#### Effect 2 — Particle burst on click
- `qaSpawnParticles(e)` spawns 7 `.qa-particle` divs at click coordinates inside `#qaChartWrap`
- Each particle: random colour from 5-colour palette, angle spread `2π/7 * i`, distance 22–42px, `particleFly` animation (0.7s ease-out): `translate + scale(0.3) + opacity:0`, `--pfly` CSS var
- Particles are `position:absolute; border-radius:50%; z-index:4` and self-remove after `animationend`

#### Effect 3 — Shimmer sweep
- `qaRunShimmer()` appends a `.qa-shimmer` div: 80px wide translucent strip (`rgba(255,255,255,0.5)` gradient), `animates shimmerSweep` (1s ease-in-out, left: -80px → calc(100% + 80px)), removed on `animationend`

#### Effect 4 — KPI count-up pop-in
- `qaAnimateKpis()` staggers `.qa-insight-kpi` pop-in: `kpiPop` (scale 0.8 → 1.06 → 1, opacity 0→1, 0.45s cubic-bezier), 80ms + 110ms × index delay
- Each `.qa-insight-kpi-val` numeric value counts up from 0 over 700ms using `requestAnimationFrame` with `1 - (1-t)³` easing; decimal-aware; preserves unit suffix `<span>`

#### Effect 5 — SVG pulse rings
- `qaAddPulseRings(svg, points, color)` appends `<circle>` elements to the SVG at data-point coordinates
- Each circle: `class="qa-pulse-ring"`, `pulseRing` animation (r: 5→14, stroke-opacity: 0.7→0, 1.4s ease-out infinite), random `animation-delay` 0–0.8s

---

### JavaScript functions (`headless.html`)

| Function | Purpose |
|---|---|
| `switchTab(id, btn)` | Shows active tab panel; triggers `animateDonut()`, `initTrend()`, `initAtStats()` on respective tabs; hides right panel on `agentic`/`policy` tabs |
| `switchPPTab(tab, btn)` | Switches Studio ↔ Configuration Testing sub-tabs; hides `pp-right` on config tab |
| `cycleBadge(btn)` | Cycles permission badge: Auto → Ask → Approval → Auto |
| `openCaseDetail(idx)` | Opens full-page case detail overlay; populates confidence chart, gates bar, ledger, reasoning, sidebar card + buttons (context-aware labels) |
| `closeCaseDetail()` | Removes `.visible` from `#caseDetailPage`; clears `_currentCaseIdx` |
| `renderCases(data)` / `filterCases()` | Renders + live-filters cases table by search + 4 dropdowns |
| `showToast(msg, type)` | Shows temporary toast notification (green/blue/orange) |
| `initRadar()` | Draws 8-axis interactive SVG radar chart; polygon hover, legend toggle, floating tooltip |
| `animateDonut()` | Animated draw-in + count-up + pulse glow on donut chart; replays every policy tab open |
| `initTrend()` | Draws trend chart; hover crosshair + tooltip; month-label click redraws curve |
| `initTimeline()` | Draws activity timeline; draw-in animation; hover crosshair; marker click popovers; time-tab switching |
| `initAtStats()` | Count-up pop-in on agentic tab open; staggered delay; red pulse glow; amber shimmer |
| `initStatValues()` | Animates confidence + fleet health stats on load |
| `handleQuickAction(action, btn)` | Wrapper: shows skeleton → renders chart after 620ms → hides skeleton → fires all 5 micro-interaction effects |
| `qaShowSkeleton()` | Injects `.qa-skeleton` overlay (20 shimmer bars + SVG spinner) into `#qaChartWrap` |
| `qaHideSkeleton()` | Fades out and removes `.qa-skeleton` (300ms opacity transition) |
| `qaRunShimmer()` | Appends shimmer sweep div to `#qaChartWrap`; self-removes after 1s |
| `qaAnimateKpis()` | Stagger-animates `.qa-insight-kpi` pop-in; count-up for all `.qa-insight-kpi-val` numerics |
| `qaBindChartInteractions()` | One-time bind of mousemove (trail) + click (particles) + ResizeObserver to `#qaChartWrap` |
| `qaShowSkeleton()` / `qaHideSkeleton()` | Skeleton loader: show before chart renders; fade-remove after |
| `qaTrailMove(e)` | Pushes `{x,y,r,a,rgb}` point onto `_trailPoints`; capped at 60 |
| `qaSpawnParticles(e)` | Spawns 7 animated particle divs at click coords in `#qaChartWrap` |
| `qaAddPulseRings(svg, pts, color)` | Appends animated pulse-ring circles to SVG at given data-point coords |
| `closeQaPanel()` | Hides panel; clears active button state |
| `drawLatencyChart(wrap)` | Draws multi-line latency time-series SVG (30 data points × 3 agents) |
| `drawC4Chart(wrap)` | Draws horizontal bar chart SVG (13 nodes, health %) |
| `drawRcaChart(wrap)` | Draws stacked area chart SVG (72h, 3 contributors) |
| `qaLatHov(e,i,v0,v1,v2)` | Latency chart hover — tooltip + crosshair |
| `qaC4Hov(e,name,val,color)` | C4 bar hover — tooltip with node name + health status |
| `qaRcaHov(e,label,hw,cfg,load)` | RCA area hover — tooltip with per-contributor breakdown |
| `qaHideTT()` | Hides `#qaTooltip` and crosshair line |
| `runConfigTest(scenario)` / `renderCTResult()` | Runs digital-twin simulation; animated spinner → metric count-up |
| `renderTopo()` | Draws animated network topology SVG (7 nodes) |
| `closeDropdown()` / `selectRegion(name)` | Region dropdown open/close/select |
| `openApproveModal` / `confirmApprove` / `confirmEscalate` | Action card modal flow |
| `initDragDrop()` | Wires dragstart/dragend on all `[draggable]` cards; dragover/drop on canvas viewport |
| `openDropPanel(cardId)` | Populates + shows `#dropPanel` with card-specific KPIs, trace, confidence bars, tags |
| `closeDropPanel()` | Hides `#dropPanel` |
| `confirmDropApprove(cardId)` | Approve action from drop panel — fires toast (timeline branch: export toast) |
| `confirmDropEscalate()` | Escalate from drop panel — fires orange toast |
| `geoToOrth(lon, lat, R, cx, cy)` | Orthographic projection: returns `[x, y, dot]` or `null` if behind globe (`dot < 0`) |
| `gmapDraw()` | Main globe render loop: star field → atmosphere → ocean → clip → graticule → continents → gloss → rim → arcs → nodes |
| `drawArc(lon1, lat1, lon2, lat2, color, dashed)` | Renders a 40-sample Slerp great-circle arc between two lon/lat points |
| `gmapInit()` | Sets canvas hi-DPI size (300px), cancels previous RAF, wires all mouse/wheel/touch events |
| `gmapNodeHit(mx, my)` | Finds node within 12px of cursor using `geoToOrth`; returns null for back-hemisphere nodes |
| `gmapZoomIn/Out/Reset()` | Adjusts `globeZoom`; reset restores `globeLon=20, globeLat=15, globeZoom=1` |
| `openAiPanel()` | Shows `#aiPanel` with `.visible` class |
| `closeAiPanel()` | Hides panel; removes `listening`/`has-chat`; resets orb labels; stops recognition |
| `toggleAiListen()` | Toggles listening state; starts/stops Speech Recognition; updates orb title + sub |
| `startRecognition()` | Starts Web Speech API; falls back to 2s demo simulation on unsupported browsers |
| `stopRecognition()` | Stops recognition; clears fallback timer |
| `stopListenState()` | Clears listening UI state and stops recognition |
| `aiSendText()` | Reads text input; calls `aiAddUserMsg` + `aiShowTyping` + delayed `aiAddAgentMsg` |
| `aiSuggest(chip)` | Suggestion chip click — same flow as `aiSendText` |
| `getAiResponse(text)` | Keyword-matches input to canned response object (`text` + `chips[]`) |
| `aiAddUserMsg(text)` | Appends user bubble; adds `has-chat` class to panel |
| `aiShowTyping()` | Appends 3-dot typing indicator bubble (`#aiTypingMsg`) |
| `aiAddAgentMsg(resp)` | Removes typing indicator; appends agent bubble with text + KPI chips |
| `_cdRipple(btn, e)` | Spawns `.cd-ripple` span at click coords; removes self after `cdRipple` animation ends |
| `cdApprove(e)` | Ripple → spinner/disabled → green success state → toast → `closeCaseDetail()` (1.4s + 1s) |
| `cdDeny(e)` | Ripple → spinner/disabled → grey dismissed state → toast → `closeCaseDetail()` (1.1s + 0.9s) |
| `cdChatSend()` | Reads sidebar chat input; adds user bubble, hides chips, shows typing, fires agent reply after 1.2s |
| `cdChatChip(chip)` | Sidebar suggestion chip click — same flow as `cdChatSend` |
| `_cdGetResponse(text)` | Keyword-matches sidebar chat input to `cdChatResponses` (5 keys + default) |
| `_cdChatAddUser(text)` / `_cdChatAddAgent(resp)` | Appends user/agent bubbles to `.cd-chat-msgs` |
| `_cdChatTyping()` | Shows typing indicator in sidebar chat; removed when agent reply arrives |

---

### CSS animations in `headless.html`

| Keyframe | Used by | Effect |
|---|---|---|
| `skeletonPulse` | `.qa-skeleton-bar` | Opacity 0.55 ↔ 1, 1.1s ease-in-out — pulsing shimmer bars |
| `spinnerRot` | `.qa-skeleton-spinner circle` | `stroke-dashoffset` → -80, 0.8s linear — rotating arc |
| `shimmerSweep` | `.qa-shimmer` | left: -80px → 100%+80px, 1s ease-in-out |
| `pulseRing` | `.qa-pulse-ring` | r: 5→14, stroke-opacity: 0.7→0, 1.4s ease-out infinite |
| `drawLine` | `.qa-line-anim` | stroke-dashoffset 3000→0, 1.1s cubic-bezier |
| `areaFadeIn` | `.qa-area-anim` | opacity 0→1, 0.7s ease, 0.7s delay |
| `kpiPop` | `.qa-kpi-pop` | scale 0.8→1.06→1, opacity 0→1, 0.45s cubic-bezier |
| `particleFly` | `.qa-particle` | translate + scale 0.3 + opacity 0, 0.7s ease-out |
| `cdRipple` | `.cd-ripple` | scale 1→4, opacity 0, 0.55s ease-out |
| `btnSpinRot` | `.cd-btn-spinner` | rotate 360°, 0.7s linear infinite |
| `successPulse` | `.cd-btn-approve.success` | scale 0.7→1.15→1, opacity 0→1, 0.35s cubic-bezier |

---

### Design tokens used in `headless.html`

| Token | Value | Used for |
|---|---|---|
| Body gradient | `linear-gradient(160deg, #f8fafd → #f3f6fb → #ddeaf5 → #b8d4e8 → #9ec8e0)` fixed | Full-page background |
| Accent blue | `#2563eb` | Tab active border, donut, quick-action + suggestion buttons |
| Dark green | `#166534` | Knob values, stat percentages, chart KPI values |
| Red alert | `#dc2626` | Agent-04 latency line, hardware RCA area, at-stat pulse |
| Amber | `#d97706` | Agent-06 latency line, config-drift RCA area, at-stat shimmer |
| Text primary | `#111827` | Headings, labels |
| Text muted | `#6b7280` | Descriptions, subtitles |
| Text faint | `#9ca3af` | Radar axis labels, chart grid labels |
| Border | `#e5e7eb` | Panel dividers, chart grid lines |
| Surface frosted | `rgba(255,255,255,0.72)` + `backdrop-filter:blur(12px)` | Policy panels (header, score row, tabs, studio) |
| QA panel bg | `rgba(248,250,253,0.97)` + `backdrop-filter:blur(16px)` | Quick-action panel overlay |
| Drop panel bg | `rgba(248,250,253,0.97)` + `backdrop-filter:blur(16px)` + scale-in | Drop detail panel |
| AI panel bg | `linear-gradient(160deg, #eef4fb, #ddeaf5, #c8dff0)` | AI voice/chat panel background |
| AI orb gradient | `#bfdbfe → #a5b4fc → #818cf8 → #60a5fa → #93c5fd` | Gradient sphere + mic trigger button |
| AI indigo | `#818cf8` / `#6366f1` | Listening state, send button, voice button |
| White solid | `#ffffff` | `.pp-right` panel |
| Panel inset | `inset:15px` when `.visible` | 15px floating margin (qa-panel, drop-panel, ai-panel) |
| Auto badge | `#dcfce7` / `#166534` | Green Auto permission |
| Ask badge | `#dbeafe` / `#1d4ed8` | Blue Ask permission |
| Approval badge | `#f3f4f6` / `#374151` | Grey Approval permission |

---

## File Structure

```
/Users/jayakrishnakaimal/Desktop/JK_demo/
│
├── index.html                          ← MAIN SITE (~3400 lines)
│   Key sections:
│   ├── CSS (lines 8–1050)
│   │   ├── Panel/split layout           ~118–145
│   │   ├── MacBook SVG keyframes        ~1212–1216 (inline <style>)
│   │   ├── Char tabs CSS                ~338–400
│   │   ├── Pillar arch CSS              ~604–620
│   │   ├── Direction micro-interaction  ~688–880
│   │   └── Gallery / Lightbox CSS       ~880–960
│   ├── Top nav                          ~1053–1064
│   ├── Stepper bar                      ~1066–1095
│   ├── Panel 0 — Overview              ~1099–1437
│   │   └── MacBook SVG                 ~1218–1387
│   ├── Panel 1 — What & Why            ~1442–1568
│   ├── Panel 2 — Characteristics       ~1573–1820
│   │   └── Live agent terminal demo    ~1793–1816
│   ├── Panel 3 — Four Pillars          ~1825–1900
│   │   └── Interactive SVG diagram     ~1900–2200
│   ├── Panel 4 — Directions & Gallery  ~2390–2680
│   │   ├── Direction cards             ~2395–2455
│   │   ├── Team grid                   ~2458–2468
│   │   ├── Gallery 4-tile              ~2470–2525
│   │   └── Rail micro-interaction      ~2516–2677
│   ├── Gallery Lightbox HTML           ~2682–2712
│   ├── Dark footer                     ~2714–2726
│   └── <script> block                  ~2728–end
│       ├── goToStep / stepper          ~2728–2751
│       ├── VS toggle                   ~2760
│       ├── Char tabs                   ~2770–2778
│       ├── Gallery lightbox JS         ~3060–3135
│       ├── Pillar architecture JS      ~3137–3214
│       └── Direction micro-interactions ~3215–3410
│
├── headless.html                       ← HEADLESS AI DASHBOARD (~6200 lines)
│   ├── CSS (lines 8–2100)
│   │   ├── Body gradient + base          ~8–42
│   │   ├── Top nav                       ~44–165
│   │   ├── Stats bar + badges            ~166–265
│   │   ├── Canvas viewport + orbs        ~266–342
│   │   ├── AI mic trigger + AI panel     ~342–640
│   │   │   ├── .ai-mic-trigger           ~342–356
│   │   │   ├── .ai-panel + close         ~358–390
│   │   │   ├── .ai-orb-area / glow / ring/ sphere ~392–490
│   │   │   ├── .ai-listen-dots           ~492–514
│   │   │   ├── .ai-chat-area / messages  ~516–590
│   │   │   ├── .ai-typing                ~592–610
│   │   │   ├── .ai-input-row / wrap      ~612–660
│   │   │   └── .ai-suggestions / chip    ~662–640
│   │   ├── Quick-action panel (.qa-*)    ~640–730
│   │   ├── QA chart micro-interaction CSS ~730–800
│   │   │   ├── .qa-skeleton + bars       ~800–835
│   │   │   ├── shimmerSweep / pulseRing  ~735–760
│   │   │   ├── kpiPop / particleFly      ~770–790
│   │   │   └── skeletonPulse / spinnerRot ~800–840
│   │   ├── Drag states + drop panel      ~840–1095
│   │   ├── Agentic trace (.at-*)         ~1095–1210
│   │   ├── #tab-agentic (position:relative) ~1210–1215
│   │   ├── Case detail (.cd-page, .cd-main, .cd-sidebar) ~1215–1530
│   │   │   ├── .cd-side-card (12.png)    ~1430–1520
│   │   │   ├── .cd-side-btns + buttons   ~1487–1610
│   │   │   ├── Ripple + spinner CSS      ~1560–1615
│   │   │   └── .cd-chat-box              ~1615–1700
│   │   ├── Right panel + action cards    ~1700–1850
│   │   ├── Timeline CSS                  ~1850–1940
│   │   ├── Policy & Permissions (.pp-*)  ~1940–2070
│   │   └── Config testing tab (.ct-*)    ~2070–2140
│   ├── Top nav HTML                      ~2140–2200
│   ├── Canvas tab HTML                   ~2580–2960
│   │   ├── Greeting + quick buttons      ~2800–2930
│   │   ├── #qaPanel (insight + chart + canvas) ~2932–2950
│   │   ├── AI mic trigger button         ~2953–2965
│   │   ├── #aiPanel (orb + chat + input) ~2965–3040
│   │   └── #dropPanel (drop detail)      ~3040–3120
│   ├── Agentic trace tab HTML            ~3120–3220
│   ├── #caseDetailPage (inside #tab-agentic) ~3038–3400
│   │   ├── #cdMain (confidence chart, gates, ledger, reasoning) ~3040–3270
│   │   └── #cdSidebar (cd-side-card, cd-side-btns, cd-chat-box) ~3270–3400
│   ├── Policy & Permissions tab HTML     ~3400–3600
│   ├── Right panel (3 draggable cards)   ~3600–3800
│   └── <script> block                    ~3800–end (~6215)
│       ├── switchTab / initStatValues    ~3810–4000
│       ├── animateDonut / initTrend      ~4000–4100
│       ├── openCaseDetail / closeCaseDetail ~4100–4400
│       │   ├── caseDetailData[10]        ~4100–4200
│       │   └── confidence chart + gates animation ~4270–4310
│       ├── _cdRipple / cdApprove / cdDeny ~4350–4420
│       ├── cdChatSend / cdChatChip / responses ~4420–4510
│       ├── renderCases / filterCases     ~4510–4640
│       ├── showToast / region / modals   ~4650–4770
│       ├── initTimeline / initTrend      ~4770–4850
│       ├── initRadar (interactive SVG)   ~4850–4900
│       ├── Config testing (CT_SCENARIOS) ~4900–4970
│       ├── closeQaPanel / _origHandleQuickAction wrapper ~4970–5000
│       ├── QA micro-interactions (trail, particles, shimmer, kpi, rings, skeleton) ~5000–5070
│       ├── drawLatencyChart / drawC4Chart / drawRcaChart ~5070–5200
│       ├── hover helpers (qaLatHov etc.) ~5200–5250
│       ├── AI panel (openAiPanel … aiAddAgentMsg) ~5250–5450
│       └── initDragDrop + dropCardData + drop handlers ~5450–5600
│
├── uxr_plan.html                       ← UXR CONCEPT TESTING PLAN (~1460 lines)
│   ├── Carbon CSS tokens + component styles  lines 10–625
│   ├── UI Shell header (Research · Headless) lines 628–641
│   ├── Page header (dark, IBM style)         lines 643–648
│   ├── Key metric tiles (4-col)              lines 650–670
│   ├── Section 01 — Background & screens     lines 671–740
│   ├── Section 02 — Research objectives      lines 742–804
│   ├── Section 03 — Key research questions   lines 805–855
│   ├── Section 04 — Participant criteria     lines 856–906
│   ├── Section 05 — Tasks & discussion guide lines 907–1075
│   ├── Section 06 — Success metrics          lines 1076–1125
│   ├── Section 07 — Study timeline           lines 1126–1178
│   ├── Section 08 — Analysis framework       lines 1179–1238
│   ├── Section 09 — Discussion guide outline lines 1239–1300
│   ├── Section 10 — Risks & mitigations      lines 1301–1368
│   ├── Section 11 — Deliverables             lines 1369–1430
│   └── Page footer                           lines 1432–1454
│
├── designing-for-invisible-ui.md       ← This file (project documentation)
│
├── ibm-content-design-review-designing-for-invisible-ui.html
│                                       ← IBM content design heuristic review
│
├── SKILL.md                            ← IBM content design skill reference
│
├── ini1.png    ← Gallery: Canvas — Main Dashboard
├── ini2.png    ← Gallery: Agentic Trace — Escalation View
├── ini3.png    ← Gallery: Policy & Permissions — Studio
├── ini4.png    ← Gallery: Policy & Permissions — Full Scroll
│
├── 01.png      ← headless.html reference: Canvas dashboard
├── 02.png      ← headless.html reference: Agentic trace list
├── 03.png      ← headless.html reference: Agentic trace detail
├── 04.png      ← headless.html reference: Policy & Permissions
├── 05.png      ← headless.html reference: Digital twin
├── 06.png      ← headless.html reference: Policy Studio flat layout
├── 07.png      ← headless.html reference: pp-right radar full view
├── 08.png      ← headless.html reference: pp-right knobs section
├── 09.png      ← headless.html reference: Configuration Testing tab
├── 10.png      ← headless.html reference: AI voice/chat panel orb design
├── 11.png      ← headless.html reference: Case detail full page
├── 12.png      ← headless.html reference: cd-side-card escalation card
├── 13.png      ← headless.html reference: (reserved for next feature)
│
└── desgin-for-invisible-ui (1).pptx   ← Source presentation (25 slides)
```

---

## GitHub

| Property | Value |
|---|---|
| Remote | `git@github.com:jayakrishnakaimal/JK_Demo.git` |
| Branch | `main` |
| Pages | https://jayakrishnakaimal.github.io/JK_Demo/ |
| Main site | https://jayakrishnakaimal.github.io/JK_Demo/index.html |
| UXR Plan | https://jayakrishnakaimal.github.io/JK_Demo/uxr_plan.html |
| Headless Dashboard | https://jayakrishnakaimal.github.io/JK_Demo/headless.html |

---

## Changelog

### Latest — `headless.html`

| # | Change | Detail |
|---|---|---|
| 1 | **3D Orthographic Globe** | Replaced flat equirectangular map with a fully custom canvas orthographic globe renderer. Auto-spin, star field, atmosphere glow, ocean gradient, graticule, continent polygons, great-circle arc edges, specular gloss, drag-to-rotate, scroll-to-zoom, double-click spin toggle. |
| 2 | **Globe nav button** | `.nav-icon-btn--globe` — 36×36 gradient blue pill with radial-fill SVG sphere, specular dot, hover glow ring + scale, active solid-blue state. |
| 3 | **qa-insight sidebar** | Creative coloured KPI sidebar: rainbow accent stripe, per-card colour variants (red/amber/green/blue/violet), `--kpi-accent` CSS var, left accent bar, mini SVG icon + status badge, trend micro-pill below each value. |
| 4 | **Remove maximize button** | `settingsMaximizeBtn` + `settingsRestoreBtn` removed from Global Network Map panel header. Only close (✕) remains. |
