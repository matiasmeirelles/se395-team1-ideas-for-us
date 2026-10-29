# Interview Log: Leo (Scope Priorities)

**Project:** AI Grant Agent for IDEAS For Us
**Interviewee:** Leonardo Takeshi Campi Kiyose (Leo)
**Interviewer:** Claude (Claude Code)
**Date:** October 29, 2026
**Angle:** Scope priorities
**Inputs reviewed before the interview:** Project Proposal (Oct 18, 2026, 11 pages); 10/26 IDEAS meeting notes (Clay and JayBird). *The presentation slides were referenced but not attached.*

---

## Contents

1. [Opening request](#1-opening-request)
2. [Interviewer's initial read](#2-interviewers-initial-read)
3. [Interview: questions and answers](#3-interview-questions-and-answers)
4. [Final project plan](#4-final-project-plan)

---

## 1. Opening request

> I have attached our project proposal document, presentation slides, and notes from our 10/26 meeting with IDEAS For Us (Clay and JayBird). Read them first.
>
> My team is building an AI Grant Agent that helps IDEAS For Us find, draft, approve, and track grant applications, working alongside their existing Runway and Airtable tools. We have 8 weeks left to build and deliver.
>
> Note: the 10/26 meeting showed that the Runway already handles grant finding, fit scoring, eligibility summaries, and rough drafts, and our team was asked to each take 3 grants to a ready draft inside the Runway. Factor this into scope.
>
> Interview me so we can create a detailed project plan. Ask me one question at a time. Wait for my answer before asking the next question. After 8-10 questions, generate a project plan with tasks broken into subtasks, build order and dependencies, acceptance criteria for each task, time estimates, and who owns each task.
>
> I am focusing on the scope priorities angle. Ask me questions from that perspective.

### 10/26 IDEAS meeting notes (as provided)

1. If someone faces a challenge or bug, don't wait till the next meeting. Reach out whenever, no matter the time.
2. Toggle a specific grant so everyone else sees that you're working on the grant.
3. 1st task:
   1. Communicate which grant/series you want to take on.
   2. If it makes a good rough draft rapidly, do 3 grants each to get to the finish line.
4. Login process:
   1. Ongoing runway that updates daily; sees if any database companies have new grants.
   2. Checks with past grants, gives you fit % and grant amount.
   3. Look at packets (up to $1M); be able to edit the rough draft it gives you.
   4. When you find one you identify, you can click and learn more about its mission and project alignment.
   5. If it aligns, half the work for the draft is done.
   6. Go to the application and it will give you info about the company and mission.
   7. NOTHING applied before approval.
   8. If it looks real and right, send it to Clay or Caroline for review.
   9. Gives you summary and eligibility.
   10. Funding and grant opportunities.

**Checklist:** get logged in · select 3 grants · begin playing around with the tool · any bugs or hurdles, reach out right away · aim to have 3 ready to present next week.

---

## 2. Interviewer's initial read

After reading the proposal and the meeting notes, Claude summarized the scope tension:

> The 10/26 meeting overlaps heavily with the proposal. The Runway already does what the **Grant Finder**, the **eligibility part of Conditions Check**, and much of the **Draft Builder** were meant to do. What the Runway doesn't do yet: the **Review Gate and Tracker** (Clay called it the "one thing to definitely build"), restriction checks that quote their source, flagging AI-sounding text, and a written approval process.

---

## 3. Interview: questions and answers

### Q1. Which pieces does the Runway overlap make obsolete?

Here are the five proposal components and how much the Runway now covers each:

| Component | Runway overlap |
|---|---|
| Project Profile (8-parameter intake + context pack) | Partial (unclear if Runway stores project context) |
| Grant Finder (ranked shortlist) | **Heavy** (daily runway, fit %, amount) |
| Conditions Check (quoted funder conditions vs. restriction list) | Partial (Runway gives "summary and eligibility," not IDEAS's restriction list) |
| Draft Builder (limits, gap flags, AI-sentence flags) | **Heavy** (Runway gives an editable rough draft) |
| Review Gate + Tracker (approve/deny, Airtable export, win ratio) | **None** |

How would you sort each one?
- **Keep:** build it as planned
- **Reshape:** build it as an add-on to the Runway instead of a standalone piece
- **Cut:** drop it

Put another way: are you open to cutting the Grant Finder and most of the Draft Builder outright, or does your team, Clay, or the professor expect all five to still show up in some form?

> **Leo:** Reshape

**Recorded as:** All five components stay in some form, rebuilt as add-ons around the Runway rather than standalone replacements. The Grant Finder and Draft Builder shrink into thin layers on Runway output (e.g. "take the Runway's draft and run checks on it") instead of new search and drafting.

---

### Q2. What is the floor?

If reshaped add-ons are the plan, we need a priority order for when time gets tight. Rank these five reshaped pieces from **must ship** to **first to cut**:

- **A. Review Gate + Tracker:** approve/deny screen for Clay/Caroline, submission log, Airtable export, monthly count and win ratio. *(Runway has none of this; Clay's "definitely build")*
- **B. Conditions Check add-on:** takes a Runway grant and quotes each funder condition, flagging conflicts with IDEAS's restriction list and funder AI-use rules
- **C. Draft Checker add-on:** takes the Runway's rough draft and flags invented facts, character-limit overruns, AI-sounding sentences, and unanswerable questions *(replaces "Draft Builder")*
- **D. Project Profile / context pack:** stores project facts once so drafts and checks pull from them *(only valuable if the Runway can't already hold this)*
- **E. Grant Finder add-on:** re-ranks the Runway's shortlist for one specific project *(heaviest overlap)*

Give your order and say which one is the **floor**: the single thing that must work at handoff even if everything else slips.

> **Leo:** D, B, A, C, E

**Recorded as:** Profile > Conditions Check > Review Gate/Tracker > Draft Checker > Grant Finder. **The Profile is the floor.**

---

### Q3. The Tracker sits at #3, but Clay asked for it by name.

On 10/9 Clay asked for a "crash-tested, sharpened, automated grant **approval and tracking** system" and called tracking the "one thing to definitely build." The proposal made the Review Gate + Tracker Build 1 for that reason. The new order puts it third, behind the Profile and the Conditions Check.

That can be a defensible call. The Profile feeds everything, and a missed restriction is the costliest kind of mistake. But if the semester runs short, IDEAS could get a strong context tool and no tracker, which is the thing they asked for.

Which of these matches what you mean?

- **(a) Order holds as-is.** If we run short, the Tracker gets cut before the Profile or Conditions Check. We explain the trade-off to Clay.
- **(b) Build order differs from priority.** A **minimal Tracker** (approve/deny + log + Airtable export, no win-ratio dashboard) is guaranteed and built early or in parallel.
- **(c) Something else**, e.g. the Runway or Airtable already covers part of the tracking.

> **Leo:** A

**Recorded as:** Strict priority order. The Tracker is cut before the Profile or Conditions Check. The plan adds an early task to explain the trade-off to Clay.

---

### Q4. How does the "3 grants each" task fit with building?

At the 10/26 meeting each team member was asked to pick 3 grants and take them to a ready draft inside the Runway. That's **12 grants** across the team, with "aim to have 3 ready to present next week."

How should the plan treat it?

- **(a) It's our discovery phase.** Working the 12 grants in the Runway *is* how we learn what's missing. Each person logs friction, and that log drives what the Profile and Conditions Check actually do. Build starts after week 1–2.
- **(b) Separate parallel track.** A fixed slice of each person's time (~20–30%) every week; the build runs independently.
- **(c) One-time push.** 12 drafts done in weeks 1–2, then near-full-time build.
- **(d) Something else.**

Also: do the 12 drafts need to be *submitted* this semester, or just brought to "ready for Clay/Caroline review"?

> **Leo:** A

**Recorded as:** The 12 grants are the discovery phase, with a friction log per grant. The sub-question wasn't answered, so the plan **assumes** "done" means ready for Clay/Caroline review, consistent with "NOTHING applied before approval."

---

### Q5. Who owns what?

The plan needs an owner on every task. Work areas:

1. **Profile / context pack** (#1)
2. **Conditions Check** (#2)
3. **Review Gate + Tracker** (#3)
4. **Draft Checker** (#4)
5. **Partner liaison + docs**
6. **Tech lead / integration**

How would you assign these?

> **Leo:** Leo (myself) Conditions Check, Tristan (Partner Liaison) and Tech Lead, Charlotte Draft Checker and Gabe Profile Context Pack

**Recorded as:**
- **Leo:** Conditions Check
- **Gabe:** Profile / context pack
- **Charlotte:** Draft Checker
- **Tristan:** Partner Liaison + Tech Lead

The Review Gate + Tracker had no owner. The plan assigns it to **Gabe as lead (shared)**, since it reads from the Profile's data model.

---

### Q6. How do we connect to the Runway?

This decides how much of the plan is building versus copy-paste:

- **(a) Real integration:** API, DB access, or structured export from JayBird.
- **(b) Copy-paste bridge:** staff paste Runway text into our tool; zero dependency on JayBird.
- **(c) Build inside the Runway:** add features to the Runway itself.
- **(d) Unknown yet:** start with (b) and upgrade to (a) if access comes through.

> **Leo:** D

**Recorded as:** Start with the copy-paste bridge, and upgrade to real integration if the JayBird walkthrough opens access. The walkthrough is an early dependency owned by Tristan. If there's no access by a set week, copy-paste becomes the final design.

---

### Q7. What is the minimum Profile?

The Profile is the floor, so "minimum done" needs to be precise. Which of these are **in**?

1. **8-parameter project form**
2. **Project facts with last-updated dates**
3. **Voice pack:** Clay's 5 example grants + staff edits
4. **Past applications:** wins/losses, including the $4.7M debrief
5. **Restriction list**
6. **One-click "context block" output:** paste-ready brief for the Runway or Claude, replacing the 40-minute briefing

Proposed floor: **1 + 2 + 5 + 6**, with 3 and 4 as stretch. Agree, or draw the line elsewhere?

> **Leo:** Agree

**Recorded as:** Profile floor = 8-parameter form, dated project facts, restriction list, one-click context block. Voice pack and past applications are stretch.

---

### Q8. What is the minimum Conditions Check?

Input: copy-pasted funder guidelines + the Profile's restriction list. Which outputs are **in**?

1. **Extract and quote conditions** verbatim
2. **Source pointer** for each quote
3. **Restriction conflicts** flagged
4. **Funder AI-use rules** check (e.g. NIH 2025 notice)
5. **Go/no-go summary card**
6. **Seeded-condition test:** IDEAS's 5 known conditions all flagged, zero missed

Proposed floor: **1 + 2 + 3 + 4 + 6**; item 5 is stretch because the Tracker may absorb the go/no-go decision. Agree, or adjust?

> **Leo:** Agree

**Recorded as:** Conditions Check floor = extract & quote, source pointer, restriction conflicts, AI-use rule check, seeded-condition test. The go/no-go card is stretch.

---

### Q9. Calendar and cut-off dates

Proposed calendar ("8 weeks left" from the week of Oct 26):

| Plan week | Dates | Proposal week |
|---|---|---|
| W1 | Oct 26 – Nov 1 | 9 |
| W2 | Nov 2 – 8 | 10 |
| W3 | Nov 9 – 15 | 11 |
| W4 | Nov 16 – 22 | 12 |
| W5 | Nov 23 – 29 *(Thanksgiving)* | 13 (buffer) |
| W6 | Nov 30 – Dec 6 | 14 (pilot) |
| W7 | Dec 7 – 13 | 15 (handoff) |
| W8 | Dec 14 – 20 | Final presentation / report |

Proposed cut-off rule:
- **End of W3:** if the Profile floor isn't passing its tests, the **Grant Finder is cut** and its time goes to the Profile.
- **End of W4:** if the Conditions Check floor isn't passing, the **Draft Checker shrinks** to the AI-sentence flag only.
- **End of W5:** if the Gate/Tracker isn't working end to end, it ships as a **log-only tracker** or is cut.

Is the calendar right, and does the rule work?

> **Leo:** Yes it works

**Recorded as:** Calendar and all three checkpoints accepted.

---

### Answer summary

| # | Topic | Answer |
|---|---|---|
| 1 | Keep / reshape / cut | Reshape all five as Runway add-ons |
| 2 | Priority order | Profile > Conditions Check > Gate/Tracker > Draft Checker > Grant Finder; Profile is the floor |
| 3 | Tracker at #3 vs. Clay's ask | Order holds; Tracker cut first among the top three; tell Clay |
| 4 | 3 grants each | Discovery phase with friction logs |
| 5 | Owners | Leo: Conditions · Gabe: Profile (+ Tracker lead) · Charlotte: Draft Checker · Tristan: Liaison + Tech Lead |
| 6 | Runway connection | Unknown; copy-paste first, upgrade if access |
| 7 | Profile floor | Form + dated facts + restrictions + context block |
| 8 | Conditions floor | Quote + source + conflicts + AI-use + seeded test |
| 9 | Calendar and checkpoints | Accepted |

---

## 4. Final project plan

*Also saved as [`docs/plan-interview-leo.md`](plan-interview-leo.md).*

### 2.1 Assumptions

1. **Capacity:** about 8 hours per person per week, so about 60 hours per person over the 8 weeks (Thanksgiving week at half capacity). Estimates below are in **person-hours**.
2. **Integration:** a **copy-paste bridge** is the default design. Staff paste Runway grant text or draft text into our tool, and our tool produces a paste-ready block to take back to the Runway or Claude. Real Runway integration is an upgrade, not a dependency.
3. **Stack:** Python + Streamlit + Claude API (per the proposal). Data lives in a simple local store (SQLite or JSON). The Airtable connection is a **CSV export** matching IDEAS's Airtable columns unless JayBird gives API access.
4. **The 12 grants** (3 per person) are worked inside the Runway and brought to "ready for Clay/Caroline review." They are not submitted by us.
5. **Calendar:**

| Plan week | Dates | Proposal week | Theme |
|---|---|---|---|
| W1 | Oct 26 – Nov 1 | 9 | Discovery: pick grants, setup |
| W2 | Nov 2 – 8 | 10 | Discovery → requirements freeze; Profile data model |
| W3 | Nov 9 – 15 | 11 | Profile floor; Conditions Check core · **Checkpoint 1** |
| W4 | Nov 16 – 22 | 12 | Conditions Check floor; Tracker; Draft Checker · **Checkpoint 2** |
| W5 | Nov 23 – 29 | 13 | Buffer (Thanksgiving) · **Checkpoint 3** |
| W6 | Nov 30 – Dec 6 | 14 | Pilot on a live project |
| W7 | Dec 7 – 13 | 15 | Handoff: guide, cold-start test |
| W8 | Dec 14 – 20 | n/a | Final presentation and report |

### 2.2 Architecture (copy-paste bridge)

```
 Runway (JayBird)                     AI Grant Agent (Streamlit)                       Airtable
 ────────────────                     ──────────────────────────                       ────────
 grant listing ──copy/paste──► [Conditions Check] ◄── restriction list ──┐
                                        │                                │
 rough draft ───copy/paste──► [Draft Checker] ◄──── project facts ───────┤
                                        │                                │
                                        ▼                         [Project Profile]  ◄── staff intake (≤10 min)
                              [Review Gate + Tracker] ──CSV export──► Airtable
                                        │
                              context block ──copy/paste──► Runway / Claude
```

### 2.3 Build order and dependencies

```
T0 Setup & app shell (Tristan) ───────────────┬──────────────────────────────────────┐
T1 Discovery: 12 grants + friction log (All) ─┤                                      │
T2 Partner inputs (Tristan) ──────────────────┤                                      │
                                              ▼                                      │
                         T3 Project Profile — FLOOR (Gabe)                           │
                           │        │          │                                     │
                           ▼        ▼          ▼                                     │
              T4 Conditions   T5 Review Gate   T6 Draft Checker                      │
              Check (Leo)     + Tracker (Gabe) (Charlotte)                           │
                   │               │                │                                │
                   └───────────────┴────────┬───────┘     T7 Grant Finder (stretch)  │
                                            ▼             T8 Runway integration ◄────┘
                                   T9 Pilot (Tristan + All)   (conditional, Tristan)
                                            ▼
                               T10 Handoff (Tristan + All)
                                            ▼
                          T11 Final presentation & report (All)
```

**Hard dependencies:**

| Task | Cannot start / finish until |
|---|---|
| T3 Profile requirements freeze | T1 friction logs submitted (end W2) |
| T3 Profile build | T0 app shell running (W2) |
| T4 Conditions Check restriction matching | T2 restriction list received; T3 restriction-list storage done |
| T4 seeded-condition test | T2 five seeded conditions received from IDEAS |
| T5 Review Gate | T2 "who decides go/no-go" answered; T3 project records exist |
| T5 Airtable export | T2 Airtable column list from JayBird |
| T6 invented-fact check | T3 project facts available |
| T8 Runway integration | T2 JayBird walkthrough confirms access (decision by end W3) |
| T9 Pilot | T3 + T4 floors passing; T2 live project + baseline timing |
| T10 cold-start test | T10 user guide drafted; a non-pilot tester lined up |

---

### 2.4 Tasks, subtasks, acceptance criteria, estimates, owners

> **Legend:** Est = person-hours · Wk = target week · ★ = floor-critical

---

#### T0: Project setup and app shell
**Owner:** Tristan (Tech Lead) · **Total est:** 14 h · **Weeks:** W1–W2

| ID | Subtask | Owner | Est | Wk | Depends on |
|---|---|---|---|---|---|
| T0.1 | Create `src/` app structure: Streamlit multipage shell (Profile, Conditions, Draft Check, Tracker tabs) | Tristan | 4 | W1 | – |
| T0.2 | Claude API wrapper: one function, model config, per-call token/cost logging to a file | Tristan | 3 | W1 | – |
| T0.3 | Local data store (SQLite or JSON) with a shared schema doc so all four builders write to the same model | Tristan + Gabe | 3 | W2 | T0.1 |
| T0.4 | `README` run instructions; `.env.example` for the API key; never commit keys | Tristan | 2 | W2 | T0.2 |
| T0.5 | Agree on a monthly API cost cap with JayBird and name the key owner after handoff | Tristan | 2 | W2–W3 | T2.4 |

**Acceptance criteria:**
- Any teammate can clone the repo and run `streamlit run` from the README in 10 minutes or less.
- Every Claude call logs model, tokens, and estimated cost.
- No API keys or IDEAS-sensitive data in git history.
- A cost cap and post-handoff key owner are written in `docs/`.

---

#### T1: Discovery: 12 grants in the Runway + friction log
**Owner:** All (each person owns their 3 grants) · **Total est:** 40 h (10 h each) · **Weeks:** W1–W2, light follow-up through W4

| ID | Subtask | Owner | Est | Wk | Depends on |
|---|---|---|---|---|---|
| T1.1 | Each person picks 3 grants and toggles them in the Runway so others see who is working on them | All | 1 ea | W1 | Runway login |
| T1.2 | Create a shared **friction log template**: what context was re-entered, which restrictions/conditions were nearly missed, AI-sounding sentences, time spent per step | Leo | 1 | W1 | – |
| T1.3 | Work the 3 grants to a rough draft in the Runway; fill in the friction log as you go | All | 6 ea | W1–W2 | T1.1, T1.2 |
| T1.4 | Bring 3 grants (one per presenter or the team's best 3) to "ready to present" for the next IDEAS meeting | All | 1 ea | W1–W2 | T1.3 |
| T1.5 | **Synthesis session (60 min):** merge the friction logs into a requirements list per component; tag each item Floor / Stretch / Out | Leo (facilitates) + All | 1 ea | End W2 | T1.3 |
| T1.6 | Send the remaining drafts to Clay or Caroline for review; log their feedback (this becomes Tracker test data) | All | 1 ea | W2–W4 | T1.3 |

**Acceptance criteria:**
- All 12 grants are toggled in the Runway with an owner visible.
- 12 friction log entries exist in `discovery/findings/` (one per grant).
- 3 grants are presented at the next IDEAS meeting.
- The requirements list in `docs/` is tagged Floor / Stretch / Out and **frozen at end of W2**. Later changes need team agreement.
- Every Floor requirement for T3 and T4 traces to at least one friction-log entry or a proposal friction point.

---

#### T2: Partner inputs and liaison
**Owner:** Tristan (Partner Liaison) · **Total est:** 14 h · **Weeks:** W1–W6

| ID | Subtask | Owner | Est | Wk | Depends on |
|---|---|---|---|---|---|
| T2.1 | **Scope reset with Clay:** explain the Runway-aware reshape and that the Tracker is #3 and could be cut. Get his acknowledgement in writing (email/Slack) | Tristan | 2 | W1–W2 | – |
| T2.2 | Get the **restriction list** + **5 seeded funder conditions** IDEAS has run into (needed by Leo, by W3) | Tristan | 2 | W2 | – |
| T2.3 | Get the answer to **who makes the go/no-go call** and whether Clay and Caroline review every application (15 min with Caroline) | Tristan | 1 | W2 | – |
| T2.4 | **30-min JayBird walkthrough:** Runway data access (API/export/none), Airtable column list, cost cap | Tristan | 2 | W2–W3 | – |
| T2.5 | Get the **data rules**: what we may load, whether an NDA is needed | Tristan | 1 | W2 | – |
| T2.6 | **Baseline timing:** time one long application end to end (or get IDEAS's best estimate) | Tristan | 2 | W2–W3 | – |
| T2.7 | Schedule 2 × 30-min feedback sessions (W4, W5/W6) and line up **one live project** with an upcoming deadline for the W6 pilot | Tristan | 2 | W3 | – |
| T2.8 | Weekly status note to Clay/Caroline (3 bullets: done, next, blockers); flag any cut decision the same day it is made | Tristan | 2 | W2–W7 | – |

**Acceptance criteria:**
- Clay has acknowledged the priority order (including the Tracker-as-#3 trade-off) by end of W2.
- The restriction list and 5 seeded conditions are in the repo (or in a secure location if sensitive) by end of W2. **If they are late, T4 is blocked; escalate immediately.**
- The go/no-go decider is named in writing.
- The integration decision (copy-paste final vs. upgrade) is recorded by **end of W3**.
- Baseline timing is recorded before the pilot.
- The live pilot project is confirmed by end of W4.

---

#### T3: Project Profile / context pack ★ FLOOR
**Owner:** Gabe · **Total est:** 32 h · **Weeks:** W2–W4 (floor done by end W3)

| ID | Subtask | Owner | Est | Wk | Depends on |
|---|---|---|---|---|---|
| T3.1 | Data model: project record (8 parameters), fact records (value, source, **last-updated date**), restriction records (type: partner/product/funder, reason, added-by) | Gabe | 4 | W2 | T0.3, T1.5 |
| T3.2 | **8-parameter intake form:** purpose, focus area, eligibility, min award, max award/matching, deadline, funding-needed-by, reporting burden. Drop-downs and text boxes only, no prompting | Gabe | 6 | W2–W3 | T3.1 |
| T3.3 | **Project facts editor:** add/edit facts; every fact shows its last-updated date; facts older than 6 months (configurable) are highlighted as possibly stale | Gabe | 5 | W3 | T3.1 |
| T3.4 | **Restriction list manager:** org-wide list (shared across projects); import from the list IDEAS provides; read API for T4 | Gabe | 4 | W3 | T3.1, T2.2 |
| T3.5 | **One-click context block:** generates a paste-ready brief (project params + dated facts + restrictions) for the Runway or Claude; copy button | Gabe | 5 | W3 | T3.2–T3.4 |
| T3.6 | Load 2 past projects (from the 12 grants or IDEAS's past applications) as test data | Gabe | 3 | W3 | T3.2 |
| T3.7 | Timed intake test with IDEAS staff, or with a teammate if staff are unavailable; fix friction | Gabe | 3 | W4 | T3.6 |
| T3.8 | *Stretch:* voice pack (Clay's 5 grants + edits); past applications store incl. $4.7M debrief | Gabe | (8) | W5+ | Floor done |

**Acceptance criteria (floor):**
- A new project profile can be entered in **under 10 minutes** (timed, proposal success criterion 6).
- Every fact displays a last-updated date; stale facts are visibly flagged.
- The restriction list is stored once and readable by the Conditions Check.
- The context block for each of the 2 test projects is confirmed by a staff member (or, failing access, by the team member who worked that grant) to hold **what they would otherwise tell Claude** in the 40-minute briefing.
- Pasting the context block into the Runway or Claude produces a draft with no re-briefing needed.

---

#### T4: Conditions Check add-on ★
**Owner:** Leo · **Total est:** 34 h · **Weeks:** W2–W4 (floor done by end W4)

| ID | Subtask | Owner | Est | Wk | Depends on |
|---|---|---|---|---|---|
| T4.1 | Collect test inputs: funder guideline text for the 12 grants + any guidelines tied to the 5 seeded conditions | Leo | 3 | W2 | T1.3, T2.2 |
| T4.2 | **Extract & quote:** paste funder guidelines → Claude extracts each condition (eligibility, match, allowable costs, reporting, partner/product limits) **verbatim** | Leo | 7 | W3 | T0.2, T4.1 |
| T4.3 | **Quote verification:** code check that every quote is an exact substring of the pasted text; any quote that fails is dropped and flagged, never shown as a quote | Leo | 3 | W3 | T4.2 |
| T4.4 | **Source pointer:** each quote shows the nearest section heading/paragraph number from the pasted text, plus a URL if the user supplied one | Leo | 3 | W3 | T4.2 |
| T4.5 | **Restriction conflicts:** compare each condition against the Profile's restriction list; show conflicts first with condition quote + restriction text side by side | Leo | 6 | W3–W4 | T3.4, T4.2 |
| T4.6 | **Funder AI-use rule check:** dedicated scan for AI-disclosure / "no AI-generated content" / originality language; flagged separately at the top | Leo | 4 | W4 | T4.2 |
| T4.7 | **Seeded-condition test:** run all 5 seeded conditions; write as a repeatable test script in `src/tests/` | Leo | 4 | W4 | T2.2, T4.5 |
| T4.8 | Run on all 12 grants from T1; compare against what the friction logs say was nearly missed | Leo | 4 | W4 | T4.5, T1.5 |
| T4.9 | *Stretch:* go/no-go summary card (conflicts first, "decided by / date" field), feeding T5 | Leo | (5) | W5+ | Floor done |

**Acceptance criteria (floor):**
- **5 of 5 seeded conditions flagged, zero missed** (proposal success criterion 3).
- **100% of displayed quotes are verbatim** from the pasted guidelines (automated substring check passes on all 12 grants).
- Every flagged condition shows a source pointer.
- Every restriction conflict shows both the funder text and the restriction it conflicts with.
- The AI-use check correctly flags the NIH NOT-OD-25-132 notice language in a test input, and produces no AI-use flag on at least 3 guidelines known to have no AI policy.
- Each check finishes in under 60 seconds and its cost per run is logged.

---

#### T5: Review Gate + Tracker (priority #3)
**Owner:** Gabe (lead), with Tristan on Airtable export · **Total est:** 22 h · **Weeks:** W4–W5
**Cut rule:** If not working end to end at **end of W5**, ship as **log-only** (no approval enforcement) or cut entirely, per Q3. Tristan tells Clay the same day.

| ID | Subtask | Owner | Est | Wk | Depends on |
|---|---|---|---|---|---|
| T5.1 | Application record: project, funder, grant name, amount, deadline, status (drafting → in review → approved/denied → submitted → won/lost/no reply) | Gabe | 3 | W4 | T3.1 |
| T5.2 | **Approve/deny screen** for the named decider(s); records who, when, and a note; only Clay/Caroline (or the named decider) can approve | Gabe | 5 | W4 | T5.1, T2.3 |
| T5.3 | **Gate enforcement:** export and "ready to submit" are disabled until status = approved | Gabe | 2 | W4 | T5.2 |
| T5.4 | Post-submission fields: submitted date, response due date, funder contact, outcome, debrief score/notes | Gabe | 3 | W5 | T5.1 |
| T5.5 | **Airtable CSV export** matching IDEAS's Airtable columns (or API if T2.4 grants access) | Tristan | 4 | W5 | T2.4, T5.1 |
| T5.6 | Monthly count + win ratio view (simple table, no dashboard) | Gabe | 2 | W5 | T5.4 |
| T5.7 | Load test data: the 12 grants from T1 + the $4.7M finalist debrief (84/100) | Gabe | 3 | W5 | T5.4, T1.6 |

**Acceptance criteria:**
- **Zero unapproved applications can be exported** (proposal success criterion 7). Tested by attempting export at each non-approved status.
- Every approval records who approved and when.
- The CSV imports into IDEAS's Airtable base without column edits (confirmed by JayBird or Tristan on a copy of the base).
- The $4.7M debrief (84/100) is logged and visible.
- Monthly count and win ratio are correct for the loaded test data.

---

#### T6: Draft Checker add-on (priority #4)
**Owner:** Charlotte · **Total est:** 26 h · **Weeks:** W3–W5
**Cut rule:** If the Conditions Check floor is not passing at **end of W4**, T6 shrinks to **AI-sentence flagging only** (T6.4), and Charlotte's remaining hours go to T4 support or T5.

| ID | Subtask | Owner | Est | Wk | Depends on |
|---|---|---|---|---|---|
| T6.1 | Collect test drafts: the Runway rough drafts from the 12 grants + Caroline's examples of "very obvious AI" phrasing if she can share any | Charlotte | 3 | W3 | T1.3 |
| T6.2 | Input: paste the Runway draft + the funder's questions with character/word limits | Charlotte | 3 | W3 | T0.1 |
| T6.3 | **Limit check:** per-answer character/word count vs. limit (pure code, no AI) | Charlotte | 2 | W3 | T6.2 |
| T6.4 | **AI-sentence flagger:** highlight sentences matching AI patterns (rule list from T1 friction logs + Claude pass), each with a short reason; user can dismiss | Charlotte | 7 | W3–W4 | T6.1 |
| T6.5 | **Invented-fact check:** every number, date, name, and claim in the draft is matched against the Profile's facts; unmatched items flagged "not in profile, verify" | Charlotte | 6 | W4–W5 | T3.3, T6.2 |
| T6.6 | **Gap flags:** funder questions the profile cannot answer are listed as "needs human input" | Charlotte | 3 | W5 | T3.5, T6.2 |
| T6.7 | Caroline/staff rating of the AI-sentence flags on 2 drafts (feedback session) | Charlotte | 2 | W4–W5 | T6.4, T2.7 |

**Acceptance criteria:**
- Limit check is correct on 100% of answers in test drafts.
- **Zero invented facts reach the reviewer unflagged** in the test drafts (proposal success criterion 4): every number in the draft either matches a profile fact or is flagged.
- On 2 test drafts, Caroline (or the reviewer) agrees with most flagged AI sentences and says the flags are worth keeping.
- The checker never rewrites the draft itself. It flags; people edit (keeps the voice-training loop intact).

---

#### T7: Grant Finder add-on (priority #5, stretch)
**Owner:** Unassigned; whoever finishes their floor first (default: Leo or Charlotte) · **Total est:** (12 h) · **Weeks:** W5 only if on schedule
**Cut rule:** **Automatically cut at end of W3** if the Profile floor is not passing. Even if not cut, it is only built after T3–T6 are on track.

| ID | Subtask | Owner | Est | Wk | Depends on |
|---|---|---|---|---|---|
| T7.1 | Paste the Runway's daily list → re-rank against **one specific project's** profile with a one-line reason each | TBD | 6 | W5 | T3.5 |
| T7.2 | Source-mix line: report the federal vs. foundation vs. local share in the shortlist (source-bias risk) | TBD | 2 | W5 | T7.1 |
| T7.3 | Known-grants test on past projects | TBD | 4 | W5 | T7.1 |

**Acceptance criteria (if built):** 6 of the top 10 are rated "worth a look" by staff (success criterion 1). At least 2 of every 3 known grants appear (success criterion 2).

---

#### T8: Runway integration upgrade (conditional)
**Owner:** Tristan · **Total est:** (10 h) · **Weeks:** W4–W5, **only if** T2.4 confirms access by end W3

| ID | Subtask | Owner | Est | Wk | Depends on |
|---|---|---|---|---|---|
| T8.1 | Read Runway grants/drafts via the access JayBird provides (API, export, or DB) into the paste fields | Tristan | 6 | W4 | T2.4 |
| T8.2 | Keep the copy-paste path working as a fallback | Tristan | 2 | W4 | T8.1 |
| T8.3 | Document the integration for JayBird's maintenance | Tristan | 2 | W5 | T8.1 |

**Acceptance criteria:** A grant can be pulled from the Runway without copy-paste; the copy-paste path still works if the integration fails. **If there is no access by end of W3, T8 is closed and copy-paste is the final design.**

---

#### T9: Pilot on a live project
**Owner:** Tristan (coordination) + All · **Total est:** 20 h · **Week:** W6

| ID | Subtask | Owner | Est | Wk | Depends on |
|---|---|---|---|---|---|
| T9.1 | Rerun all earlier acceptance tests on the final build (regression) | Each component owner | 2 ea (8) | W6 | T3–T6 |
| T9.2 | Staff run the full flow on the live project: Profile → context block → Runway draft → Conditions Check → Draft Checker → Review Gate | Tristan (facilitates) | 4 | W6 | T2.7, T9.1 |
| T9.3 | Time each step vs. the W2 baseline | Tristan | 2 | W6 | T2.6 |
| T9.4 | Staff rate the draft's voice 1–5 and say whether they would keep using the tool | Charlotte | 2 | W6 | T9.2 |
| T9.5 | Fix pilot-blocking bugs only (no new features) | Owners | 4 | W6 | T9.2 |

**Acceptance criteria:**
- Briefing time is **under 10 minutes** (vs. up to 40), and search + drafting of a long application is **at least 30% faster** than baseline (success criterion 6).
- Voice rating averages **4 or higher**, and staff say "yes" to continued use (success criterion 5).
- Nothing in the pilot is submitted without approval in the Review Gate (or, if T5 was cut, without Clay/Caroline sign-off by email).

---

#### T10: Handoff
**Owner:** Tristan (lead) + All · **Total est:** 20 h · **Week:** W7

| ID | Subtask | Owner | Est | Wk | Depends on |
|---|---|---|---|---|---|
| T10.1 | **User guide:** one page per component, written for a new intern; screenshots | Each owner writes their section (2 h ea) | 8 | W7 | T9 |
| T10.2 | Maintenance doc: how to run, API key owner, cost cap, where data lives, known limits | Tristan | 3 | W7 | T0.5 |
| T10.3 | **Cold-start test:** someone who was not in the pilot runs the tool using only the guide; fix the guide where they get stuck | Tristan | 3 | W7 | T10.1 |
| T10.4 | Demo recording (5–8 min) | Leo | 3 | W7 | T9 |
| T10.5 | Final code tagged in GitHub; repo README updated | Tristan | 3 | W7 | T9.5 |

**Acceptance criteria:**
- The cold-start tester completes Profile → Conditions Check (and the Review Gate if built) **without help**.
- A named IDEAS owner for the API key and fixes is written in the maintenance doc.
- The code is tagged, and the README run steps work on a fresh clone.

---

#### T11: Final presentation and report
**Owner:** All (proposed: Charlotte assembles the report, Leo assembles the deck) · **Total est:** 24 h · **Week:** W7–W8

| ID | Subtask | Owner | Est | Wk | Depends on |
|---|---|---|---|---|---|
| T11.1 | Results vs. the 7 success criteria, with what was cut and why (the scope decisions above) | Leo | 4 | W7–W8 | T9 |
| T11.2 | Final report draft (sections per component, written by owners) | Charlotte (assembles), All | 4 + 2 ea | W8 | T11.1 |
| T11.3 | Presentation deck + rehearsal | Leo (assembles), All | 4 + 1 ea | W8 | T11.1 |
| T11.4 | Save everything in `deliverables/` (report, presentation, handoff) | Tristan | 2 | W8 | T11.2–T11.3 |

**Acceptance criteria:** The report and deck are in `deliverables/`. Every success criterion is reported with a number or an honest "not measured" and the reason. Cut components are explained, not hidden.

---

### 2.5 Week-by-week schedule

| Week | Leo | Gabe | Charlotte | Tristan | Gate / milestone |
|---|---|---|---|---|---|
| **W1** Oct 26–Nov 1 | Friction log template (T1.2); 3 grants (T1.3) | 3 grants (T1.3) | 3 grants (T1.3) | App shell + API wrapper (T0.1–2); Clay scope reset (T2.1); 3 grants | 3 grants ready to present |
| **W2** Nov 2–8 | Finish grants; run synthesis (T1.5); collect guideline texts (T4.1) | Finish grants; Profile data model (T3.1); start intake form | Finish grants; send to Clay/Caroline (T1.6) | Data store (T0.3); restriction list, seeded conditions, decider, data rules (T2.2–2.5) | **Requirements frozen**; restriction list in hand |
| **W3** Nov 9–15 | Extract & quote + verification + source pointer (T4.2–4.4); start conflicts (T4.5) | Intake form, facts editor, restriction manager, context block (T3.2–3.6) | Test drafts, limit check, start AI-sentence flagger (T6.1–6.4) | JayBird walkthrough (T2.4); baseline timing (T2.6); line up pilot (T2.7) | **Checkpoint 1:** Profile floor passing? If not → T7 cut, help Gabe. **Integration decision.** |
| **W4** Nov 16–22 | Conflicts, AI-use check, seeded test, 12-grant run (T4.5–4.8) | Intake timing test (T3.7); Tracker record + approve/deny + gate (T5.1–5.3) | AI-sentence flagger; invented-fact check (T6.4–6.5); feedback session 1 | Integration (T8) if access; weekly status | **Checkpoint 2:** Conditions Check floor passing? If not → T6 shrinks to AI-flags only. |
| **W5** Nov 23–29 *(Thanksgiving, half capacity)* | Buffer; stretch go/no-go card (T4.9) or T7 | Post-submission fields, win ratio, test data (T5.4, 5.6, 5.7) | Gap flags (T6.6); Caroline rating (T6.7) | Airtable CSV (T5.5) | **Checkpoint 3:** Tracker end-to-end? If not → log-only or cut. Tell Clay. |
| **W6** Nov 30–Dec 6 | Regression + pilot support | Regression + pilot support | Voice rating (T9.4); regression | Run pilot, timing (T9.2–9.3) | **Pilot on live project** |
| **W7** Dec 7–13 | Guide section; demo video (T10.4); results vs. criteria (T11.1) | Guide section | Guide section | Maintenance doc; cold-start test; tag code (T10.2–10.5) | **Handoff to IDEAS** |
| **W8** Dec 14–20 | Deck (T11.3) | Report sections | Report assembly (T11.2) | `deliverables/` (T11.4) | **Final presentation and report** |

### 2.6 Owner load (floor + committed scope; stretch in parentheses)

| Owner | Tasks | Est hours |
|---|---|---|
| **Leo** | T1 (10, incl. log template + synthesis), T4 (34), T10.1/10.4 (5), T11.1/11.3 (9), T9 (2) | **~60** (+5 T4.9, +12 T7) |
| **Gabe** | T1 (10), T3 (32), T5 lead (18), T10.1 (2), T11 (3), T9 (2) | **~67** (+8 T3.8) ⚠ heaviest. If tight, T5 slips first, per the priority order |
| **Charlotte** | T1 (10), T6 (26), T9.4 (2), T10.1 (2), T11.2 (6), T9 (2) | **~48** (has room to support T4 or T5 if needed) |
| **Tristan** | T0 (14), T1 (10), T2 (14), T5.5 (4), T9 (8), T10 (11), T11 (3) | **~64** (+10 T8 if access) |

> **Load-balancing note:** Gabe carries both the floor and the Tracker. If Checkpoint 1 passes cleanly, **Charlotte takes T5.4–T5.7** (post-submission fields, win ratio, test data) to free Gabe. Decide this at Checkpoint 1.

### 2.7 Cut-off checkpoints (agreed rule)

| Checkpoint | Date | Test | If it fails |
|---|---|---|---|
| **1** | End W3 (Nov 15) | Profile floor passes T3 acceptance criteria | **Grant Finder (T7) cut.** Its time goes to the Profile. |
| **1b** | End W3 (Nov 15) | JayBird has given Runway data access | **T8 closed**; copy-paste is the final design. |
| **2** | End W4 (Nov 22) | Conditions Check floor passes T4 acceptance criteria (5/5 seeded) | **Draft Checker shrinks** to AI-sentence flagging only; Charlotte supports T4. |
| **3** | End W5 (Nov 29) | Review Gate + Tracker works end to end, with a zero-unapproved-export test passing | **Ships log-only** (no enforcement) **or is cut**. Tristan tells Clay that day, per the T2.1 agreement. |

Each checkpoint is a 15-minute team call. The decision and reason are recorded in `docs/meeting-notes/`.

### 2.8 Scope risks

| Risk | Likelihood | Impact | Response |
|---|---|---|---|
| Clay expects the Tracker and it gets cut | Medium | High (trust) | T2.1 gets Clay's written acknowledgement of the trade-off in W1–W2; weekly status flags it early; the Checkpoint 3 decision is communicated the same day |
| Restriction list / seeded conditions arrive late | Medium | **Blocks T4 floor** | Tristan escalates by mid-W2; Leo builds against the friction-log conditions from the 12 grants in the meantime |
| The Runway already stores project context (Profile duplicates it) | Low–Med | High (floor redundancy) | Confirm in the JayBird walkthrough (T2.4). If so, the Profile is reshaped as the restriction list + dated facts + context block that *feeds* the Runway, still the floor |
| Copy-paste is too slow for Clay ("slower than opening Claude") | Medium | Medium | Profile under 10 minutes; context block is one click; time it in the pilot vs. baseline |
| Scope creep from the 12-grant discovery | Medium | Medium | Requirements freeze at end of W2; new ideas go to a "post-handoff" list in `docs/` |
| Gabe overloaded | Medium | Medium | Load-balancing rule at Checkpoint 1 (Charlotte takes T5.4–5.7) |
| Funder AI-use rules are missed | Low | High | Dedicated T4.6 check, flagged at the top; the reviewer decides disclosure |

### 2.9 Open items to confirm

1. Do the 12 grants need to be **submitted** this semester, or only brought to "ready for review"? (Plan assumes the latter.)
2. Whether Charlotte or Gabe takes the second half of the Tracker (decide at Checkpoint 1).
3. Whether the presentation slides differ from the proposal on scope, dates, or owners. They were not attached to this interview, so reconcile once available.
4. The exact final presentation date in W8.
