# Scope Creep Audit: AI Grant Agent Project Plan

**Reviewer role:** Senior project reviewer (scope creep lens)
**Prepared for:** Catalyst Collective, SE 395-2 (IDEAS For Us)
**Prepared by:** Leonardo Takeshi Campi Kiyose, with Claude
**Date:** November 4, 2026
**Plan audited:** *AI Grant Agent Project Plan* (unified plan, Weeks 8–15, 123 of 128 hours committed)

This audit lists problems and fixes only. It does not rewrite the plan.

---

## Summary

The plan's core is well scoped: Profile, Tracker, Review Gate, Conditions Check, Draft Checker and the pilot. Scope creep comes in three ways:

1. **Features the council cut or deferred were brought back** (T10, T11). That is 9 hours of new capability for things IDEAS did not ask for.
2. **Subtasks quietly grow a task past its definition.** The "never rewrites" Draft Checker has a retry loop and a voice rating. The Review Gate has reused-passage detection backed by a store that no task builds. The Profile carries a layout task for other screens.
3. **Partner time is spread across many separate asks.** The council's M5 (budget IDEAS staff time) was deferred, yet the plan asks IDEAS staff for something in at least 9 places.

The plan also has **no real reserve.** The 128-hour budget assumes full weeks, but T17 plans Thanksgiving week at half capacity. That leaves about 120 hours available against 123 committed, so the plan starts about 3 hours over. Every item below that frees hours also fixes this.

**Severity:** 🔴 High: adds unbudgeted work or threatens a never-cut item · 🟠 Medium: grows a task past its definition · 🟡 Low: small drift or duplication

---

## Issues and fixes

### 1. 🔴 T11 Outcome insights: a feature nobody asked for, built on one data point

**Problem:**
- The council voted 3–1 to cut this. IDEAS asked to *track* win ratios and debriefs (Clay, Oct 9); they did not ask for a suggestion engine.
- IDEAS has about **one** debrief on record (the $4.7M / 84-of-100). The minimum-data rule in T11 will therefore almost certainly display "not enough history."
- The task can pass every acceptance criterion while giving IDEAS nothing. It still costs 6 hours plus four subtasks of UI: suggestions, source links, the threshold, and accept/dismiss.

**Fix:** Cut T11.
- T5 already stores and displays debrief score and notes, which is the part Clay asked for.
- Record "outcome insights after 5+ debriefs" on the post-handoff list.
- **Saves 6 h** and restores a real reserve.

---

### 2. 🔴 T10 Reviewer edits saved to the context pack: depends on an editor that no task builds

**Problem:**
- T8 is a checker that "flags, never rewrites," and no task gives reviewers an in-app place to edit a draft. So the "reviewer edits" T10 captures have no source.
- Making T10 work means building a draft editor, a pending-edit queue, and an approve/reject flow for edits. That is a second review gate on top of T6, and none of it is in the 3-hour estimate.
- The proposal says the voice-training loop already works outside the tool and should not change. The council's Scope Guardian voted to defer it for that reason.

**Fix:** Cut T10 as a separate task.
- If the team wants the voice pack to grow, add one subtask to T4: "Paste an approved final answer into the voice pack, with the approver's name and date." That is under 1 hour and needs no edit workflow.
- **Saves 2–3 h** and removes hidden editor scope.

---

### 3. 🟠 T8 Draft Checker: "retry at most twice" is a Draft Builder in disguise

**Problem:**
- The first T8 subtask says to "check the character limit; retry at most twice, then flag." A retry means the model regenerates the answer, which is drafting.
- That contradicts the task's own title ("flags, never rewrites") and the team's decision to build the Checker instead of the Draft Builder.
- It also adds model calls, cost, and a new failure mode: a regenerated answer could introduce invented facts *after* the fact check has run.

**Fix:** Make the limit check pure code.
- Count characters and words and flag any over-limit answer for a human to shorten. Remove the retry.
- This matches the council's view that the limit check is "plain code with no model risk."

---

### 4. 🟠 T8 Draft Checker: the voice rating measures the Runway, not our tool

**Problem:**
- The subtask "Record the voice rating (4/5 target) with a scheduled rater" scores the *draft*, and the Runway wrote that draft. Our Checker never writes text.
- A low or high score says nothing about whether our tool works, but it still needs a scheduled IDEAS rater. It is carried over from the Draft Builder plans, which were cut.

**Fix:** Remove the voice rating from T8.
- Keep the subtask that rates the *flags* ("staff rate a sample of the AI-sentence flags"), which does measure our tool.
- If the team wants a voice number for the final report, collect it once during the T13 pilot, not as a T8 deliverable.

---

### 5. 🟠 T4 Context pack and voice pack: "voice input to the Draft Checker" has no matching feature

**Problem:**
- T4's last subtask makes Clay's five grants "available to the Draft Checker as voice input," and T8 lists T4 as a dependency. Yet no T8 subtask uses voice examples.
- The AI-sentence flagger uses Caroline's pattern list plus a Claude pass. A "compare to Clay's voice" feature is implied but never defined, estimated, or tested. That is a classic opening for scope creep: someone will build it during Weeks 10–12 because the dependency says to.

**Fix:** Pick one of these.
- **(a)** Remove the T4 → T8 dependency and keep T4 as storage only, so the examples are on hand for the post-handoff list or for Runway briefing via the context block.
- **(b)** Define one bounded use in T8: "Include up to 2 of Clay's examples in the AI-sentence prompt as reference." Add that to T8's estimate.

Option (a) is the smaller scope.

---

### 6. 🟠 T6 Review Gate: reused-passage detection needs a store that no task builds

**Problem:**
- T6 says to highlight "reused passages: exact match against stored answers only."
- No task stores past answers. Win/loss tagging, past-application storage, and searchable documents are all cut, and T4 stores only Clay's five grants.
- Shipping this subtask therefore means building an answers store. It also partly duplicates T8: "highlight numbers and gaps" repeats the invented-fact and gap flags.

**Fix:**
- Remove reused-passage detection from T6 and put it on the post-handoff list.
- Change "highlight numbers and gaps" to "display T8's flags on the reviewer screen," so the logic lives in one place and T6 only renders it.

---

### 7. 🟠 T3 Project Profile: the "one-screen view of key grant information" is design work for other tasks

**Problem:**
- The Profile is project-level, but this subtask asks for a *grant*-level view to serve "as the layout guide for review and tracker screens." That is a UI design deliverable for T5 and T6, scheduled inside T3.
- It sits on the critical path for the floor: T3 has to pass Checkpoint 1 in Week 10.
- The council kept it only "as a layout guideline … not a separate dashboard" (row 10b).

**Fix:** Remove it from T3.
- Add a short layout note (which fields appear first) to the T1 schema doc, and let T5 and T6 own their own screens.

---

### 8. 🟠 T7 Airtable export: integration work beyond the CSV

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

### 9. 🟠 T0 Kickoff and partner inputs: nine subtasks in 6 hours, and two are not blockers

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

### 10. 🟠 Plan-wide: partner time is the hidden scope

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

### 11. 🟡 T15 Handoff duplicates T14 Cold-user test

**Problem:**
- T15's criterion "a staff member follows the guide without help" is a second unfamiliar-user test. It lands in Week 15, too late to change anything, and needs another IDEAS session.
- T14 already tests an unfamiliar user in Week 13.

**Fix:**
- Have the T14 tester use the draft guide from T15. That moves one guide section earlier, but it is the same work.
- Change T15's criterion to "the guide was used in the T14 cold-user test and blocking gaps were fixed."

---

### 12. 🟡 T12 Regression and security: "scripted tests for every acceptance criterion" contradicts the deferral

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

### 13. 🟡 T9 Conditions Check: run-time measurement is optional work

**Problem:** "Measure run time (a target, not a gate)" adds instrumentation and reporting for a number nothing depends on.

**Fix:** Drop it. The T1 cost log already captures each call, which covers spend, the only budget risk.

---

### 14. 🟡 T5 Tracker: test data refers to 12 drafts the plan no longer produces

**Problem:**
- T5 says to "label the 12 unsubmitted drafts as test data," but T2 cut discovery to 4–6 grants and the 12-grant round is on the cut list.
- Leftover references like this lead to work being done to match old wording.

**Fix:** Change the wording to "label the T2 discovery drafts (4–6) as test data."

---

### 15. 🟡 T1 App foundation: "persistent host" is undefined deployment work

**Problem:**
- "Build … storage on the persistent host" and "a saved record survives an app restart on the chosen host" commit the team to deploying the app somewhere.
- That depends on a T0 answer and has no separate estimate. If IDEAS names nothing, someone will spend hours picking and configuring a host.

**Fix:** Add a default to T1: "If IDEAS has not named a host by end of Week 9, run locally on one team laptop for the pilot and record hosting as a handoff decision for JayBird." The restart test then runs locally.

---

### 16. 🔴 "If hours run short": the cut order protects creep and gives up the partner's request

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

### 17. 🟡 Plan-level: features were kept while cheaper safeguards were deferred

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

## Hours impact

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

## What is *not* scope creep (leave as is)

- **The T6 hard export block at the storage layer.** It is cheap and the most testable safeguard.
- **Exact-substring quote verification in T9.** It takes a few lines and turns "quoted" into a verified fact.
- **The one-click context block in T3.** It delivers "no re-briefing" without any Runway dependency.
- **The win ratio with its sample size in T5.** IDEAS asked for it directly.
- **The T14 cold-user test.** It is a 2-hour check of the "interns, drop-downs only" requirement.
- **The cut list.** The Grant Finder, Gmail delivery, notifications, Draft Builder, and admin page should all stay cut.
