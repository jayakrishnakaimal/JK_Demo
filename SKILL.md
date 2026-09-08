---
name: ibm-content-design
description: >
  Review or generate IBM Software interface content from Figma designs, screenshots, user flows,
  or supplied UI strings. Apply IBM voice, Carbon for IBM Products guidance, IBM Content Standard
  heuristics, and accessibility writing requirements to navigation, headings, labels, actions,
  forms, messages, empty states, notifications, and related product copy. Use for IBM product UI
  content work; do not use for marketing campaigns, long-form technical documentation, UI code,
  or implementation-only accessibility audits.
---

# IBM content design

Help designers create clear, consistent, accessible content for IBM Software interfaces. Review
content in its visual and task-flow context, not as isolated strings. Preserve the product's
established terminology unless authoritative IBM guidance or clear user harm supports changing it.

---

## Source model

Use sources according to the decision being made. Do not treat them as a single universal ranking.

1. Accessibility, legal, safety, and regulatory requirements take precedence when applicable.
2. Product terminology and established interaction behavior govern product-specific meaning.
3. Carbon and Carbon for IBM Products govern component patterns and IBM Software UI conventions.
4. IBM editorial, design-language, and brand guidance govern language mechanics, voice, and tone.
5. Local consistency and designer judgment resolve cases not covered above.

When sources differ, name the conflict and recommend the option that best preserves accessibility,
task clarity, product meaning, and cross-product consistency. Do not invent a rule or claim that
all IBM sources agree when the evidence only comes from one source.

---

## Review inputs

Accept any combination of:

- a Figma file, selected frame, prototype, or component link
- screenshots or exported frames
- pasted UI strings or a content inventory
- a user flow, product requirement, or description of the interaction

For a Figma review, establish the selected scope before reviewing: specific frames, a component,
a complete flow, or the full accessible file. If only images or strings are available, review what
is observable and identify missing context without pretending to have inspected hidden layers,
interactions, or component states.

Ask for missing context only when it would materially change the recommendation. Otherwise state
a reasonable assumption and proceed.

---

## IBM voice and tone

IBM content should be simple and logical, confident without boasting, grounded in facts and
outcomes, persuasive rather than poetic, and intellectually purposeful. Voice remains recognizable;
tone changes with the user's situation.

**IBM Brand Center voice checklist — IBM content at its best:**
- Has a clear point of view
- Is simple and logical
- Builds on solid research, data, and analysis
- Is intellectually ambitious — expresses a bigger idea
- Is persuasive, not poetic
- Is confident, but not boastful
- Only uses figurative language for emphasis
- Elevates facts and outcomes
- Engages the thinker by speaking like the thinker

| Context | Appropriate tone |
| --- | --- |
| Onboarding and tours | Inviting, encouraging, conversational |
| Headings and navigation | Direct, concise, informational |
| Descriptions and guidance | Clear, instructional, action-oriented |
| Empty states | Inviting, focused on the first meaningful action |
| Success | Brief, warm, proportional to the achievement |
| Error and warning states | Respectful, factual, economical, recovery-oriented |
| Help text and tooltips | Concise and supplemental |

Avoid forced delight in stressful, destructive, security-sensitive, or failure situations.

**IBM personality traits (Level 3 — Excellent):**
- **Engaging** — speaks directly to users; confident; conveys a likeable personality
- **Helpful** — guides users through their goals; just enough information; aids error recovery
- **Conversational** — natural, everyday language; warm; sounds like a person, not a machine

---

## Core writing guidance

### Language mechanics

- Use US English throughout.
- Use sentence case for all IBM Software UI text. Preserve proper nouns, trademarks, approved
  product names, initialisms, and intentionally styled names (watsonx, GitHub, iPhone).
- Prefer active voice — it makes the actor and action clear.
- Passive voice can be useful when the actor is irrelevant or when it avoids blaming the user,
  especially in error messages. Do not require passive voice for every error.
- Prefer simple present or simple past over unnecessarily complex constructions.
- Address the user as "you." Prefer direct imperatives for actions.
- Use common contractions when they sound natural: can't, don't, isn't, what's. Avoid
  triple contractions (wouldn't've). Never form contractions with brand names.
- Use one term for one concept across the complete flow — no synonyms for the same thing.
- Avoid unnecessary "please," "thank you," and "successfully" in routine system messages.

### Word choice

Prefer the simpler word when it preserves the intended meaning:

| ✅ Use | ❌ Avoid |
| --- | --- |
| start | commence, initiate |
| end / stop | terminate |
| run | execute |
| use | utilize, leverage |
| help | assist, assistance |
| before | prior to |
| if | in the event of |
| to | in order to |
| buy | purchase |
| extra / more | additional |

Jargon to avoid:

| ❌ Avoid | ✅ Use instead |
| --- | --- |
| abort | cancel, stop, end |
| drill down | refine, explore, expand |
| drive (abstract) | control, manage, increase |
| facilitate (abstract) | be specific about how you're helping |
| going forward | in future |
| monetize | chargeable, paid plans |
| socialize | publish, share |
| synergy | reword to natural language |

Replace Latin abbreviations when space allows: i.e. → "that is"; e.g. → "for example"; etc. → "and so on".

US English spellings (always use left column):

| ✅ Use | ❌ Avoid |
| --- | --- |
| authorize | authorise |
| behavior | behaviour |
| canceled | cancelled |
| center | centre |
| organize | organise |
| program | programme |
| toward | towards |

### Content length

Treat length guidance as a target, not a reason to sacrifice meaning:

- Button labels are typically 1–2 words and verb-first.
- Navigation labels typically aim for 1–3 words and predominantly use nouns.
- Field labels should be short enough to scan while remaining explicit.
- Page headings should be succinct and front-load the distinguishing concept.
- Body text should be designed for a comfortable measure, commonly 32–80 characters per rendered
  line. Evaluate this only when the rendered layout is visible — it is not a string-length limit.

When an exception is needed, explain the user or product benefit rather than mechanically shortening.

---

## Component patterns

### Action labels

Use the standard Carbon term when it accurately describes the action. Check the consequence before
changing a label. Do not substitute a standard label blindly — retain established product language
when changing it would create cross-product inconsistency.

| Meaning | ✅ Preferred label | ❌ Avoid |
| --- | --- | --- |
| Enter an existing account | **Log in** | Sign in (visually distinct from Sign up) |
| Create an account | **Sign up** | Register |
| Return one step | **Back** | Previous |
| Abandon action or close without applying | **Cancel** | Close, Dismiss |
| Stop an operation in progress | **Stop** | Abort, Kill, Terminate |
| Permanently destroy an object | **Delete** | Remove (implies reversibility) |
| Detach an object while preserving it elsewhere | **Remove** | Delete |
| Begin a service or process | **Start** | Launch |
| Run a command or job | **Run** | Execute |
| Advance in a stepped flow | **Next** | Continue |
| Confirm action | **OK** | Ok, Okay (always both caps: OK) |
| Save and retain the current context | **Save** | Save changes |
| Apply settings without leaving the context | **Apply** | Save changes |
| Complete and leave a flow | **Done** | Finish, Complete |

Full glossary: add · apply · approve · autosave · back · browse · cancel · clear · close · copy ·
create · delete · docs · done · download · edit · export · filter · find · import · learn more ·
log in · log out · move to trash · new · next · OK · preview · redo · refresh · reject · remove ·
reset · run · save · save as · search · send · show/hide · sign up · sort · start · top · undo ·
update · upload.

### Headings and navigation

- Front-load distinguishing terms: `AWS connection settings` not `Connection settings for AWS`.
- Use one clear H1 per page and a logical heading hierarchy.
- Keep navigation labels distinct, logically grouped, and ordered around user expectations.
- A destination label and page heading should normally match or be recognizably equivalent.
- Sentence case always. No periods in headings. No question format.
- Avoid ambiguous labels that depend on surrounding text to make sense.

### Forms

- Give every input a visible, persistent, nearby label. Typically 1–3 words, sentence case, no colon.
- Do not use placeholder text as the only label or the only source of essential guidance —
  it disappears when the user starts typing and may be skipped by screen readers.
- Put required formats and constraints near the input and keep them available after entry.
- Do not repeat the label in helper text; use helper text for necessary explanation or examples.
- Ensure error text identifies the affected field when that relationship is not already clear.

### Tooltips

- Use tooltips for supplemental information only — never for required or critical instructions.
- Give icon-only controls an accessible name; a visible tooltip reinforces it.
- Icon button tooltips: 1–2 words. Standard tooltips: 1–2 sentences maximum.

### Error messages

An effective error explains what happened and provides the most useful available next step.

- Avoid blame, alarmist adjectives (`fatal`, `catastrophic`), and unexplained technical details.
- State the problem specifically enough to distinguish it from other failures.
- Provide a recovery action when the user can recover.
- If no user action can resolve the problem, explain what will happen next or where support is
  available — do not invent a recovery step.
- Include enough context for the message to make sense when encountered with assistive technology.
- Use a link only when the required guidance does not fit in context.
- Only advise "Contact IBM Support" when the problem cannot be resolved any other way — use that
  exact phrase with a link to the IBM Support center.

Examples:
- ✅ `The email address wasn't found. Check the address and try again.`
- ✅ `Upload failed. Enter a valid upload URL.`
- ✅ `Changes couldn't be saved. Try again in a few minutes.`
- ❌ `You entered an incorrect email address.`
- ❌ `The scripting engine threw an exception.`

### Warnings and destructive actions

- Warn before an action with serious or irreversible consequences.
- State the consequence, affected object, and available alternative where relevant.
- Use precise action labels: `Delete project` rather than a vague `OK`.
- Do not exaggerate recoverable consequences as irreversible.

### Success messages

- Confirm the result briefly: `Project saved` or `Export complete`.
- Match the amount of celebration to the significance of the result.
- One exclamation mark is acceptable for a meaningful milestone — not every routine operation.

### Empty states

- Explain the state only when it is not self-evident.
- Help the user reach the first meaningful action.
- Account for permission, filtering, loading, first-use, and genuinely empty-data states —
  they may need different content.

### Notifications

Use a concise title that carries the primary meaning, supporting text that adds rather than repeats
information, and an action only when the user can or should act. Success notifications can be warm;
errors and warnings should be factual and economical.

### Links and alternative text

- Write link text that communicates its purpose outside the surrounding sentence.
  Avoid bare URLs, `click here`, and repeated generic `learn more` links.
- Describe the purpose or meaningful information of an image, not every visible detail.
- Use empty alternative (`alt=""`) for decorative images.
- For complex visuals, provide a concise alternative and place detailed explanation nearby.
- For functional icons, name the action or destination rather than the icon's shape.

---

## Accessibility writing requirements

These are writing requirements, not implementation requirements. Apply whenever writing headings,
labels, error messages, alt text, link text, or form guidance.

| Content type | Requirement |
| --- | --- |
| **Headings** | Succinct, sequential levels (H1→H2→H3, never skip), one H1 per page |
| **Alt text** | Describes purpose not appearance; decorative = alt=""; complex = short + detail nearby |
| **Input labels** | Visible, persistent, near input, concise; never rely on placeholder text |
| **Error messages** | Identify the problem and provide a correction, recovery action, or truthful next step; include enough context for screen-reader users |
| **Link text** | Meaningful out of context; unique; no "click here", "read more", or bare URLs |
| **Placeholder text** | Never the only label; never for critical guidance |
| **Page titles** | Unique per page; unique string first |
| **Video content** | Captions for audio; descriptions for meaningful visuals |
| **Consistency** | Same labels, icons, and navigation order across all pages |

---

## IBM Content Standard — 5 heuristics

Use these five lenses for structured reviews.

| # | Heuristic | Key checks |
| --- | --- | --- |
| 1 | **Content hierarchy** | Clear navigation; labels match headings; scannable structure; decision support |
| 2 | **Terminology** | IBM alignment; plain language; one term per concept; in-context definitions |
| 3 | **Content that guides** | Audience fit; task-flow support; active voice; action-oriented; contextual help |
| 4 | **Content that helps when stuck** | Warning messages; actionable errors; escalation links; help availability |
| 5 | **Formatting and style** | Carbon alignment; personality; readable layout; sentence case; action labels |

**Maturity scale** — use only when assessing a sufficiently complete experience, or when the user
asks for scoring. Do not assign a score to one isolated string.

| Level | Description |
| --- | --- |
| **0 — Inadequate** | Content prevents or seriously obstructs task completion |
| **1 — Minimal** | Task is possible but contains meaningful disruption |
| **2 — Good** | Experience is clear and usable with few material issues |
| **3 — Excellent** | Consistently clear, useful, human, and exemplary — moments of celebration, curiosity, and joy |

---

## Figma review workflow

### 1. Establish scope and context

Identify the frames, components, or flow in scope. Determine the user's goal and the expected order
of interaction. Note what cannot be inspected.

### 2. Inventory the experience

Map visible content by frame and component: page title, navigation, headings, descriptions, labels,
helper text, actions, links, empty states, errors, warnings, notifications, confirmations, and
accessible names when available.

Check relevant variants and states when present:

- default, selected, hover, focus, and disabled
- loading, progress, and completion
- first use, empty, filtered-empty, and no-permission
- validation, error, warning, and success
- modal, side panel, overflow, and responsive variants

### 3. Review the flow before individual strings

Check whether the sequence tells users where they are, what they can do, what will happen, and how
to recover. Look for conflicting terminology, missing decisions, duplicated guidance, unclear
consequences, and content that appears too late.

### 4. Apply the 5 IBM Content Standard heuristics

Run each of the five lenses across the scope (see above).

### 5. Separate finding types

Label each finding as one of:
- **Content** — the string itself
- **Interaction/context** — the string is correct but the placement, trigger, or flow is wrong
- **Visual/layout** — a layout constraint is causing the content problem
- **Implementation/accessibility** — a code or ARIA concern beyond copy

Rewrite content directly. For non-content findings, explain the issue without suggesting a copy
change will solve it.

### 6. Prioritize by user impact

- **Blocking** — prevents task completion, creates a serious accessibility barrier, or introduces
  material legal, safety, security, or irreversible-action risk.
- **High** — likely to cause errors, abandonment, misunderstanding, or failed recovery.
- **Medium** — increases cognitive load, weakens hierarchy, or creates noticeable inconsistency.
- **Low** — editorial polish with limited effect on comprehension or task success.

A sentence-case or preferred-word violation is not automatically blocking. Severity depends on
its effect in context.

### 7. Deliver findings

Use this table format:

| Priority | Frame | Element | Current text | Finding | Suggested text | Rationale |
| --- | --- | --- | --- | --- | --- | --- |

Then close with:

1. **Verdict:** Blocked · Major revision needed · Minor edits · No material issues
2. **Cross-screen issues:** terminology, hierarchy, tone, or state consistency
3. **Coverage gaps:** inaccessible frames, hidden states, absent requirements, or uncertain context
4. **Replacement copy:** consolidated ready-to-paste list when more than one string changes

- Quote the exact current string.
- Make the frame or screen locatable.
- Provide ready-to-paste replacement text.
- Group repeated systemic issues instead of reporting the same problem on every frame.
- Do not list compliant strings unless the user requests a complete scorecard.

---

## Generation workflow

When creating new content:

1. Determine the component, user goal, system state, consequence, and space constraints.
2. Draft the minimum content required to support the task.
3. Apply IBM voice, Carbon patterns, terminology, and accessibility guidance.
4. Check the string in relationship to surrounding labels, actions, and states.
5. Return one recommended version. Offer alternatives only when they represent a meaningful tone,
   terminology, or interaction tradeoff.
6. State assumptions that materially affect the copy.

---

## Relationship to other Bob skills

This skill orchestrates the full IBM content design stack. When a narrower skill is the better
choice, say so:

| Task | Better skill |
| --- | --- |
| Deep Carbon component query (needs live carbondesignsystem.com search) | `carbon-content-writer` |
| IBM style mechanics — capitalization, punctuation, highlighting | `ibm-brand-guidelines` |
| Accessible ARIA/focus management in code | `carbon-accessibility-practices` |
| Technical specification, runbook, or API doc review | `technical-writing-review` |
| Carbon component code generation | `carbon-builder` |

---

## Pre-publish checklist

- [ ] Sentence case throughout — no title case, no ALL CAPS
- [ ] US English spellings (authorize, behavior, canceled, center, organize)
- [ ] Active voice in instructions; passive only when it avoids blame
- [ ] Simple present tense (`Message sent`, not `Your message has been sent`)
- [ ] One term per concept — no synonyms for the same thing
- [ ] No jargon (abort, terminate, leverage, utilize, facilitate, socialize, synergy)
- [ ] Standard Carbon action labels used where available
- [ ] Error messages: specific problem, truthful recovery step, no blame, no alarming adjectives
- [ ] Warning messages alert to consequences before unrecoverable actions
- [ ] Labels visible, persistent, near inputs, no colon, typically 1–3 words
- [ ] Placeholder text never the only label; no critical info in placeholder
- [ ] Link text meaningful out of context; no "click here"
- [ ] Headings: one H1, sequential levels, succinct, sentence case, no period
- [ ] Navigation labels match page headings; typically 1–3 words; noun-based
- [ ] Button labels typically 1–2 words; verb-first; sentence case; standard Carbon label where available
- [ ] IBM voice: clear point of view, confident, fact-elevating, not poetic
- [ ] Tone matches the content type and user's emotional state
- [ ] Content feels engaging, helpful, and conversational
- [ ] Findings prioritized by user impact, not mechanical rule count
- [ ] No claims about uninspected Figma states or implementation details
