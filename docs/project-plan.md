# AI Grant Agent: Final Project Plan

**Project:** AI Grant Agent for IDEAS For Us
**Team:** Catalyst Collective (Charlotte Groton, Gabe Cioffi, Tristan Willing, Leonardo Takeshi Campi Kiyose), SE 395-2
**Version:** Final, after the team audit round (November 4, 2026)
**Built from:** the unified plan (council evaluation plus team decisions) and four audits:

| Audit | Author | Findings | Code used below |
|---|---|---|---|
| Scope creep | Leo | 17 | L1–L17 |
| Missing tasks | Tristan | 22 | M1–M22 |
| Wrong dependencies | Gabe | 13 | G1–G13 |
| Vague acceptance criteria | Charlotte | 11 | C1–C11 |

**Guiding rule (from the proposal):** *AI handles the volume; people make every commitment.* Nothing is applied before Clay or Caroline approve it.

---

## 1. What changed and why

### 1.1 In one paragraph

Outcome insights (T11) and Reviewer edits (T10) are **cut**. All four audits found that they were unbuildable, unneeded, or both, and cutting them frees 9 hours. Those hours, plus trims to other tasks, pay for the cheap safety fixes the audits found missing:
- a real approver identity
- approval tied to the exact version approved
- an "incomplete" state when a Claude call fails
- checker flags shown on the review screen
- test drafts with an answer key
- a dated handoff between every pair of dependent tasks
- a handoff that moves keys and accounts to IDEAS

Every acceptance criterion now names a concrete test. The budget is recomputed with half of Thanksgiving week removed.

### 1.2 Decision on every finding

**A** = accept · **M** = accept with changes · **R** = reject · **–** = moot, because the task it targets was cut.

| # | Finding(s) | Decision | How it is applied |
|---|---|---|---|
| 1 | Cut Outcome insights: L1, G11, C8, M10 (threshold part) | **A** | T11 removed. C8 and the threshold half of M10 are moot. "Insights after 5+ debriefs" goes on the post-handoff list. |
| 2 | T10 depends on an editor no task builds: L2, G3 | **A** | T10 removed. T4 gains "add an approved final answer to the voice pack," recording the approver and date. |
| 3 | Limit check retries are drafting: L3 | **A** | T8 limit check is pure code and only flags. |
| 4 | Voice rating and time-saving criteria no longer fit the tool: L4, C4, M7, C11 | **A** | T8 rates *flags*, yes/no per flag. T0 gets IDEAS to agree in writing on the timed segment, the formula and thresholds. T13 and T16 use only the agreed criteria. |
| 5 | Voice pack has no consumer: L5, M11 | **A** (M11 version) | The T3 context block can include up to 2 of Clay's examples. The T4 → T8 dependency is removed. |
| 6 | Checker and Conditions results never reach the Review Gate; drop reused passages: L6, M1, G4 | **A** | T6 shows T8 and T9 results stored on the record. The result format is frozen Fri Nov 20. Reused-passage detection is removed. |
| 7 | Grant-level layout view in T3: L7, G5 (layout part) | **A** | Removed from T3. Field order is noted in `docs/schema.md`. |
| 8 | T7 API option has no date; Runway "integration" doc: L8, G13 (date part) | **A** | API credentials must arrive by Fri Nov 13, or the option is closed. T7 documents only the CSV and copy-paste workflow. |
| 9 | T0 carries non-blocking subtasks: L9 | **A** | The Claude Corps check and the Runway scope split become two questions on the kickoff call, not subtasks. |
| 10 | Nobody owns the pilot project: L9, M8, G13 | **A** | T17 (Charlotte): candidate list by Fri Nov 13, confirmed by Fri Nov 20. Fallback: replay a past grant with its real deadline simulated. |
| 11 | Partner time is unplanned and spread across many asks: L10, M22, M14 | **A** | Four booked sessions, all on calendars by Sun Nov 8 (T17). Session 2 (Week 13) includes the Clay and Caroline walkthrough. |
| 12 | T15 duplicates T14; "without help" is undefined: L11, C10 | **A** | The T14 tester uses the T15 draft guide, with a zero-hint rule. The T15 criterion now points to T14. |
| 13 | Testing starts late and has no end: L12, M12, G2 | **A** | Each owner writes the floor tests for their own task inside their own hours. T12 is split into Part A (due at the Fri Dec 4 freeze, gates the pilot) and Part B (Week 14, gates handoff). |
| 14 | No test drafts or answer key: M3, C3, C5 | **A** | Tristan (not Gabe) writes the T8 test drafts and key by Fri Nov 13. T0 gets an answer key for the 5 seeded conditions from IDEAS. A condition counts as caught only when the clause, location and conflict decision all match. |
| 15 | Run-time measurement in T9: L13 | **A** | Dropped. |
| 16 | "12 unsubmitted drafts" no longer exist: L14 | **A** | T5 now refers to "T2 discovery drafts (4–6)." |
| 17 | Hosting and deployment: L15, M5 | **M** | Local by default: the app runs on one team laptop. If IDEAS names a host by Fri Nov 13, deploying takes 2 h from the reserve. No host means hosting becomes a handoff decision for JayBird. |
| 18 | Cut-first order gives up the partner's request: L16 | **A** | New order in Section 9. The AI-sentence flagger is now last to cut. |
| 19 | Never asked "drafts or checker?"; no Claude-failure state: L17, M6 | **A** | The question goes on the T0 kickoff call. The T1 wrapper returns "incomplete," and T6 blocks Approve until checks re-run. |
| 20 | No intake for drafts or guidelines: M2 | **A** | Paste screens in T8 and T9. T9 records the largest guideline tested. |
| 21 | "Named reviewer" has no identity: M4 | **A** | T1: shared app password, and each person picks their name from `config/approvers.yaml`. Only listed approvers see Approve. |
| 22 | Handoff transfers no keys or accounts: M9 | **A** | T15 moves the repo, key and host (if any) to IDEAS accounts, rotates the key, and gets written acceptance from the named owner. |
| 23 | Import IDEAS's existing Airtable records: M10 (import part) | **R** | 1.5 h for a non-floor feature. The Tracker starts with new submissions plus the $4.7M debrief. Import goes on the post-handoff list. |
| 24 | No backup or restore: M13 | **M** | T1 adds a backup script (dated copy of the database). T12 runs one restore test. No scheduler is built. |
| 25 | No calendar dates; Thanksgiving not in the hours: M15 | **A** | Dates mapped in Section 2 and confirmed in T0. The budget is 120 h, not 128. |
| 26 | Data handling not built in: M16 | **M** | The T0 data-rules section covers what is sent, logged and retained. `docs/schema.md` records it. T12 verifies it. No separate checklist task. |
| 27 | Prompts and model not versioned: M17 | **A** | Prompts live as files in `src/prompts/`. The model name is pinned in config. Any change to either re-runs the seeded tests (T12). |
| 28 | No hostile-text test: M18 | **A** | T12 checklist item. |
| 29 | Funder type not recorded: M19 | **A** | New T5 field. |
| 30 | Reviewers not told what was checked: M20 | **A** | A fixed note on the T6 review screen. The reviewer checklist goes in the T15 guide. |
| 31 | Course deliverables beyond the report: M21 | **A** | T17 confirms the list with the professor in Week 9. Any extra deliverable comes from the reserve. |
| 32 | Pilot dependencies are wrong: G1 | **A** | T13 depends on the floor plus T12 Part A, T14 and T0. T7 is "include if done." |
| 33 | T4 and T5 missing their T0 links: G5, G6 | **A** | Added (data rules, Clay's grants, Airtable columns, win rule). |
| 34 | T3 and T9 do not depend on T2: G7 | **A** | Both depend on the T2 friction summary, due Fri Nov 6. |
| 35 | Seeded-condition fallback has no cut-off: G8 | **A** | If IDEAS has not sent the conditions by Fri Nov 6, Charlotte builds the fallback set from T2 by Fri Nov 13. |
| 36 | "Depends on" overlaps in the same week: G9 | **A** | Section 5 names every handoff item, its owner and its date. |
| 37 | Caroline's examples are never collected; T8 missing its T0 link: G10 | **A** | T0 collects them by Fri Nov 13. T8 depends on T0. |
| 38 | T16 dependencies: G12 | **A** | T16 depends on T0, T12, T13 and T14. |
| 39 | Feature freeze overlaps T10/T11: G13 (freeze part) | **–** | Moot: T10 and T11 are cut. |
| 40 | Win ratio is undefined: C1 | **A** | Proposed rule in T5, confirmed by Clay or Caroline in T0. Tested on a fixture. |
| 41 | An approval survives later edits: C2 | **A** | Approval is bound to a version. Changing the draft or amount voids it (T6). |
| 42 | When does the 10-minute clock stop: C6 | **A** | Defined in T3. |
| 43 | Airtable import can hold wrong values: C7 | **A** | Field-by-field value test in T7. |
| 44 | "High severity" is undefined: C9 | **A** | Release blockers defined in T12 before any check runs. |

**Totals (44 rows):** 39 accepted · 3 accepted with changes · 1 rejected · 1 moot. Several rows cover more than one finding, and all 63 findings appear above.

---

## 2. Calendar and budget

**Assumed dates** (confirmed on the T0 kickoff call). The team is in **Week 9** as of Wed Nov 4.

| Week | Dates | Notes |
|---|---|---|
| W8 | Oct 26 – Nov 1 | Complete |
| W9 | Nov 2 – Nov 8 | **Now.** T0, T1 and T2 handoffs due this week |
| W10 | Nov 9 – Nov 15 | Checkpoint 1 (Fri Nov 13) |
| W11 | Nov 16 – Nov 22 | Feedback session 1 |
| W12 | Nov 23 – Nov 29 | **Thanksgiving: half capacity.** Checkpoint 2 (Wed Nov 25) |
| W13 | Nov 30 – Dec 6 | Session 2, cold-user test, feature freeze (Fri Dec 4) |
| W14 | Dec 7 – Dec 13 | Pilot. Checkpoint 4 (Fri Dec 11) |
| W15 | Dec 14 – Dec 20 | Handoff, final presentation and report |

**Budget:** 4 people × 4 h × 8 weeks = 128 h, minus 2 h each for Thanksgiving week = **120 h available.**
**Committed:** 115 h · **Reserve:** 5 h. The optional deploy (2 h) and any extra course deliverable come out of the reserve.

---

## 3. Hours by owner

| Owner | Tasks | Hours | Capacity |
|---|---|---|---|
| Leo | T0, T3, T15, T16 | 29 | 30 |
| Gabe | T1, T7, T8, T9 prompt review (1 h), T14 | 30 | 30 (full; no slack) |
| Tristan | T5, T6, T12 | 28 | 30 |
| Charlotte | T2, T4, T9, T13, T17 | 28 | 30 |
| **Total** | | **115** | **120** |

### Changes from the unified plan

| Task | Was | Now | Why |
|---|---|---|---|
| T0 Kickoff | 6 | 7 | Answer key, success-criteria agreement, win rule, Caroline's examples (#4, #14, #37, #40) |
| T1 Foundation | 10 | 11 | Identity, failure state, prompt files, backup script (#19, #21, #24, #27) |
| T3 Profile | 9 | 8 | Layout view removed (#7) |
| T4 Voice pack | 4 | 2.5 | Storage only, plus approved-answer entry (#2, #5) |
| T6 Review Gate | 8 | 10 | Shows checker results, version-bound approval, incomplete-check block, checked-items note (#6, #19, #30, #41) |
| T7 Airtable | 4 | 3 | CSV only; API closed unless credentials by Nov 13; moved to Gabe (#8) |
| T8 Draft Checker | 12 | 13 | Paste intake and own floor tests; retry and voice rating removed (#3, #4, #13, #20) |
| T9 Conditions | 12 | 13 | Paste intake, own floor tests, Gabe's prompt review; run-time measure removed (#13, #15, #20) |
| T10, T11 | 9 | 0 | Cut (#1, #2) |
| T12 Regression | 7 | 6 | Owners write their own tests; T12 keeps test drafts, blockers and checklist (#13, #14) |
| T13 Pilot | 7 | 6 | Uses the agreed timed segment only (#4) |
| T14 Cold-user | 2 | 2 | Moved to Gabe, a non-author of the screens under test |
| T16 Report | 7 | 6 | Results table fed by T12 records |
| T17 Cadence | 3 | 4.5 | Pilot project, session booking, course deliverables (#10, #11, #31) |

---

## 4. Build order

| Task | Owner | Hours | W8 | W9 | W10 | W11 | W12 | W13 | W14 | W15 |
|---|---|---|---|---|---|---|---|---|---|---|
| T0 Kickoff and partner inputs | Leo | 7 | ■ | ■ | ■ | | | | | |
| T1 App foundation | Gabe | 11 | ■ | ■ | | | | | | |
| T2 Light discovery and friction log | Charlotte | 3 | ■ | ■ | | | | | | |
| T3 Project Profile | Leo | 8 | | ■ | ■ | | | | | |
| T4 Voice pack | Charlotte | 2.5 | | ■ | ■ | | | | | |
| T5 Tracker | Tristan | 12 | | | ■ | ■ | | | | |
| T8 Draft Checker | Gabe | 13 | | | ■ | ■ | ■ | | | |
| T9 Conditions Check | Charlotte (+Gabe 1 h) | 13 | | | ■ | ■ | ■ | | | |
| T6 Review Gate and export block | Tristan | 10 | | | | ■ | ■ | | | |
| T7 Airtable CSV export | Gabe | 3 | | | | | ■ | | | |
| T12 Regression and security | Tristan | 6 | | ■ | ■ | ■ | ■ | ■ | ■ | |
| T14 Cold-user test | Gabe | 2 | | | | | | ■ | | |
| T13 Pilot | Charlotte | 6 | | | | | | | ■ | |
| T15 Handoff | Leo | 8 | | | | | | ■ | ■ | ■ |
| T16 Final presentation and report | Leo | 6 | | | | | | | | ■ |
| T17 Weekly cadence | Charlotte | 4.5 | ■ | ■ | ■ | ■ | ■ | ■ | ■ | ■ |

T0 runs into Week 10 only for inputs with a Week 10 due date (see Section 5).

---

## 5. Handoffs (what moves between tasks, and when)

"Depends on" means the named item has arrived, not that the whole upstream task is finished (G9).

| Due | Item | From | To | If late |
|---|---|---|---|---|
| Thu Nov 5 | Development Claude API key + named key owner | T0 (Leo) | T1 | Gabe uses a team key with a $10 cap until the IDEAS key arrives |
| Fri Nov 6 | Data rules (send / log / retain; NDA yes or no) | T0 | All | No real IDEAS record is loaded until received |
| Fri Nov 6 | Approver names | T0 | T1 config | Placeholder names; approval tests use them |
| Fri Nov 6 | Restriction list | T0 | T3, T9 | Chase daily; Checkpoint 1 fails if still missing Nov 13 |
| Fri Nov 6 | 5 seeded conditions + answer key | T0 | T9 | Charlotte builds the fallback set from T2 by Fri Nov 13 |
| Fri Nov 6 | `docs/schema.md` reviewed by all four; storage module running | T1 (Gabe) | T3, T4, T5, T6 | Builders code against the draft schema; changes go through Gabe |
| Fri Nov 6 | Friction summary tagged → T3 / → T9 | T2 (Charlotte) | T3, T9, T0 fallback | T3 and T9 start from the proposal's friction points |
| Fri Nov 13 | Airtable column list and field types; win-counting rule confirmed | T0 | T5, T7 | T5 uses the proposed rule, marked "unconfirmed" |
| Fri Nov 13 | Caroline's AI-phrase examples | T0 | T8 | Flagger starts from the friction-log quotes only |
| Fri Nov 13 | Agreed timed segment, formula and thresholds | T0 | T13, T16 | Pilot reports raw times, marked "unverified" |
| Fri Nov 13 | JayBird API credentials, or none | T0 | T7 | API option closed; CSV only |
| Fri Nov 13 | Host named, or none | T0 | T1 deploy (optional) | Local laptop for the pilot |
| Fri Nov 13 | Profile facts and restriction table working | T3 (Leo) | T8, T9 | Checkpoint 1 fails |
| Fri Nov 13 | T8 test drafts + answer key | T12 (Tristan) | T8 | T8 floor test cannot pass Checkpoint 2 |
| Fri Nov 13 | Pilot candidate list (2–3 grants) | T17 (Charlotte) | T13 | – |
| Fri Nov 20 | Check-result format frozen (fields stored on the record) | T8, T9 | T6 | T6 integration slips into Week 13 and the freeze is at risk |
| Fri Nov 20 | Baseline timing of the agreed segment | T0 | T13 | Labeled "estimated" |
| Fri Nov 20 | Pilot project confirmed | T17 | T13 | Fallback: replay a past grant |
| Wed Nov 25 | `export()` enforcing approval | T6 (Tristan) | T7 | T7 slips to Week 13 |
| Wed Dec 2 | Draft guide (use and review sections) | T15 (Leo) | T14, Session 2 | T14 runs on labeled controls only |
| Fri Dec 4 | T12 Part A: zero open release blockers | T12 | T13 | Pilot does not start |

---

## 6. Checkpoints

Each checkpoint has a runnable pass/fail test. Charlotte records the result in the weekly note and tells Clay the same day if anything is cut.

| Checkpoint | Date | Pass test | If it fails |
|---|---|---|---|
| 1 | Fri Nov 13 | T3 floor tests pass. Schema stored. Restriction list received. Seeded conditions received or fallback ready | Reserve hours go to T3. T4 context-block examples are dropped |
| 2 | Wed Nov 25 | T6: unapproved, denied and changed-version exports all refused. T8: zero planted errors missed. T9: 5 of 5 against the answer key | Next item in the cut order (Section 9) |
| 3 | Fri Dec 4 | T12 Part A has zero open blockers. T14 passes with zero hints. **Feature freeze** | Pilot delayed to Wed Dec 9; T16 written around the delay |
| 4 | Fri Dec 11 | Pilot run and the decider's pass/fail recorded | Report the pilot as incomplete, with evidence of what ran |

---

## 7. Tasks

Every task answers three questions: **Build** (what exactly is produced), **Needs before start**, and **Done when** (the test that proves it).

### Phase 1. Set-up and foundation (Weeks 8–10)

#### T0 · Kickoff and partner inputs

**Owner:** Leo · **Estimate:** 7 h · **When:** W8–W10 (most items due Fri Nov 6 or Fri Nov 13) · **Depends on:** none

**Build:** one document, `docs/partner-inputs.md`, with a fixed section for each input below. Each section holds the value received, or "pending," a chase date and the IDEAS person responsible. The restriction list, seeded conditions, Airtable columns and Clay's grants go in `data/partner/`, or in a location IDEAS approves if the data rules forbid the repo.

**Needs before start:** a 30-minute kickoff call with Clay or Caroline, and a 15-minute call with JayBird. Book both by Thu Nov 5.

**Subtasks:**
- [ ] **Approvers:** names of everyone who may approve (→ `config/approvers.yaml`) and the go/no-go decider
- [ ] **Data rules:** what may be sent to the Claude API, what may be logged, how long drafts are kept, whether an NDA is needed
- [ ] **Keys and hosting:** API key owner, monthly cost cap in dollars, host name or "none"
- [ ] **Restriction list**, plus the **5 seeded conditions with an answer key**: for each, the expected clause, source location, and the IDEAS restriction it conflicts with, or "no conflict." If not received by Fri Nov 6, the T2 fallback is used.
- [ ] **Airtable column list** with field types (for T5 and T7)
- [ ] **Clay's five grants** (for T4) and **Caroline's AI-phrase examples** (for T8)
- [ ] **Success-criteria agreement**, in writing from the decider:
  - the timed segment (proposed: from opening a completed draft to recording a review decision)
  - the formula: (baseline − pilot) ÷ baseline × 100
  - whether the 30% target applies to that segment
  - the flag-usefulness pass fraction for T8
  - whether a voice rating is still wanted
- [ ] **Win-counting rule** (proposed in T5) confirmed
- [ ] **Baseline timing** of the agreed segment, labeled measured or estimated (by Fri Nov 20)
- [ ] **JayBird:** API credentials by Fri Nov 13, or the T7 API option is closed
- [ ] **On the call:**
  - Do you want generated drafts, or only a checker?
  - Is Claude Corps building anything similar?
  - Is the Runway scope split as we understand it?
  - Are the Week 8–15 dates in Section 2 right?
- [ ] Clay's written acknowledgement that the **Tracker is the first priority**

**Done when:**
- `docs/partner-inputs.md` has no empty section: every item has a value, or a chase date and an owner
- Clay or Caroline has replied "confirmed" to an email summarizing the approvers, data rules, success criteria and win rule. The reply is saved in `docs/`.
- The approver list is in Gabe's hands by Fri Nov 6
- The baseline is recorded and labeled

---

#### T1 · App foundation

**Owner:** Gabe · **Estimate:** 11 h · **When:** W8–W9 (schema and storage by Fri Nov 6) · **Depends on:** a development API key from T0 (Thu Nov 5). Not on hosting: the app runs locally by default.

**Build:**
- `src/app.py`: Streamlit app with pages Profile, Conditions Check, Draft Checker, Review, Tracker
- `src/llm.py`: one function that loads a prompt from `src/prompts/<name>.md`, calls Claude with the model name pinned in `config/settings.toml`, and appends tokens and cost to `logs/cost.csv`. On an error or timeout it returns status `incomplete`; it never returns an empty result as if it succeeded.
- `src/storage.py`: SQLite behind `save / get / list / export`. `export()` lives here so T6 can enforce approval in one place.
- `docs/schema.md`: record shapes (project, fact, restriction, application, check_result, review), the field order for screens, and the T0 data rules
- Sign-in: a shared app password, then each person picks a name from `config/approvers.yaml`. Only names listed as approvers can see Approve.
- `scripts/backup.sh`: copies the database to a dated file in a second folder
- README, `.env.example`, `requirements.txt`, and a pre-commit secrets scan

**Needs before start:** the development API key (T0, Thu Nov 5). Approver names (Fri Nov 6) can start as placeholders.

**Subtasks:**
- [ ] App shell, README, `.env.example`, `requirements.txt`, pre-commit secrets scan
- [ ] `llm.py` with prompt files, pinned model, cost log and the `incomplete` status
- [ ] `storage.py` with `export()`, plus `docs/schema.md` reviewed by all four (by Fri Nov 6)
- [ ] Sign-in and approver list
- [ ] `backup.sh`
- [ ] Floor tests for the items below in `src/tests/`
- [ ] *Optional, from the reserve (2 h):* deploy to the IDEAS host if one is named by Fri Nov 13

**Done when** (each is a test in `src/tests/` or a recorded check):
- A teammate other than Gabe runs the app from a fresh clone using only the README
- One test call adds a row to `logs/cost.csv` with tokens and cost
- A simulated API failure returns `incomplete`
- A saved record is still there after the app restarts
- The secrets scan blocks a commit containing a fake key
- A non-approver name does not see Approve
- `backup.sh` produces a dated copy
- All four have marked `docs/schema.md` reviewed

---

#### T2 · Light discovery and friction log

**Owner:** Charlotte · **Estimate:** 3 h · **When:** W8–W9 (summary due Fri Nov 6) · **Depends on:** none

**Build:**
- `discovery/findings/friction-log.md`: one row per grant with these columns:
  - grant and funder
  - date
  - minutes spent finding, briefing, drafting and editing
  - context re-entered
  - conditions or restrictions nearly missed (quoted)
  - AI-sounding sentences (quoted)
  - notes
- `discovery/findings/friction-summary.md`: each requirement it suggests, tagged → T3 or → T9

**Needs before start:** Charlotte's Runway login. Nothing else.

**Subtasks:**
- [ ] Create the log template with the columns above
- [ ] Work 4–6 grants in the Runway to "ready for review" and fill one row per grant
- [ ] Present three grants at the next IDEAS meeting and log the feedback in the notes column
- [ ] Write the summary. Pull out any funder conditions found as a fallback set for T0.

**Done when:**
- At least 4 rows, with every column filled ("none" counts as filled)
- The summary has at least one item tagged → T3 and one tagged → T9, or says "none found" for that task
- Three grants were shown at an IDEAS meeting, with feedback logged
- The drafts are labeled "test data" for T5

---

#### T3 · Project Profile

**Owner:** Leo · **Estimate:** 8 h · **When:** W9–W10 (working by Fri Nov 13) · **Depends on:** T1 storage and schema (Nov 6), T0 restriction list (Nov 6), T2 summary (Nov 6), T4 examples (optional)

**Build:** the Profile page:
- 8-parameter intake form (drop-downs and text boxes only)
- facts editor in which every fact shows a last-updated date, with a stale tag after 12 months (a fixed constant in code)
- restriction list import (paste or CSV) and an editable table
- one-click context block with a copy button, optionally including up to 2 of Clay's examples from T4

**Subtasks:**
- [ ] Intake form
- [ ] Facts editor with dates and the stale tag
- [ ] Restriction list import and table
- [ ] Context block and copy button
- [ ] Floor tests in `src/tests/`
- [ ] Timed intake with a staff member at Session 1 (Week 11)

**Done when:**
- **Ten-minute test (C6):** a staff member gets the approved facts for a past project. The clock starts when they open a blank form and stops when all 8 parameters are saved. The result must be **under 10 minutes.** Report the elapsed time.
- **No re-briefing test:** the saved context block, pasted into the Runway, contains all 8 inputs, and no supplied fact had to be entered twice
- Every stored fact shows its date, and a fact dated 13 months ago shows the stale tag
- IDEAS's restriction list imports, is edited, saves and reloads unchanged

---

#### T4 · Voice pack

**Owner:** Charlotte · **Estimate:** 2.5 h · **When:** W9–W10 · **Depends on:** T1 (Nov 6), T0 data rules and Clay's grants (Nov 6)

**Build:**
- storage for Clay's five grants as plain text (paste or .txt)
- an "add approved final answer" form that records the approver's name and date (replaces the cut T10)
- a selector for T3's context block

**Subtasks:**
- [ ] Store and list the five grants
- [ ] Approved-answer form (approvers only)
- [ ] Expose up to 2 selected examples to T3

**Done when:**
- All five grants are stored, and each is character-for-character identical to its source after a save and reload
- An approved answer saves with the approver's name and date
- A non-approver cannot add one

---

### Phase 2. The floor: Tracker, Review Gate, export (Weeks 10–12)

#### T5 · Tracker

**Owner:** Tristan · **Estimate:** 12 h · **When:** W10–W11 · **Depends on:** T1 schema (Nov 6), T0 data rules (Nov 6), Airtable columns and win rule (Nov 13)

**Build:** Tracker records and page.
- **Fields:** grant, funder, **funder type** (federal / state / foundation / local / corporate), amount, deadline (shown as a column), status, submitted date, decision date, funder contact, response date, debrief score, debrief notes, test-data flag
- **Monthly view:** count and win ratio

**Proposed win rule (C1, confirmed in T0):**
- Submissions are counted by submission month.
- Win ratio = wins ÷ (wins + losses), shown with its sample size.
- Pending, no-reply and test records are excluded from the ratio.
- With zero decisions the page shows "No decisions yet."

**Subtasks:**
- [ ] Record fields and page
- [ ] Monthly count and win ratio per the rule
- [ ] Load the $4.7M / 84-of-100 debrief (after the data rules), plus the T2 discovery drafts (4–6) flagged as test data
- [ ] Floor tests

**Done when:**
- **Fixture test:** a month with 2 wins, 1 loss, 1 pending and 1 unsubmitted test draft displays **"4 submissions, 67% (2 of 3 decisions)."** A month with no decisions displays **"No decisions yet."**
- Every field saves and reloads
- The real debrief shows score 84 and its notes
- Test-data records never appear in counts or exports

---

#### T6 · Review Gate and hard export block

**Owner:** Tristan · **Estimate:** 10 h · **When:** W11–W12 (core by Wed Nov 25) · **Depends on:** T5 records (Nov 20), T1 sign-in, T8 and T9 result format (Nov 20)

**Build:**
- Approve and deny buttons, shown to listed approvers only
- Each approval stores the reviewer's name, time and the **version** approved: a hash of the draft text and amount (C2)
- `export()` refuses any record whose current version is not approved
- The review screen shows the T8 flags and T9 conflicts stored on the record
- If any check is `incomplete`, Approve is disabled until the check is re-run
- A fixed note lists what the tool checked and what it did not (M20)

**Subtasks:**
- [ ] Approve and deny with name, time and version
- [ ] Version check inside `export()`
- [ ] Show T8 and T9 results; disable Approve on `incomplete`
- [ ] Fixed "what was checked" note
- [ ] Floor tests, calling `export()` directly

**Done when:**
- Exporting a denied or unreviewed record directly fails every time
- **Changed-version test (C2):** approve a sample, export it, and confirm the exported amount equals the approved amount. Change the amount and export again: **refused** until an approver approves the new version. The recorded reviewer and time match the exported version.
- A record with an `incomplete` check cannot be approved
- T8 flags and T9 conflicts are visible on the review screen for the test record
- If the gate misses Checkpoint 2, it fails visibly. There is no log-only fallback.

---

#### T7 · Airtable CSV export

**Owner:** Gabe · **Estimate:** 3 h · **When:** W12 · **Depends on:** T6 `export()` (Wed Nov 25), T0 Airtable columns (Nov 13)

**Build:** a CSV whose columns match IDEAS's Airtable list, produced only through `export()`. A short section for the T15 guide on the CSV import and copy-paste workflow. The API path is built only if JayBird sent credentials by Fri Nov 13; otherwise "closed" is recorded in `docs/partner-inputs.md`.

**Subtasks:**
- [ ] CSV built from the column list
- [ ] Value-level test
- [ ] Guide section

**Done when (C7):** an approved sample with deliberately different dates and debrief score 84 is exported and imported into an Airtable test base. Every mapped field matches its source, an empty field stays empty, and an unapproved control record is absent from the CSV.

---

### Phase 3. Drafting safeguards (Weeks 10–12)

#### T8 · Draft Checker (flags, never rewrites)

**Owner:** Gabe · **Estimate:** 13 h · **When:** W10–W12 (result format frozen Fri Nov 20) · **Depends on:** T1 `llm.py`, T3 facts (Nov 13), T0 Caroline's examples and flag pass fraction (Nov 13), T12 test drafts and answer key (Nov 13)

**Build:**
- **Paste screen** for the draft, the funder question and the character or word limit
- **Limit check** in plain code: it flags only, with no retry
- **Invented-fact check:** numbers, dates and names are matched against Profile facts in code first, then by one model pass. Each unsupported claim is flagged individually.
- **Gap flag** for any question the profile cannot answer
- **AI-sentence flagger:** a pattern list from Caroline's examples plus one Claude pass. Each flag gives a reason and can be dismissed.
- **Storage:** results are saved on the record in the frozen format. The draft text is never modified.

**Subtasks:**
- [ ] Paste screen
- [ ] Limit check
- [ ] Invented-fact check
- [ ] Gap flags
- [ ] AI-sentence flagger
- [ ] Freeze the result format and hand it to T6 (Fri Nov 20)
- [ ] Floor tests against the T12 drafts
- [ ] Caroline rates the flags at Session 1

**Done when:**
- **Planted-error test (C3):** a draft with a wrong budget, a wrong date, an unsupported name, one correctly sourced figure and one unanswerable question gets the following result:
  - each of the three errors is flagged individually
  - the sourced figure is **not** flagged
  - the question is flagged as a gap
  - the draft text is byte-identical before and after
- On all T12 test drafts, **zero planted errors are missed**
- 100% of over-limit answers are flagged
- **Flag usefulness (C4):** Caroline answers yes/no to "Did this flag identify a specific phrase you would change?" for each flag on a saved sample. The yes-fraction meets the pass fraction IDEAS set in T0. Any rating of the overall draft is reported separately.

---

#### T9 · Conditions Check

**Owner:** Charlotte (12 h) with Gabe's prompt review (1 h) · **Estimate:** 13 h · **When:** W10–W12 (result format frozen Fri Nov 20) · **Depends on:** T0 restriction list and seeded conditions with answer key (Nov 6; fallback by Nov 13), T3 restriction table (Nov 13), T2 summary (Nov 6), T1 `llm.py`

**Build:**
- **Paste screen** for funder guidelines, recording the largest guideline tested
- **Extraction:** each condition is quoted with a source pointer (section heading or paragraph number)
- **Quote check in code:** every quote must be an exact substring of the pasted guideline, or it is dropped and flagged
- **Conflicts first:** conflicts with the restriction list are shown first, with the funder text beside the restriction
- **AI-use rules:** a keyword scan plus one prompt line surface candidate AI-use rules for a human to confirm
- **Storage:** results are saved on the record in the frozen format

**Subtasks:**
- [ ] Paste screen; test with the longest real guideline from T2 and record its size
- [ ] Extraction with source pointers
- [ ] Exact-substring check
- [ ] Conflict comparison
- [ ] AI-use scan
- [ ] Gabe reviews the prompts (1 h)
- [ ] Freeze the result format and hand it to T6 (Fri Nov 20)
- [ ] Floor tests: seeded conditions and NIH

**Done when:**
- **Seeded test (C5):** a condition counts as caught only when the clause, source location and conflict decision all match the T0 answer key. A second reviewer opens each pointer. The result must be **5 of 5.**
- Every displayed quote is an exact substring of its source (automated)
- The NIH NOT-OD-25-132 language is flagged, and three guidelines with no AI policy are not
- The largest guideline size tested is recorded in the guide

---

### Phase 4. Verify, pilot, hand off (Weeks 9–15)

#### T12 · Regression and security

**Owner:** Tristan · **Estimate:** 6 h · **When:** W9–W14 · **Depends on:** each task's floor tests (written by its owner)

**Build:**
- **T8 test drafts and answer key:** 10–12 drafts with planted false numbers, dates and names, written by Tristan, not Gabe. Due Fri Nov 13.
- **Release blockers, defined before any check runs (C9):**
  - a non-approver can approve
  - an unapproved or changed-version record exports
  - a key is exposed
  - prohibited community personal data is stored
  - an `incomplete` check allows approval
- **Checklist** (`docs/security-checklist.md`), with expected result, actual result and tester for each item:
  - secrets scan
  - non-approver approve attempt
  - unapproved and changed-version export attempts
  - data rules (what is sent, logged and retained) (M16)
  - a guideline with embedded instructions leaves the T9 flags unchanged (M18)
  - backup restore (M13)
  - re-running the seeded tests after any prompt or model change (M17)
- **Part A** is due at the Fri Dec 4 freeze and is run by a non-author. **Part B** in Week 14 re-runs all floor tests after the pilot fixes.

**Done when:**
- Every checklist row has an expected result, an actual result and a tester
- **Zero open release blockers** at Part A and Part B
- A blocker is closed only after the failed check passes on a re-run

---

#### T14 · Cold-user test

**Owner:** Gabe · **Estimate:** 2 h · **When:** W13 (by Fri Dec 4) · **Depends on:** T3, T6, T15 draft guide (Wed Dec 2)

**Build:** one observed session (C10). An unfamiliar tester, ideally an IDEAS intern, gets:
- the draft guide
- a sample project
- an approver test name

They save a complete profile and record a review decision on a sample draft. Allowed help: the guide and labeled controls. Observer hints are not allowed.

**Done when:**
- Both results can be reopened and verified
- **Zero observer hints** were given
- The step where any hint was needed, or the tester got stuck, is logged
- Blocking issues are fixed before the pilot

---

#### T13 · Pilot on a live project

**Owner:** Charlotte · **Estimate:** 6 h · **When:** W14 · **Depends on:**
- the floor: T5, T6, the T8 invented-fact check, T9
- T12 Part A (Fri Dec 4)
- T14 blocking fixes
- T0 decider, agreed segment and baseline
- the T17 pilot project (Fri Nov 20)

T7 is included if done.

**Build:** one live grant run through the tool, with:
- a timing sheet for the agreed segment
- an issue log (severity, owner, status)
- the decider's written pass/fail

**Subtasks:**
- [ ] Run the grant
- [ ] Time the agreed segment
- [ ] Log issues and fix pilot-blocking ones only
- [ ] Get the decider's pass/fail

**Done when (C11):**
- Baseline and pilot minutes are recorded for the agreed segment, and the saving is computed as (baseline − pilot) ÷ baseline × 100
- An estimated baseline is labeled "estimated." If the steps cannot be compared, the result is marked "unverified."
- The decider's pass/fail is written down
- No blocking issue is open

---

#### T15 · Handoff

**Owner:** Leo · **Estimate:** 8 h · **When:** W13–W15 (draft guide by Wed Dec 2) · **Depends on:** T12 Part B, T13, T14 findings

**Build:**
- `deliverables/handoff/guide.md`, one guide covering:
  - use
  - the review checklist
  - what the tool checks and does not check
  - the CSV and copy-paste workflow
  - maintenance
  - the named IDEAS owner and failure contact
- **Transfer** of the repo, the API key and the host (if any) to IDEAS accounts, with the key **rotated**

**Subtasks:**
- [ ] Draft guide by Wed Dec 2, used in T14 and walked through with Clay and Caroline at Session 2
- [ ] Walk JayBird through the maintenance section
- [ ] Transfer and rotate the key
- [ ] Get the named owner's written acceptance
- [ ] Tag the final code in GitHub

**Done when:**
- The guide was used in T14 and every blocking gap found was fixed
- The named IDEAS owner has accepted in writing (saved in `docs/`)
- The old key is revoked and the new key is held by IDEAS
- A release tag exists in GitHub

---

#### T16 · Final presentation and report

**Owner:** Leo · **Estimate:** 6 h · **When:** W15 · **Depends on:** T0 agreed criteria, T12 results, T13, T14

**Build:**
- the report, with a results-versus-criteria table using the criteria agreed in T0
- a live demo
- a section on what was cut (Grant Finder, T10, T11) and why

The report and presentation lead with what IDEAS can use.

**Done when:**
- Every agreed criterion is marked met, not met or unverified, with a link to its evidence (test output, T12 checklist, T13 sheet)
- The demo runs live

---

### Running through all weeks

#### T17 · Weekly cadence, sessions and pilot project

**Owner:** Charlotte · **Estimate:** 4.5 h · **When:** W8–W15 · **Depends on:** none

**Build:**
- **A three-bullet weekly status note to IDEAS** (done / next / blockers), plus:
  - a risk line
  - a decisions-and-cuts line, which serves as the decision log
- **Four IDEAS sessions**, all booked on IDEAS calendars by Sun Nov 8:

  | Session | When | Purpose |
  |---|---|---|
  | Kickoff | W9 | Runs T0 |
  | Session 1 | W11 | T3 timed intake; T8 flag rating |
  | Session 2 | W13 | Guide walkthrough with Clay and Caroline |
  | Pilot | W14 | Runs T13 |

**Subtasks:**
- [ ] Book all four sessions
- [ ] Confirm the course's deliverable list with the professor in Week 9
- [ ] Pilot project: candidate list by Fri Nov 13, confirmed by Fri Nov 20, or the fallback (replay a past grant with its real deadline simulated)
- [ ] Record each checkpoint result, and tell Clay the same day if anything is cut

**Done when:**
- A note went out every week (8 notes)
- All four sessions were on calendars by Nov 8
- The pilot project or fallback was confirmed by Nov 20
- Each checkpoint result is recorded with its test output

---

## 8. Never cut

- T5 Tracker
- T6 Review Gate, including the version-bound approval and the `incomplete` block
- T8 invented-fact check, limit check and gap flags
- T9 seeded test and exact-quote check
- T12 Part A release blockers
- T13 Pilot

## 9. If hours run short (cut in this order)

1. The optional deploy (stay on the local laptop)
2. The T7 API path (already conditional)
3. T4 examples in the context block (keep storage)
4. The T9 AI-use keyword scan (the NIH test goes with it)
5. **Last:** the T8 AI-sentence flagger, which answers Caroline's stated concern

## 10. Cut from the plan

- **T10** Reviewer edits saved to the context pack (no editor exists; replaced by T4's approved-answer entry)
- **T11** Outcome insights (about one debrief on record; revisit after 5+)
- Grant Finder, its API client, source logging and source-mix report
- Go/no-go summary card
- Draft Builder, and any retry or regeneration inside the Checker
- Email notifications, deadline reminders, dashboard polish, Gmail delivery
- Role admin page, win/loss tagging, searchable documents, PDF/DOCX parsing
- Reused-passage detection
- Grant-level layout view in T3
- Run-time measurement in T9
- The 12-grant discovery round, the demo recording, a separate deliverables step
- Log-only Tracker fallback

## 11. Post-handoff list (deferred, not lost)

- Import IDEAS's existing Airtable grant records (M10)
- Outcome insights once 5 or more debriefs exist
- A hosted deployment, if none was named by Nov 13
- Reused-passage detection
- PDF/DOCX intake for long guidelines
- A named backup for Gabe's AI work. Partly covered: Charlotte and Tristan read the T8 and T9 prompts during review.

---

## 12. Specificity check: T0, T1, T2

Before saving, the first three tasks were checked against three questions.

| Task | (1) What exactly do I build? | (2) What do I need before I start? | (3) How do I know it is done? |
|---|---|---|---|
| **T0** | `docs/partner-inputs.md` with 12 named sections (one per subtask), plus a "confirmed" email from Clay or Caroline | Two calls booked by Thu Nov 5 (Clay or Caroline, 30 min; JayBird, 15 min) | No empty section (value, or chase date and owner); confirmation email saved; approver list with Gabe by Nov 6; baseline labeled |
| **T1** | 7 named files and folders (`app.py`, `llm.py`, `storage.py`, `schema.md`, `approvers.yaml`, `backup.sh`, README set) | A development API key (Thu Nov 5). Hosting is **not** needed, because the default is local | 8 named checks, each a test or recorded check, run by a non-author where stated |
| **T2** | `friction-log.md` with 9 defined columns and `friction-summary.md` with → T3 / → T9 tags | A Runway login | At least 4 complete rows; at least one tag per target task, or "none found"; 3 grants presented; drafts labeled as test data |

**What failed before these fixes:**
- **T0** produced no artifact. It was a list of conversations, and "acknowledged" had no record behind it.
- **T1** could not start until T0 picked a host. "All four reviewed" had no evidence, and "the persistent host" was undefined.
- **T2** never defined the friction-log columns. "Findings written into requirements" could not be checked.

All three now pass.

**Status note:** today (Wed Nov 4) is in Week 9, so the first handoffs fall on Thu Nov 5 and Fri Nov 6. If T0, T1 or T2 has not started, raise it at the next team check-in. The 5-hour reserve absorbs about one day's slip.

## 13. Open decisions that need IDEAS

These are raised on the T0 kickoff call. The plan proceeds on the defaults shown until they are answered.

| Question | Default until answered |
|---|---|
| Generated drafts, or only a checker? | Checker only |
| Which segment is timed, and does the 30% target apply? | Opening a completed draft → recording a review decision; result reported without a target |
| Is a voice rating still wanted? | No; flag usefulness only |
| Win-counting rule | The rule proposed in T5 |
| Host and key owner | Local laptop; team key with a $10 cap |
