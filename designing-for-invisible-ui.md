# Designing for Invisible UI

> A design research interactive guide for **headless AI agents** — AI systems that operate autonomously without a user-facing interface. Built as a **5-panel interactive stepper** (`index.html`) using the IBM Predictable Delivery design language.

---

## Project Overview

| Property | Value |
|---|---|
| **Format** | 5-panel interactive stepper (`index.html`) |
| **Theme** | IBM Predictable Delivery — white + light blue-grey, IBM Plex Sans 300, `#0f62fe` accent |
| **Panels** | 0 Overview · 1 What & Why · 2 Characteristics · 3 Four Pillars · 4 Directions & Gallery |
| **Pillars explored** | 4 (Scope & Policy · Trace View · Contextual Chat · Agent Identity) |
| **Design directions** | 5 (derived from the four pillars) |
| **Navigation** | Fixed top nav + stepper progress bar; `goToStep(n)` JS-driven panel switching |
| **Flow label** | Recognition → Words → Agreement → Evidence |

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
- **Top nav** — fixed 48px bar; IBM logo · step tabs · "View as" role selector · step counter badge
- **Stepper bar** — 5 dots with connecting line; active dot filled blue, completed dots outlined
- **Back / Next buttons** — `btn-back` / `btn-next` at bottom of each panel calling `goToStep(n)`

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
| `event` | Event Driven | Network agent triggers on CPU > 85%, reroutes load, logs action |
| `autonomous` | Autonomous | Security agent monitors 50+ apps, revokes stale permissions 24/7 |
| `action` | Action Oriented | Invoice agent extracts PDF data, writes to DB, schedules payment |
| `context` | Context Building | Lead enrichment agent queries LinkedIn + Crunchbase from scratch |

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

## File Structure

```
/Users/jayakrishnakaimal/Desktop/JK_demo/
│
├── index.html                          ← MAIN FILE (~3400 lines)
│   Key sections:
│   ├── CSS (lines 7–880)
│   │   ├── Panel/split layout           ~118–145
│   │   ├── MacBook SVG keyframes        ~1211–1215 (inline <style>)
│   │   ├── Char tabs CSS                ~338–400
│   │   ├── Pillar arch CSS              ~604–620
│   │   ├── Direction micro-interaction  ~688–880
│   │   └── Gallery / Lightbox CSS       ~880–960
│   ├── Panel 0 — Overview              ~1099–1436
│   │   └── MacBook SVG                 ~1217–1386
│   ├── Panel 1 — What & Why            ~1441–1566
│   ├── Panel 2 — Characteristics       ~1572–1819
│   │   └── Live agent terminal demo    ~1790–1815
│   ├── Panel 3 — Four Pillars          ~1824–2385
│   │   └── Interactive SVG diagram     ~1900–2200
│   ├── Panel 4 — Directions & Gallery  ~2390–2679
│   │   ├── Direction cards             ~2395–2455
│   │   ├── Team grid                   ~2458–2468
│   │   ├── Gallery 4-tile              ~2470–2525
│   │   └── Rail micro-interaction      ~2516–2677
│   ├── Gallery Lightbox HTML           ~2682–2712
│   ├── Dark footer                     ~2714–2726
│   └── <script> block                  ~2728–end
│       ├── goToStep / stepper          ~2728–2750
│       ├── VS toggle                   ~2760
│       ├── Char tabs                   ~2770–2780
│       ├── Gallery lightbox JS         ~3060–3135
│       ├── Pillar architecture JS      ~3137–3214
│       └── Direction micro-interactions ~3215–3410
│
├── designing-for-invisible-ui.md       ← This file
│
├── ini1.png    ← Gallery: Canvas dashboard
├── ini2.png    ← Gallery: Agentic Trace
├── ini3.png    ← Gallery: Policy & Permissions Studio
├── ini4.png    ← Gallery: Policy & Permissions Full Scroll
│
├── desgin-for-invisible-ui (1).pptx   ← Source presentation (25 slides)
│
└── Screenshot 2026-09-03 at *.png     ← Backup screenshots (not used in gallery)
```
