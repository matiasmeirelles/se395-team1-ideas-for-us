# Audit Log: Leonardo (Scope Creep Review)

**Project:** AI Grant Agent for IDEAS For Us (Catalyst Collective, SE 395-2)
**Participant:** Leonardo Takeshi Campi Kiyose (Leo)
**Reviewer:** Claude (Claude Code), acting as senior project reviewer
**Date:** November 4, 2026
**Related files:** [`audit-scope-creep-leonardo.md`](audit-scope-creep-leonardo.md) (the audit on its own), [`interview-log-leo.md`](interview-log-leo.md), [`plan-interview-leo.md`](plan-interview-leo.md)

---

## Contents

1. [The request](#1-the-request)
2. [The plan submitted for review](#2-the-plan-submitted-for-review)
3. [Audit findings](#3-audit-findings)
4. [Follow-up discussion](#4-follow-up-discussion)

---

## 1. The request

> Act as a senior project reviewer. Here is our project plan for an AI tool we are building for IDEAS for Us.
>
> *[project plan, reproduced in Section 2]*
>
> Audit this plan for scope creep. Be specific. For each issue you find, name the task, explain the problem, and suggest a fix.
> Do not rewrite the plan. Just list the problems and fixes. Save it as an artifact called audit-Scope Creep]-[leonardo.md.

*Note: the requested filename was saved as `audit-scope-creep-leonardo.md`, with the stray brackets and space removed.*

---

## 2. The plan submitted for review

*Reproduced from the pasted plan. The content is unchanged. The layout is cleaned up for Markdown: each task's owner, estimate, timing and dependencies are on one line, and the empty week columns in the build-order table are replaced by a "When" column.*

### AI Grant Agent Project Plan

*Catalyst Collective · SE 395-2 · Weeks 8–15*

One plan for IDEAS For Us, built from the council evaluation with the team's decisions applied. Tasks follow build order.

#### Team decisions applied

The team kept three items the council had flagged. Every other council suggestion is treated as not an immediate priority: items the council cut stay cut, and its 12 added tasks are deferred.

| Kept by the team | Task | Council verdict and how it is built here |
|---|---|---|
| **Reviewer edits saved to the context pack** | T10 | Council: modify. Kept, with edits held as pending until a reviewer approves them, and built after the Review Gate. |
| **Outcome insights** | T11 | Council: cut. Kept as advisory only, with source records, a minimum-data rule and accept / dismiss. |
| **Regression and security check** | T12 | Council: modify. Kept as tests written as each task lands plus one checklist. |

- Budget: 4 people × 4 hours × 8 weeks = 128 hours. This plan commits 123, leaving 5 in reserve. The Technical Reviewer's realistic ranges for several components were higher than these estimates, so the plan is tight.
- Owners are proposed. Charlotte owns the Conditions Check because the load is balanced at about 31 hours each; Gabe should review its prompts.
- Draft Checker is chosen over Draft Builder, as the council recommended. IDEAS has not been asked which they prefer.
- Reserve hours cover pilot fixes and anything the Technical Reviewer's ranges push over.

#### Hours by owner

| Owner | Hours | Tasks |
|---|---|---|
| Gabe | 31 h | T1, T8, T10, T11 |
| Leo | 30 h | T0, T3, T15, T16 |
| Tristan | 31 h | T5, T6, T7, T12 |
| Charlotte | 31 h | T2, T4, T9, T14, T13, T17 |
| **Total** | **123 of 128 h** | 5 in reserve |

#### Build order at a glance

| Task | Owner | Hours | When |
|---|---|---|---|
| T0 Kickoff and partner inputs | Leo | 6 | Weeks 8–9 |
| T1 App foundation and storage | Gabe | 10 | Weeks 8–9 |
| T2 Light discovery and friction log | Charlotte | 3 | Weeks 8–9 |
| T3 Project Profile | Leo | 9 | Weeks 9–10 |
| T4 Context pack and voice pack | Charlotte | 4 | Weeks 9–10 |
| T5 Tracker | Tristan | 12 | Weeks 10–11 |
| T6 Review Gate and hard export block | Tristan | 8 | Weeks 11–12 |
| T7 Airtable export | Tristan | 4 | Week 12 |
| T8 Draft Checker (flags, never rewrites) | Gabe | 12 | Weeks 10–12 |
| T9 Conditions Check | Charlotte | 12 | Weeks 10–12 |
| T10 Reviewer edits saved to the context pack | Gabe | 3 | Week 13 |
| T11 Outcome insights | Gabe | 6 | Weeks 12–13 |
| T12 Regression and security check | Tristan | 7 | Weeks 11–14 |
| T14 Cold-user test | Charlotte | 2 | Week 13 |
| T13 Pilot on a live project | Charlotte | 7 | Week 14 |
| T15 Handoff | Leo | 8 | Weeks 14–15 |
| T16 Final presentation and report | Leo | 7 | Week 15 |
| T17 Weekly cadence, checkpoints and risk register | Charlotte | 3 | Weeks 8–15 |

#### Checkpoints

| When | Pass test |
|---|---|
| Week 10 | Profile form works end to end; Tracker schema stored; restriction list and five conditions received |
| Week 12 | Review Gate blocks a direct unapproved export; Draft Checker and Conditions Check pass their seeded tests |
| Week 13 | Feature freeze; only pilot-blocking fixes after this point; cold-user test done |
| Week 14 | Pilot complete and pass / fail recorded |

#### Phase 1. Set-up and foundation (Weeks 8–9)

##### T0 · Kickoff and partner inputs

**Owner:** Leo · **Estimate:** 6 h · **When:** Weeks 8–9 · **Depends on:** None

Subtasks:
- [ ] Hold a 15-minute call to confirm the go/no-go decider and the pass/fail thresholds for voice, usefulness and time (IDEAS staff set them)
- [ ] Confirm the data rules, including what may be sent to the Claude API and whether an NDA is needed, before any record is loaded
- [ ] Confirm a hosting target that keeps data across restarts, the API key owner and a monthly cost cap
- [ ] Collect the restriction list, the five seeded conditions (or a fallback set from the friction log), the Airtable column list and sample grants
- [ ] Write down the scope split with JayBird and the Runway; copy-paste stays the default
- [ ] Check with Claude Corps so the team does not duplicate an existing tool
- [ ] Record a baseline timing of today's process (one timed session, or a staff estimate labeled as estimated)
- [ ] Get Clay's written acknowledgement that the Tracker is the first priority
- [ ] Hold a light requirements freeze at the end of Week 8; floor items can still be refined

Acceptance criteria:
- Decider, thresholds and data rules are written down and acknowledged by Clay or Caroline
- Hosting target, key owner and cost cap are named
- Restriction list, seeded conditions and Airtable columns are received, or each has a named chase date
- Baseline is recorded and labeled measured or estimated

##### T1 · App foundation and storage

**Owner:** Gabe · **Estimate:** 10 h · **When:** Weeks 8–9 · **Depends on:** T0 (hosting and data rules)

Subtasks:
- [ ] Create the repo, Streamlit shell, README, .env.example and requirements.txt, with a pre-commit secrets check
- [ ] Build the Claude API wrapper with per-call token and cost logging against the cap
- [ ] Build one thin storage module (SQLite behind a single interface) on the persistent host
- [ ] Write the shared schema doc so everyone uses the same record shapes
- [ ] Add an approver / non-approver flag set in config (no role admin page)

Acceptance criteria:
- A fresh clone runs from the README alone
- No key or secret appears in the repo
- The cost log shows tokens and cost for every call
- A saved record survives an app restart on the chosen host
- All four members have reviewed the schema doc

##### T2 · Light discovery and friction log

**Owner:** Charlotte · **Estimate:** 3 h · **When:** Weeks 8–9 · **Depends on:** None

Subtasks:
- [ ] Set up a friction-log template, one entry per grant
- [ ] Work 4–6 grants in the Runway to "ready for review" and log staff pain points
- [ ] Present three grants at the next IDEAS meeting and log the feedback

Acceptance criteria:
- The log has entries from at least 4 grants
- Findings are written into the Profile and Conditions Check requirements
- Three grants were shown at one IDEAS meeting

##### T3 · Project Profile

**Owner:** Leo · **Estimate:** 9 h · **When:** Weeks 9–10 · **Depends on:** T1, T0

Subtasks:
- [ ] Build the intake form for the 8 parameters
- [ ] Show a last-updated date on every fact, with one fixed stale constant in code (no settings screen)
- [ ] Add the restriction list as an import plus an editable table (blocked until IDEAS supplies the list)
- [ ] Add the one-click context block with a copy button for the Runway
- [ ] Lay out a one-screen view of key grant information, used as the layout guide for review and tracker screens
- [ ] Time the intake with real IDEAS staff

Acceptance criteria:
- A staff member completes a profile in under 10 minutes
- The context block pastes into the Runway with no re-briefing
- Every stored fact shows its date
- The restriction list loads and can be edited

##### T4 · Context pack and voice pack

**Owner:** Charlotte · **Estimate:** 4 h · **When:** Weeks 9–10 · **Depends on:** T1

Subtasks:
- [ ] Store Clay's five grants as plain text
- [ ] Accept pasted text or .txt only (no PDF or DOCX parsing yet)
- [ ] Make the stored examples available to the Draft Checker as voice input

Acceptance criteria:
- All five grants are stored and retrievable
- No upload step changes the text silently

#### Phase 2. The floor: Tracker, Review Gate, export (Weeks 10–12)

##### T5 · Tracker

**Owner:** Tristan · **Estimate:** 12 h · **When:** Weeks 10–11 · **Depends on:** T1 (schema)

Subtasks:
- [ ] Build records for grant, funder, deadline, status, amount, submitted and decision dates
- [ ] Add funder contact, response date, debrief score and debrief notes
- [ ] Show the monthly grant count and the win ratio with its sample size
- [ ] Show the deadline as a visible column (no reminders)
- [ ] After the data rules are confirmed, load the $4.7M / 84-of-100 debrief and past records as test data; label the 12 unsubmitted drafts as test data and keep them apart from real records

Acceptance criteria:
- Every field saves and reloads
- The monthly count and win ratio are correct on the seeded data, and the ratio shows its sample size
- The real debrief appears with its score and notes
- Test data is labeled and separate from real records

##### T6 · Review Gate and hard export block

**Owner:** Tristan · **Estimate:** 8 h · **When:** Weeks 11–12 · **Depends on:** T5

Subtasks:
- [ ] Add approve / deny with a named reviewer; the buttons show only to approvers
- [ ] Highlight numbers and gaps on the reviewer screen (reused passages: exact match against stored answers only)
- [ ] Enforce approval inside the export function at the storage layer
- [ ] Test the export function by calling it directly with unapproved records
- [ ] If the gate misses its checkpoint, fail visibly; do not ship a log-only Tracker

Acceptance criteria:
- A direct call to export an unapproved record fails every time
- Every approval stores the reviewer's name and time
- Denied and unreviewed records cannot be exported

##### T7 · Airtable export

**Owner:** Tristan · **Estimate:** 4 h · **When:** Week 12 · **Depends on:** T6, T0 (Airtable columns)

Subtasks:
- [ ] Build a CSV that matches IDEAS's Airtable columns
- [ ] Add the API only if JayBird provides credentials by a fixed early date; otherwise close it
- [ ] Document the Runway and Airtable integration for JayBird

Acceptance criteria:
- The CSV imports into an Airtable test base with no column errors
- Only approved records export
- The integration is documented for JayBird

#### Phase 3. Drafting safeguards and insights (Weeks 10–13)

##### T8 · Draft Checker (flags, never rewrites)

**Owner:** Gabe · **Estimate:** 12 h · **When:** Weeks 10–12 · **Depends on:** T1, T3, T4

Subtasks:
- [ ] Check the character limit; retry at most twice, then flag the answer for a human
- [ ] Check for invented facts against the profile: match numbers, dates and names in code first, then use the model
- [ ] Flag unanswerable questions and gaps instead of filling them
- [ ] Flag AI-sounding sentences using a pattern list from Caroline's examples plus one Claude pass; flags can be dismissed
- [ ] Have staff rate a sample of the AI-sentence flags
- [ ] Record the voice rating (4/5 target) with a scheduled rater

Acceptance criteria:
- Zero invented facts pass through on the test drafts
- Every over-limit answer is caught
- Gaps are flagged instead of filled
- The staff rating of the flags is recorded

##### T9 · Conditions Check

**Owner:** Charlotte · **Estimate:** 12 h · **When:** Weeks 10–12 · **Depends on:** T0 (restriction list, five conditions), T3

Subtasks:
- [ ] Extract each funder condition and quote it with a source pointer
- [ ] Verify each quote by code as an exact substring of the guidelines
- [ ] Compare conditions to the restriction list and show conflicts first, with the funder text beside the restriction
- [ ] Detect funder AI-use rules with a keyword scan or one extra prompt instruction, and surface candidates for a human to confirm
- [ ] Run the seeded-condition test (5 of 5)
- [ ] Run on about four grants plus the seeded conditions and measure run time (a target, not a gate)
- [ ] Test that the NIH NOT-OD-25-132 language is flagged and three no-policy guidelines are not

Acceptance criteria:
- 5 of 5 seeded conditions are flagged
- Every quoted condition is an exact substring of its source
- The NIH language is flagged and the three no-policy guidelines are not
- Each condition has a source pointer a reviewer can follow

##### T10 · Reviewer edits saved to the context pack

**Owner:** Gabe · **Estimate:** 3 h · **When:** Week 13 · **Depends on:** T6, T4, T8

Subtasks:
- [ ] Hold reviewer edits as pending
- [ ] Save an edit to the context pack only after a reviewer approves it

Acceptance criteria:
- An edit on a checked draft leaves the pack unchanged until approval
- After approval, the edit appears in the pack with the reviewer's name
- Rejected edits are discarded

##### T11 · Outcome insights

**Owner:** Gabe · **Estimate:** 6 h · **When:** Weeks 12–13 · **Depends on:** T5 (with the debrief loaded)

Subtasks:
- [ ] Show suggestions drawn from the funder's own feedback text, each linked to its source records
- [ ] Add the minimum-data rule: show "not enough history" below a threshold the team sets
- [ ] Add an accept / dismiss control on each suggestion
- [ ] Keep suggestions advisory; a human on the team reviews and decides

Acceptance criteria:
- Every suggestion cites the records it came from
- Below the minimum threshold the page shows "not enough history" and no advice
- A reviewer can dismiss any suggestion
- Nothing is applied or exported without a human decision

#### Phase 4. Verify, pilot, hand off (Weeks 11–15)

##### T12 · Regression and security check

**Owner:** Tristan · **Estimate:** 7 h · **When:** Weeks 11–14 · **Depends on:** Each task as it lands

Subtasks:
- [ ] Write scripted tests from the acceptance criteria as each task lands
- [ ] Run one checklist: secrets scan, role bypass, no community personal data, export-gate attempts
- [ ] Have someone other than the component's author run the security check

Acceptance criteria:
- All scripted tests pass
- The checklist is complete with no open high-severity item
- No secret is in the repo
- Each component was checked by a non-author

##### T14 · Cold-user test

**Owner:** Charlotte · **Estimate:** 2 h · **When:** Week 13 · **Depends on:** T3, T6

Subtasks:
- [ ] Arrange an intern or unfamiliar user in advance
- [ ] Have them complete a profile and a review using drop-downs only, with no prompting
- [ ] Log every point of confusion and fix the blocking ones

Acceptance criteria:
- The tester finishes both tasks with no prompting
- Confusions are logged and blocking ones fixed before the pilot

##### T13 · Pilot on a live project

**Owner:** Charlotte · **Estimate:** 7 h · **When:** Week 14 · **Depends on:** T5–T12; live project confirmed by Week 11

Subtasks:
- [ ] Run a live grant with a real deadline through the tool
- [ ] Time each step against the baseline
- [ ] Keep an issue log with severity, owner and status; fix pilot-blocking bugs only
- [ ] Have the named decider record pass or fail

Acceptance criteria:
- Step timings are recorded against the baseline
- The decider's pass / fail is written down
- No blocking issue is open at handoff

##### T15 · Handoff

**Owner:** Leo · **Estimate:** 8 h · **When:** Weeks 14–15 · **Depends on:** T12, T13

Subtasks:
- [ ] Write one guide that covers use and maintenance (no separate AI doc)
- [ ] Name an IDEAS owner for the key and fixes, with a written failure-contact path
- [ ] Put the code in GitHub

Acceptance criteria:
- An IDEAS owner and failure contact are named in the guide
- A staff member follows the guide without help
- The code is in GitHub

##### T16 · Final presentation and report

**Owner:** Leo · **Estimate:** 7 h · **When:** Week 15 · **Depends on:** T13

Subtasks:
- [ ] Build the results-versus-criteria table inside the report
- [ ] Present a live demo (no separate recording)
- [ ] Lead with what IDEAS can use

Acceptance criteria:
- Every success criterion is reported as met or not met, with evidence
- The demo runs live

#### Running through all weeks (Weeks 8–15)

##### T17 · Weekly cadence, checkpoints and risk register

**Owner:** Charlotte · **Estimate:** 3 h · **When:** Weeks 8–15 · **Depends on:** None

Subtasks:
- [ ] Send a three-bullet weekly status note to IDEAS
- [ ] Tie each checkpoint to a runnable pass/fail test and tell Clay the same day about any cut
- [ ] Keep one living risk-register page inside the weekly note
- [ ] Hold two feedback sessions with staff in Weeks 11–12
- [ ] Plan Thanksgiving week at half capacity

Acceptance criteria:
- A note goes out every week
- Every checkpoint has a test that passes or fails
- Two feedback sessions are held and rated

#### If hours run short

- Cut first if hours run short: Outcome insights (T11), then the Airtable API option (T7), then the AI-sentence flag (T8).
- Never cut: Tracker (T5), Review Gate and export block (T6), invented-fact check (T8), Conditions Check seeded test (T9), pilot (T13).

#### Cut from the plan

- Grant Finder, its API client, source logging and source-mix report (the Runway already finds 10–15 grants a day)
- Go/no-go summary card
- Email notifications, deadline reminders and dashboard polish (a visible deadline column covers it)
- Gmail first-draft delivery
- Draft Builder (this plan builds the Draft Checker only)
- Admin page for changing roles; win/loss tagging; searchable context documents; PDF/DOCX parsing
- The 12-grant discovery round, the 5–8 minute demo recording and a separate deliverables folder
- Log-only Tracker fallback

#### Council suggestions deferred by the team

- Data-flow and NDA decision as its own task (the confirmation is a subtask of T0)
- Automated test harness as a separate task (T12 covers tests in the lightest form)
- Prompt and model strategy document
- Budget for IDEAS staff time
- Named backup for Gabe's AI work
- One agreed hours-per-week budget and calendar as a recorded decision (this plan uses 4 hours a week each, Weeks 8–15)
- Decision log of cuts
- Asking IDEAS whether they want generated drafts or only a checker
- Source-bias check on finder output (moot with the Finder cut)
- Error handling for Claude API failures and rate limits

---

## 3. Audit findings

*The full audit, as saved in [`audit-scope-creep-leonardo.md`](audit-scope-creep-leonardo.md).*

### Summary

The plan's core is well scoped: Profile, Tracker, Review Gate, Conditions Check, Draft Checker and the pilot. Scope creep comes in three ways:

1. **Features the council cut or deferred were brought back** (T10, T11). That is 9 hours of new capability for things IDEAS did not ask for.
2. **Subtasks quietly grow a task past its definition.** The "never rewrites" Draft Checker has a retry loop and a voice rating. The Review Gate has reused-passage detection backed by a store that no task builds. The Profile carries a layout task for other screens.
3. **Partner time is spread across many separate asks.** The council's M5 (budget IDEAS staff time) was deferred, yet the plan asks IDEAS staff for something in at least 9 places.

The plan also has **no real reserve.** The 128-hour budget assumes full weeks, but T17 plans Thanksgiving week at half capacity. That leaves about 120 hours available against 123 committed, so the plan starts about 3 hours over. Every item below that frees hours also fixes this.

**Severity:** 🔴 High: adds unbudgeted work or threatens a never-cut item · 🟠 Medium: grows a task past its definition · 🟡 Low: small drift or duplication

---

### Issues and fixes

#### 1. 🔴 T11 Outcome insights: a feature nobody asked for, built on one data point

**Problem:**
- The council voted 3–1 to cut this. IDEAS asked to *track* win ratios and debriefs (Clay, Oct 9); they did not ask for a suggestion engine.
- IDEAS has about **one** debrief on record (the $4.7M / 84-of-100). The minimum-data rule in T11 will therefore almost certainly display "not enough history."
- The task can pass every acceptance criterion while giving IDEAS nothing. It still costs 6 hours plus four subtasks of UI: suggestions, source links, the threshold, and accept/dismiss.

**Fix:** Cut T11.
- T5 already stores and displays debrief score and notes, which is the part Clay asked for.
- Record "outcome insights after 5+ debriefs" on the post-handoff list.
- **Saves 6 h** and restores a real reserve.

---

#### 2. 🔴 T10 Reviewer edits saved to the context pack: depends on an editor that no task builds

**Problem:**
- T8 is a checker that "flags, never rewrites," and no task gives reviewers an in-app place to edit a draft. So the "reviewer edits" T10 captures have no source.
- Making T10 work means building a draft editor, a pending-edit queue, and an approve/reject flow for edits. That is a second review gate on top of T6, and none of it is in the 3-hour estimate.
- The proposal says the voice-training loop already works outside the tool and should not change. The council's Scope Guardian voted to defer it for that reason.

**Fix:** Cut T10 as a separate task.
- If the team wants the voice pack to grow, add one subtask to T4: "Paste an approved final answer into the voice pack, with the approver's name and date." That is under 1 hour and needs no edit workflow.
- **Saves 2–3 h** and removes hidden editor scope.

---

#### 3. 🟠 T8 Draft Checker: "retry at most twice" is a Draft Builder in disguise

**Problem:**
- The first T8 subtask says to "check the character limit; retry at most twice, then flag." A retry means the model regenerates the answer, which is drafting.
- That contradicts the task's own title ("flags, never rewrites") and the team's decision to build the Checker instead of the Draft Builder.
- It also adds model calls, cost, and a new failure mode: a regenerated answer could introduce invented facts *after* the fact check has run.

**Fix:** Make the limit check pure code.
- Count characters and words and flag any over-limit answer for a human to shorten. Remove the retry.
- This matches the council's view that the limit check is "plain code with no model risk."

---

#### 4. 🟠 T8 Draft Checker: the voice rating measures the Runway, not our tool

**Problem:**
- The subtask "Record the voice rating (4/5 target) with a scheduled rater" scores the *draft*, and the Runway wrote that draft. Our Checker never writes text.
- A low or high score says nothing about whether our tool works, but it still needs a scheduled IDEAS rater. It is carried over from the Draft Builder plans, which were cut.

**Fix:** Remove the voice rating from T8.
- Keep the subtask that rates the *flags* ("staff rate a sample of the AI-sentence flags"), which does measure our tool.
- If the team wants a voice number for the final report, collect it once during the T13 pilot, not as a T8 deliverable.

---

#### 5. 🟠 T4 Context pack and voice pack: "voice input to the Draft Checker" has no matching feature

**Problem:**
- T4's last subtask makes Clay's five grants "available to the Draft Checker as voice input," and T8 lists T4 as a dependency. Yet no T8 subtask uses voice examples.
- The AI-sentence flagger uses Caroline's pattern list plus a Claude pass. A "compare to Clay's voice" feature is implied but never defined, estimated, or tested. That is a classic opening for scope creep: someone will build it during Weeks 10–12 because the dependency says to.

**Fix:** Pick one of these.
- **(a)** Remove the T4 → T8 dependency and keep T4 as storage only, so the examples are on hand for the post-handoff list or for Runway briefing via the context block.
- **(b)** Define one bounded use in T8: "Include up to 2 of Clay's examples in the AI-sentence prompt as reference." Add that to T8's estimate.

Option (a) is the smaller scope.

---

#### 6. 🟠 T6 Review Gate: reused-passage detection needs a store that no task builds

**Problem:**
- T6 says to highlight "reused passages: exact match against stored answers only."
- No task stores past answers. Win/loss tagging, past-application storage, and searchable documents are all cut, and T4 stores only Clay's five grants.
- Shipping this subtask therefore means building an answers store. It also partly duplicates T8: "highlight numbers and gaps" repeats the invented-fact and gap flags.

**Fix:**
- Remove reused-passage detection from T6 and put it on the post-handoff list.
- Change "highlight numbers and gaps" to "display T8's flags on the reviewer screen," so the logic lives in one place and T6 only renders it.

---

#### 7. 🟠 T3 Project Profile: the "one-screen view of key grant information" is design work for other tasks

**Problem:**
- The Profile is project-level, but this subtask asks for a *grant*-level view to serve "as the layout guide for review and tracker screens." That is a UI design deliverable for T5 and T6, scheduled inside T3.
- It sits on the critical path for the floor: T3 has to pass Checkpoint 1 in Week 10.
- The council kept it only "as a layout guideline … not a separate dashboard" (row 10b).

**Fix:** Remove it from T3.
- Add a short layout note (which fields appear first) to the T1 schema doc, and let T5 and T6 own their own screens.

---

#### 8. 🟠 T7 Airtable export: integration work beyond the CSV

**Problem:**
- T7 has two extras beyond the CSV:
  - an optional API path ("if JayBird provides credentials by a fixed early date"), with no date set
  - "Document the Runway and Airtable integration," but the plan has no Runway integration. Copy-paste is the default in T0.
- Without a date, the API option stays open into Week 12. The documentation subtask invites someone to build a Runway integration so there is something to document.

**Fix:**
- Set the API cut-off date explicitly: end of Week 10, or else the API option is closed.
- Change the documentation subtask to "Document the CSV export and the copy-paste workflow."
- Strike "Runway integration" from the task.

---

#### 9. 🟠 T0 Kickoff and partner inputs: nine subtasks in 6 hours, and two are not blockers

**Problem:**
- T0 bundles every partner question into one task. Most are true blockers: data rules, hosting, restriction list and conditions, decider. Two are not:
  - "Check with Claude Corps so the team does not duplicate an existing tool"
  - "Write down the scope split with JayBird and the Runway," which is already settled because copy-paste stays the default
- Both are open-ended conversations that can grow, and they hold the blocker items to the same Week 8–9 deadline.
- Separately, T0 does **not** include confirming the live pilot project, even though T13 (never cut) depends on "live project confirmed by Week 11." That is a gap, not creep, but it belongs in this task.

**Fix:**
- Move the Claude Corps check and the scope-split note into the first T17 weekly status note as questions, and drop the separate subtasks.
- Add "Confirm the live pilot project and its deadline by Week 11" to T0.

---

#### 10. 🟠 Plan-wide: partner time is the hidden scope

**Problem:** The plan asks IDEAS staff for time in at least 9 separate places:
- T0 call
- T0 baseline timing
- T2 meeting presentation
- T3 timed intake with staff
- T8 flag rating
- T8 scheduled voice rater
- T13 pilot and decider sign-off
- T15 "a staff member follows the guide"
- T17 two feedback sessions

The council's M5 (budget IDEAS staff time) was deferred, and the council called a missed session "the likeliest cause of delay." Each of these asks gates an acceptance criterion.

**Fix:** Bundle the asks into three planned touchpoints and list them in the first T17 status note so Clay and Caroline can book them:
1. **Kickoff call:** T0 items plus baseline timing
2. **Feedback session 1 (Week 11):** T3 timed intake + T8 flag rating
3. **Feedback session 2 / pilot (Weeks 12–14):** T13 pilot, decider sign-off, voice rating if kept

Remove the T15 staff-follows-guide criterion (see issue 11) and the T8 voice rater (see issue 4).

---

#### 11. 🟡 T15 Handoff duplicates T14 Cold-user test

**Problem:**
- T15's criterion "a staff member follows the guide without help" is a second unfamiliar-user test. It lands in Week 15, too late to change anything, and needs another IDEAS session.
- T14 already tests an unfamiliar user in Week 13.

**Fix:**
- Have the T14 tester use the draft guide from T15. That moves one guide section earlier, but it is the same work.
- Change T15's criterion to "the guide was used in the T14 cold-user test and blocking gaps were fixed."

---

#### 12. 🟡 T12 Regression and security: "scripted tests for every acceptance criterion" contradicts the deferral

**Problem:**
- The plan defers "automated test harness as a separate task," yet T12 says to "write scripted tests from the acceptance criteria as each task lands." Across 15+ tasks, that *is* a full test harness.
- At 7 hours it will either overrun or be quietly skipped. Skipping is the worse outcome, because the safety criteria are the ones that most need a test.

**Fix:** Limit scripted tests to the never-cut safety criteria only:
- export of an unapproved record fails (T6)
- zero invented facts pass on test drafts (T8)
- 5 of 5 seeded conditions are flagged (T9)
- every quote is an exact substring (T9)

Everything else is checked manually on the T12 checklist.

---

#### 13. 🟡 T9 Conditions Check: run-time measurement is optional work

**Problem:** "Measure run time (a target, not a gate)" adds instrumentation and reporting for a number nothing depends on.

**Fix:** Drop it. The T1 cost log already captures each call, which covers spend, the only budget risk.

---

#### 14. 🟡 T5 Tracker: test data refers to 12 drafts the plan no longer produces

**Problem:**
- T5 says to "label the 12 unsubmitted drafts as test data," but T2 cut discovery to 4–6 grants and the 12-grant round is on the cut list.
- Leftover references like this lead to work being done to match old wording.

**Fix:** Change the wording to "label the T2 discovery drafts (4–6) as test data."

---

#### 15. 🟡 T1 App foundation: "persistent host" is undefined deployment work

**Problem:**
- "Build … storage on the persistent host" and "a saved record survives an app restart on the chosen host" commit the team to deploying the app somewhere.
- That depends on a T0 answer and has no separate estimate. If IDEAS names nothing, someone will spend hours picking and configuring a host.

**Fix:** Add a default to T1: "If IDEAS has not named a host by end of Week 9, run locally on one team laptop for the pilot and record hosting as a handoff decision for JayBird." The restart test then runs locally.

---

#### 16. 🔴 "If hours run short": the cut order protects creep and gives up the partner's request

**Problem:**
- The cut-first order is T11 → T7 API → **AI-sentence flag (T8)**.
- The AI-sentence flag answers Caroline's stated concern ("some AI may be negatively affecting our submissions"), yet T10 and T4, which address no stated partner need, never appear on the list.
- When time runs out, the plan would keep internal extras and drop a partner request.

**Fix:** Reorder the cut-first list to:
1. T11 Outcome insights
2. T10 Reviewer edits
3. T7 API option
4. T4 voice pack beyond plain storage

Add the AI-sentence flag (T8) to "never cut," or make it the last item to cut.

---

#### 17. 🟡 Plan-level: features were kept while cheaper safeguards were deferred

**Problem:**
- The team kept 9 hours of features the council cut or deferred (T10, T11). Meanwhile it deferred two items that cost almost nothing:
  - **M10:** asking IDEAS whether they want generated drafts or only a checker. This is one question, and the plan says, "IDEAS has not been asked which they prefer."
  - **M12:** what the reviewer sees when a Claude call fails. This is a single error state that prevents a half-checked draft from looking checked.
- Scope creep often looks like this: new features get hours while scope *decisions* and failure handling do not.

**Fix:**
- Add M10 as one question in the T0 kickoff call.
- Add one subtask to T1: "If a Claude call fails, mark the check 'incomplete' and block approval of that record."
- Pay for both with hours freed from T10 and T11.

---

### Hours impact

| Fix | Task | Hours freed (approx.) |
|---|---|---|
| Cut Outcome insights | T11 | 6 |
| Cut Reviewer edits (replace with T4 paste subtask) | T10 | 2 |
| Remove limit retry and voice rating | T8 | 1–2 |
| Remove reused-passage detection | T6 | 1–2 |
| Remove grant-level layout view | T3 | 1 |
| Drop Runway integration doc and open API option | T7 | 1 |
| Drop run-time measurement | T9 | 0.5 |
| **Total freed** | | **≈ 12–14 h** |
| Added: M10 question in T0, API-failure state in T1, pilot confirmation in T0 | T0, T1 | −1.5 |
| **Net** | | **≈ 11–13 h freed** |

**Result:** about 110 hours committed against about 120 hours actually available (128 minus half of Thanksgiving week). That gives roughly a 10-hour reserve instead of a 3-hour deficit, and enough room for the Technical Reviewer's higher estimates on the Conditions Check, Draft Checker, and Handoff.

---

### What is *not* scope creep (leave as is)

- **The T6 hard export block at the storage layer.** It is cheap and the most testable safeguard.
- **Exact-substring quote verification in T9.** It takes a few lines and turns "quoted" into a verified fact.
- **The one-click context block in T3.** It delivers "no re-briefing" without any Runway dependency.
- **The win ratio with its sample size in T5.** IDEAS asked for it directly.
- **The T14 cold-user test.** It is a 2-hour check of the "interns, drop-downs only" requirement.
- **The cut list.** The Grant Finder, Gmail delivery, notifications, Draft Builder, and admin page should all stay cut.

---

## 4. Follow-up discussion

### Reviewer's summary to Leo after the audit

The audit was saved as `docs/audit-scope-creep-leonardo.md` and pushed to the `claude/nice-fermat-oi2688` branch. It lists 17 issues, each with the task, the problem and a fix, and does not rewrite the plan.

**The biggest findings:**
1. **The plan starts about 3 hours over budget.** Thanksgiving week at half capacity leaves about 120 real hours, but 123 are committed.
2. **T11 Outcome insights and T10 Reviewer edits bring back 9 hours of features the council cut or deferred.** T11 will almost certainly just say "not enough history," because IDEAS has about one debrief on record. T10 needs an in-app draft editor that no task builds.
3. **The Draft Checker (T8) has drafting work creeping in.** "Retry at most twice" means the model regenerates the answer, and the voice rating scores the Runway's draft rather than our tool.
4. **Two tasks depend on things that aren't in the plan.** Reused-passage detection in the Review Gate (T6) needs a store of past answers that no task builds. The voice pack (T4) is marked as input to the Draft Checker, but no Draft Checker subtask uses it.
5. **The cut-first list protects the extras and gives up a partner request.** If hours run short, the AI-sentence flag (Caroline's stated concern) is cut third, while T10 and T4 aren't on the list at all.
6. **IDEAS staff are asked for time in at least 9 separate places.** The audit suggests bundling these into three booked sessions.

Applying the fixes frees about 11–13 hours net, giving the plan roughly a 10-hour reserve instead of a 3-hour deficit. The audit also lists what is *not* scope creep and should stay as it is.

### Leo's next request

> Now create an artifact called audit-log-[my first name].md that contains our full conversation: the plan I gave you, your audit findings, and any follow-up discussion. Format it as a clean markdown document.

This document is the result.
