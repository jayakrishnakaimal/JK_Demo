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
| Right icons | Person icon · Globe icon |

---

### Stats Bar

| Stat | Icon | Value | Style |
|---|---|---|---|
| Confidence score | Stick-figure SVG | **95%** | `font-weight:300`, dark green `#1a6334` |
| Agent fleet health | ECG sparkline SVG | **94%** | same |
| Badges | Auto-resolved · Escalation · Fix failed | — | coloured pill badges |

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

**Layout:** Left sidebar (220px) of KPI cards + insight note · Right chart area (flex:1)

| Button | Title | Tag | Chart type | KPI cards |
|---|---|---|---|---|
| Latency spike | Latency Analysis | Live · 5s refresh | Multi-line time-series (30 min) | Peak 284ms · Avg 142ms · SLA 200ms |
| Cluster C4 | Cluster C4 Status | 12 / 13 Healthy | Horizontal bar chart (13 nodes) | 12 healthy · 1 degraded · Avg 97% |
| Root cause | Root Cause Analysis | 72h window | Stacked area chart (72h) | 4 820 events · 3 root causes · 91% confidence |

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
| Row interaction | Click → slide-in detail drawer from right |
| Drawer | Agent trace steps (Observe → Correlate → Plan → Act → Verify), meta, close button |
| Keyboard | `Esc` closes drawer |

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

### JavaScript functions (`headless.html`)

| Function | Purpose |
|---|---|
| `switchTab(id, btn)` | Shows active tab panel; triggers `animateDonut()`, `initTrend()`, `initAtStats()` on respective tabs; hides right panel on `agentic`/`policy` tabs |
| `switchPPTab(tab, btn)` | Switches Studio ↔ Configuration Testing sub-tabs; hides `pp-right` on config tab |
| `cycleBadge(btn)` | Cycles permission badge: Auto → Ask → Approval → Auto |
| `openDrawer(i)` / `closeDrawer()` | Opens/closes agentic trace detail drawer |
| `renderCases(data)` / `filterCases()` | Renders + live-filters cases table by search + 4 dropdowns |
| `showToast(msg, type)` | Shows temporary toast notification (green/blue/orange) |
| `initRadar()` | Draws 8-axis interactive SVG radar chart; polygon hover, legend toggle, floating tooltip |
| `animateDonut()` | Animated draw-in + count-up + pulse glow on donut chart; replays every policy tab open |
| `initTrend()` | Draws trend chart; hover crosshair + tooltip; month-label click redraws curve |
| `initTimeline()` | Draws activity timeline; draw-in animation; hover crosshair; marker click popovers; time-tab switching |
| `initAtStats()` | Count-up pop-in on agentic tab open; staggered delay; red pulse glow; amber shimmer |
| `initStatValues()` | Animates confidence + fleet health stats on load |
| `handleQuickAction(action, btn)` | Shows `#qaPanel`; marks active button; populates KPI sidebar; draws SVG chart |
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
├── headless.html                       ← HEADLESS AI DASHBOARD (~4500 lines)
│   ├── CSS (lines 8–2000)
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
│   │   ├── Drag states + drop panel      ~730–1060
│   │   │   ├── .action-card drag CSS     ~730–760
│   │   │   ├── .drag-hint                ~762–770
│   │   │   ├── .canvas-viewport.drag-over ~772–790
│   │   │   └── .drop-panel + dp-*        ~792–1060
│   │   ├── Agentic trace (.at-*)         ~1060–1350
│   │   ├── Right panel + action cards    ~1350–1510
│   │   ├── Timeline CSS                  ~1510–1600
│   │   ├── Policy & Permissions (.pp-*)  ~1600–1850
│   │   └── Config testing tab (.ct-*)    ~1850–2000
│   ├── Top nav HTML                      ~2000–2060
│   ├── Canvas tab HTML                   ~2060–2380
│   │   ├── Greeting + quick buttons      ~2155–2195
│   │   ├── #qaPanel (insight + chart)    ~2197–2220
│   │   ├── AI mic trigger button         ~2222–2232
│   │   ├── #aiPanel (orb + chat + input) ~2234–2310
│   │   └── #dropPanel (drop detail)      ~2312–2340
│   ├── Agentic trace tab HTML            ~2380–2500
│   ├── Policy & Permissions tab HTML     ~2500–2700
│   ├── Right panel (3 draggable cards)   ~2560–2760
│   │   ├── Card 1: restart (data-card)   ~2565–2630
│   │   ├── Card 2: chronic (data-card)   ~2632–2680
│   │   └── Card 3: timeline (data-card)  ~2682–2760
│   └── <script> block                    ~2760–end (~4500)
│       ├── switchTab / initStatValues    ~2767–3000
│       ├── animateDonut                  ~3000–3050
│       ├── openDrawer / closeDrawer      ~3050–3110
│       ├── renderCases / filterCases     ~3110–3240
│       ├── showToast / region / modals   ~3250–3490
│       ├── initTimeline                  ~3490–3700
│       ├── initTrend                     ~3700–3800
│       ├── initRadar (interactive SVG)   ~3800–3840
│       ├── Config testing (CT_SCENARIOS) ~3840–3920
│       ├── closeQaPanel / handleQuickAction ~3920–3990
│       ├── drawLatencyChart / drawC4Chart / drawRcaChart ~3990–4130
│       ├── hover helpers (qaLatHov etc.) ~4130–4150
│       ├── AI panel (openAiPanel … aiAddAgentMsg) ~4150–4350
│       └── initDragDrop + dropCardData + drop handlers ~4350–4500
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
