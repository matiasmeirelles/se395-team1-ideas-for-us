# Lab 7 Submission Report: Synthetic Feedback

**Student:** Gabe Cioffi
**Team:** IDEAS for Us
**Team Members:** Gabe Cioffi, Leonardo Takeshi, Charlotte Groton, Tristan Willing
**Submitted:** 11/17/2026, 5:46:18 PM

---

## User Map

1. Grant Writer	Finds grants, writes applications, and checks AI drafts.
2. Executive Director / CEO	Reviews all work.
3. Development Director	Manages strategy and prioritizes grant opportunities.
4. Grant Coordinator	Tracks grant deadlines, eligibility requirements, and application progress.
5. Program Manager	Provides project details and verifies that grants match environmental programs.
6. Finance Manager	Checks grant budgets, financial requirements, and funding restrictions.
7. Operations Manager	Makes sure the AI tool fits existing nonprofit workflows.
8. Environmental Project Coordinator	Identifies funding opportunities for specific sustainability projects.
9. Administrative Assistant	Organizes grant documentation, attachments, and deadlines.
10. Board Member	Reviews funding recommendations and evaluates organizational risks.

## My Persona

### grant writer
_Saved 11/12/2026, 4:06:08 PM_

**Persona:**

Sarah Mitchell
Age: 32

Role: Grant Writer

Organization: IDEAS For Us

Experience: 5 years in nonprofit fundraising, including 2 years focused on environmental grants.

Tech Comfort: Moderate


Background
Sarah works as a grant writer for IDEAS For Us, an environmental nonprofit focused on sustainability and community-based environmental projects. She helps identify funding opportunities, research grant requirements, draft proposals, and coordinate with program staff to collect information.

She balances grant writing with donor communications, reporting deadlines, and other administrative responsibilities. She has limited time to learn new software.
1. Technology Comfort Level
Tools she uses daily:
- Google Docs for writing and editing proposals.
- Google Sheets for tracking grant opportunities and deadlines.
- Gmail for communicating with funders and coworkers.
- Google Drive for storing previous grant applications.
- ChatGPT or Claude occasionally to brainstorm or improve draft wording.
Tools she has never used:
- Coding or Python.
- API integrations.
- Automated web scraping tools.
- Advanced AI agent workflows.
Sarah is comfortable with everyday software but prefers tools that work without complicated setup or technical knowledge.
2. Top Frustration With Current Workflow
Sarah spends several hours each week searching grant databases, foundation websites, and nonprofit newsletters for funding opportunities.

Her biggest frustration is spending time researching grants only to discover that IDEAS For Us does not qualify.

For example, she might spend 30 minutes reviewing a $50,000 environmental grant before discovering it is restricted to organizations in California.

She also has to manually compare opportunities against organizational priorities, geographic eligibility, funding restrictions, and deadlines.

She wishes she could enter IDEAS For Us's eligibility requirements once and receive a list of relevant, verified opportunities.
3. What Would Make Her Stop Using the Tool?
Sarah would stop using the AI grant finder if it repeatedly recommended grants that IDEAS For Us was not eligible for.

Her biggest dealbreaker is inaccurate grant information.

If the tool lists expired opportunities, invents funding amounts, or incorrectly identifies eligibility requirements, she would lose confidence in its recommendations.

She does not have time to independently research every result just to determine whether the AI is correct.

She also would not trust a system that submits applications or makes organizational commitments without staff approval.
4. First Thing She Would Check
Sarah would immediately search for grants using the following criteria:
Sarah's first test search
Focus	Environmental sustainability
Location	Florida or nationwide
Funding amount	$10,000–$100,000
Applicant type	Eligible nonprofit
Deadline	Open opportunities only


She would check whether the results include legitimate grants, working links to official funder websites, current deadlines, and clear explanations of why IDEAS For Us qualifies.

If the tool finds three relevant grants in a few minutes without her having to sort through dozens of irrelevant results, she would consider it useful.
5. A Realistic Quote From Sarah
"I don't need AI to find me 100 grants. I need it to find five that we actually qualify for. If I have to double-check every eligibility requirement and deadline myself, then it's not really saving me time."

Summary
Sarah represents a grant writer who needs an efficient and reliable way to find environmental funding opportunities. She is open to using AI but prioritizes accuracy, simplicity, and transparency. Her willingness to adopt the tool depends on whether it can reduce research time without introducing additional work or risking inaccurate applications.

**Synthetic Data:**

User Persona: Sarah Mitchell, Grant Writer
Organization: IDEAS For Us
Tool Being Tested: AI-Powered Automatic Grant Finder
Dataset: 15 grant opportunities

This fictional dataset represents a messy Google Sheets document that Sarah might maintain while researching environmental grants for IDEAS For Us.

The data intentionally contains outdated deadlines, duplicate grants, missing information, inconsistent formatting, and eligibility restrictions that could confuse an AI grant-finding system.

Important: All grant names, funding amounts, and deadlines below are invented for testing. They are not verified funding opportunities.
Sample Grant Data
ID	Funder / Grant	Amount	Deadline	Notes from Sarah
01	Green Futures Foundation	$25,000	12/15/26	FL nonprofits, sustainability programs. Looks good.
02	EcoAction Community Grant	$10k-50k	Dec 1 2026	Need 501c3. Check eligibility.
03	Sunshine Enviro Fund	$75,000	11/30/26	FL only. Watershed restoration projects.
04	Green Futures Fdn.	25k	12-15-2026	Same as #1?? Mike added this.
05	National Climate Initiative	$100,000	TBD	US organizations. Invitation only?
06	Urban Tree Project Grants	$15,000	10/01/26	Expired? Website still says APPLY.
07	BlueWater Conservation Fund	$40k	1/15/27	Coastal cleanup, 20% match required.
08	CA Green Cities Grant	$60,000	02/01/27	California applicants ONLY.
09	Community Roots Initiative	$8,500	—	Community gardens, no deadline listed.
10	Global Eco Impact Fund	$2,500,000	Mar 2027	Intl projects. Minimum $5M annual org budget.
11	O'Connor Environmental Trust	$20,000	01/20/27	Florida, restoration. Need past grant report.
12	RiverKeepers Fund	$30,000	12/10/26	Reimbursement only, requires upfront spending.
13	Clean Earth Foundation	$35,000	11/18/26	Only 501c3 fiscal sponsors can apply? Verify.
14	Neighborhood Green Grants	$12,000	rolling	Need project location. Link missing.
15	Eco Innovations Program	$50,000	12/31/26	Research institutions only. May need university partner.

All 15 records are fictional. Blank fields, inconsistent formatting, and ambiguous notes are intentional.
Problems intentionally included
Issue	Rows	What the AI should do
Duplicate entry	1, 4	Recognize the same grant despite different names and formatting.
Missing deadline	9	Mark the deadline unknown instead of inventing one.
Expired opportunity	6	Flag the expired deadline even if the application page remains visible.
Geographic ineligibility	8	Reject a California-only opportunity for a Florida applicant.
Unusually high funding	10	Check the minimum organizational budget requirement.
Special character	11	Correctly process the apostrophe in O'Connor.
Inconsistent amounts	2, 4, 7	Interpret "$10k-50k," "25k," and "$40k" correctly.
Incomplete information	5, 14	Request verification rather than assume eligibility.

Nonprofit-specific gotchas
These are problems that a simple AI grant finder could easily overlook.

Gotcha 1 — Matching requirements

Row 7 offers $40,000 but requires a 20% match. The AI must flag that IDEAS For Us may need to contribute additional eligible funding or resources. It must also verify whether the percentage applies to the grant amount or the total project budget.

Gotcha 2 — Reimbursement funding

Row 12 offers $30,000, but funds are reimbursed after eligible expenses are paid. The AI should warn Sarah that IDEAS For Us would need sufficient cash available before reimbursement.

Gotcha 3 — Fiscal sponsorship

Row 13 mentions fiscal sponsors. A regular 501(c)(3) nonprofit is not automatically eligible for a grant specifically restricted to fiscal sponsors. The AI must verify the exact applicant requirements.

Gotcha 4 — Invitation-only funding

Row 5 appears to offer $100,000, but applications may require an invitation. The AI should not treat the opportunity as openly available.
What Sarah expects the AI to accomplish
When Sarah uploads this spreadsheet, she expects the automatic grant finder to:
1. Identify duplicate grants and remove expired opportunities from the active list.
2. Filter out grants with confirmed eligibility conflicts.
3. Flag unclear requirements, missing deadlines, and financial obligations.
4. Rank promising grants based on IDEAS For Us's environmental mission and verified eligibility.
5. Explain why each opportunity was accepted, rejected, or marked for further research, including supporting source links.
Success criteria: The AI should produce a shorter, more useful list of grants without inventing information or overlooking important requirements.

## My Feedback Session

### grant writer
_Saved 11/12/2026, 4:21:29 PM_

# IDEAS Grant Runway: Grant Writer Persona Test Feedback

**Tester persona:** Sarah Mitchell (fictional), Grant Writer, IDEAS For Us. Five years in nonprofit fundraising, moderate tech comfort, about 10 minutes to try a new tool.
**Tool tested:** Editable copy of IDEAS Grant Runway (https://claude.ai/artifact/7KfahagB98FfFw8nzQSsCo)
**Test date:** November 12, 2026
**Method:** Live clicks in Chrome on the published copy. Nothing was submitted, sent or approved. Filters and search were reset afterward.

## Test setup and limitations

- The Runway was actually opened and used. The search, filters, requirements view and packet window were all clicked through live.
- **The tool has no way to import a spreadsheet.** The 15 messy test records could not be loaded, so the import and edge-case steps could not be run. The record audit below is a manual reading of the test rules, not tool output.
- Funder links and grant facts in the Runway were not re-checked against live websites during this test.
- The 15 test records are fictional. None of them can be called genuinely open.

## Sarah's walkthrough

### 1. First impression

- **What she sees:** A "This week" view with three grant cards (deadline, owner, next step, and Sent / Not sending / Missed buttons), pipeline money totals, urgency counts, and a 120-day timeline.
- **What works:** She understands it within a minute. It reads like her Monday deadline spreadsheet.
- **What confuses her:** Terms like "Ready 43", "Priority 31", "Gate" and "Grant Nexus", and file names like `applications/_owners.json` and `_open-questions.md`. These mean nothing to her.
- **Impact:** Lost trust and time on the first screen.
- **Fix:** Add a one-line explanation beside Ready and Priority, and replace file names with plain words such as "add an owner".

### 2. First search: environmental grants, Florida or nationwide, $10K–$100K, open now

| What she typed or clicked | Result |
|---|---|
| "environmental sustainability" | **0 dated · 0 rolling.** No message, and the page jumped to the Missed list |
| "sustainability" | **0 results** |
| "Florida" | 15 dated · 21 rolling |
| "Florida" + Apply directly | 11 dated · 15 rolling |
| "California" | 0 results (correct) |

- **Problem:** Search only matches funder and grant names and locations, not topics. For an environmental grant tool, getting nothing back for "sustainability" looks broken.
- **Problem:** There is no award filter. $250–$5K, $1M and $2.5M–$100M grants all appear alongside her $10K–$100K preference.
- **Problem:** Grants a Florida nonprofit can't apply to still appear. The Keidanren Nature Conservation Fund (developing countries / Japan) is listed with an "Apply: Online application" tag.
- **Impact:** Sarah wastes time or decides the tool doesn't work. Unqualified results bury good ones.
- **Fixes:**
  - Search the summary, eligibility text and focus areas too, not just names.
  - Show "No matches — try the Water or Ecology filter" next to the search box when nothing is found.
  - Add an award-range filter that ranks by preference instead of hiding results.
  - Hide grants with a known geographic exclusion by default, with a "Show ineligible" toggle.

### 3. Eligibility details (the Requirements view)

- **What works:** This is the best part of the tool. Each requirement is marked Met, Condition, Unknown, Not met or Note, with the evidence written underneath, including where facts are still open questions. This is exactly what Sarah wants.
- **Problem:** The ranking contradicts the details. Duke Energy Foundation Florida Grants has two **Not met** items (no electricity-generating equipment, no weatherization or energy-efficiency work), yet it is still ranked **96 Strong**, tagged with the Energy pillar, and labelled "Apply: Online application". Its own notes say the process starts by contacting Duke's state representative.
- **Problem:** "Not met" here means "this funder bans part of IDEAS's work", but Sarah reads it as "IDEAS is ineligible".
- **Impact:** Wrong prioritization. This is the exact mistake Sarah calls a dealbreaker.
- **Fixes:**
  - Rename "Not met" on restrictions to "Excluded activity".
  - Lower the fit score, or show a warning on the card, whenever any item is Not met.
  - Tag grants that need a contact first as "Contact funder first", not "Online application".

### 4. Deadlines and expired grants

- **What works:** Passed deadlines move into a separate "Missed & decided" section. The notes at the bottom say 12 grants whose deadlines had passed were dropped. Each grant shows days left and the exact date.
- **Problem:** The Impact Polk packet is still listed under "Drafted, still live" after its Nov 9 internal deadline (gate) passed. Its text still says "12 days from this draft" when only 4 days are left.
- **Fix:** Work out day counts in packet text when the page loads, and move a packet out of "still live" once its internal deadline has passed and nothing is recorded.

### 5. Review and submission controls

- **What works:**
  - Packets say "Nothing has been submitted. A person reviews and submits."
  - Unknown figures are left blank as `[NEEDS FIGURE]` instead of made up.
  - Official funder and guideline links are cited.
  - Nothing in the tool sends or submits anything.
- **Problem:** The **"Sent"** button sounds like it sends the application. It only records that a person already submitted it.
- **Problem:** **"Approve for applications/"** doesn't say what happens when you click it.
- **Impact:** Risk of a false belief that something went out, or fear of clicking at all.
- **Fixes:** Rename "Sent" to "Mark as submitted" and "Approve for applications/" to "Approve draft (does not submit)".

### 6. Messy-data import

- **Result:** Not testable. The Runway has no way to import or paste spreadsheet rows, only its own research data.
- **Impact:** Sarah can't check her existing Google Sheets tracker against the tool.
- **Fix:** Add a CSV / Google Sheets import that keeps every row, stores the original values beside the cleaned ones, flags duplicates, and never drops rows without saying so.

## Messy synthetic data test (live attempt)

Sarah tried to run her 15-row tracker through the tool.

| What she tried | What happened |
|---|---|
| Look for an import, upload or paste option | **None exists.** The only data in the tool is the Runway's own research records |
| Search "Green Futures" (records 01/04) | 0 dated · 0 rolling, with no message |
| Search "O'Connor" (record 11, apostrophe) | 0 results. The page did **not** break on the apostrophe, but there's no record to find |
| Search "$10k-50k" (record 02 raw amount) | 0 results, because amounts aren't searchable |
| Each search | The page jumped down to the Missed list, away from the search box |

**What breaks:** the whole import step. None of the edge cases (duplicate 01/04, expired 06, California-only 08, blank deadline 09, $2.5M / $5M budget 10, fiscal sponsor 13, invitation-only 05) can reach the tool, so none of its handling can be checked.

**What gets silently wrong:** an empty result shows "0 dated · 0 rolling" with no explanation. Sarah can't tell "no such grant", "not imported" and "search doesn't look there" apart. She might wrongly conclude a grant from her tracker is ineligible or closed.

**What Sarah notices immediately:** "Where do I put my spreadsheet?" Without import, the tool can't replace her Google Sheets tracker. She'd have to keep both.

**How the tool's own data handles the same kinds of edge cases (from browsing it):**

| Edge case | Runway behavior | Verdict |
|---|---|---|
| Expired deadline (like 06) | Moved to "Missed & decided"; 12 stale records disclosed at the bottom | Good |
| Geographic exclusion (like 08) | Keidanren (Japan / developing countries) still listed as "Apply: Online application" | Fails |
| Month-only or unclear deadline (like 10) | Not observed in this test | Untested |
| Invitation-only or contact-first (like 05) | "Letter of inquiry first" and "Contact funder first" tags exist, but Duke is mis-tagged "Online application" | Mixed |
| Budget threshold (like 10) | Shown as "Condition" / "Unknown" with evidence (e.g. DARRP notes say the $2.5M minimum is about twice IDEAS's revenue) | Good |
| Duplicates (like 01/04) | Not observed in this test | Untested |
| Unknown facts | Left as `[NEEDS FIGURE]` / "Unknown", never made up | Good |

**Fix:** add a CSV / Google Sheets import that:
- keeps every row and its raw values;
- turns "25k", "$40k" and "$10k-50k" into numbers while keeping the original text;
- reads "12/15/26", "12-15-2026" and "Dec 1 2026" as dates, and marks "Mar 2027" as month-only;
- flags likely duplicates for a person to confirm;
- marks blanks as "unknown";
- runs every row through the same Requirements check.

Also show why a search returned nothing.

## 15-record audit (manual, not tool output)

| ID | Funder | Award | Deadline | Duplicate? | Status | Issue / next action |
|---|---|---|---|---|---|---|
| 01 | Green Futures Foundation | $25,000 | Dec 15, 2026 | Yes, with 04 | possible match | Keep one record; confirm the program page |
| 02 | EcoAction Community Grant | $10,000–$50,000 | Dec 1, 2026 | No | needs verification | Confirm the 501(c)(3) requirement and documents |
| 03 | Sunshine Enviro Fund | $75,000 | Nov 30, 2026 | No | possible match | Florida only; confirm IDEAS has a watershed project |
| 04 | Green Futures Fdn. | $25,000 (raw "25k") | Dec 15, 2026 | Yes, with 01 | duplicate | Merge with 01 |
| 05 | National Climate Initiative | $100,000 | TBD | No | needs verification | Possibly invitation only; don't show as open |
| 06 | Urban Tree Project Grants | $15,000 | Oct 1, 2026 | No | expired | A live "APPLY" button doesn't prove it's open |
| 07 | BlueWater Conservation Fund | $40,000 (raw "$40k") | Jan 15, 2027 | No | needs verification | 20% match: confirm whether it's based on the request or the total project cost; don't commit funds |
| 08 | CA Green Cities Grant | $60,000 | Feb 1, 2027 | No | excluded by known restriction | California applicants only |
| 09 | Community Roots Initiative | $8,500 | Unknown (blank) | No | needs verification | No deadline; below the preferred range but not ineligible |
| 10 | Global Eco Impact Fund | $2,500,000 | March 2027 (month only) | No | needs verification | Requires a $5M+ annual budget; IDEAS's budget not confirmed |
| 11 | O'Connor Environmental Trust | $20,000 | Jan 20, 2027 | No | needs verification | Apostrophe kept; confirm the past grant report was filed |
| 12 | RiverKeepers Fund | $30,000 | Dec 10, 2026 | No | needs verification | Reimbursement only; IDEAS must spend the money first |
| 13 | Clean Earth Foundation | $35,000 | Nov 18, 2026 | No | needs verification | Fiscal-sponsor rule unclear; due in 6 days |
| 14 | Neighborhood Green Grants | $12,000 | Rolling | No | needs verification | Link missing; needs a project location |
| 15 | Eco Innovations Program | $50,000 | Dec 31, 2026 | No | needs verification | Research institutions only; a university may have to lead |

## Critical failures: fix now

| # | Problem | Found in | Fix |
|---|---|---|---|
| 1 | Topic search returns nothing ("sustainability" = 0) | First search | Search summaries, eligibility and focus areas; show a no-results hint |
| 2 | Top-ranked grants carry "Not met" items | Requirements view (Duke Energy) | "Not met" lowers the score and shows a warning on the card |
| 3 | No spreadsheet import | Messy-data import | Add a CSV / Sheets import that keeps raw values and flags duplicates |
| 4 | "Sent" and "Approve for applications/" are misleading | Review controls | Rename to "Mark as submitted" and "Approve draft (does not submit)" |
| 5 | Geographically ineligible grants shown as appliable | First search (Keidanren) | Hide known exclusions by default |

## Improvements: fix later

- An award-range filter, treated as a preference.
- Plain-language explanations for Ready, Priority and Gate.
- Packet day counts worked out live, not frozen at the date the packet was drafted.
- Separate tags for "Match required", "Reimbursement only", "Invitation only" and "Contact funder first".
- Filters that also apply to the "This week" cards (today they only change the counts and lists below).
- Remove file names (`applications/…`, `_open-questions.md`) from staff-facing text.

## Out of scope / ignore

- **Light/dark switch and chart styling:** these don't affect grant decisions.
- **Export format details (CSV/PDF columns):** useful later, but not part of Sarah's first 10 minutes.

## Closing answers in Sarah's voice

1. **Would you use this tool next week?**
   "Yes, but carefully. The requirements breakdown would save me hours. It shows which rules we meet, which we don't, and why. I'd use it to cut my list down, then check anything marked 'Strong' myself, because one top-ranked grant had two 'Not met' items. And I'd stop searching by topic, since 'environmental sustainability' gave me nothing."

2. **Single most important fix before you'd trust it?**
   "The ranking has to agree with the details. If a grant says 'Not met' anywhere, it can't also say '96 Strong' and 'Apply: Online application.' That's exactly the mistake I'm trying to avoid."

3. **What did it get right about your workflow?**
   "It never pretends. It leaves blanks instead of making up figures, links to the funder's own page, and says plainly that nothing was submitted. Expired deadlines are kept separate, and the 'This week' view shows what's due, who owns it and what's blocking it, which is what my Monday spreadsheet is supposed to do."

4. **One sentence for a coworker:**
   "It's a grant deadline board that does the eligibility homework for you. Just don't trust the 'Strong' label without opening the requirements, and search by state, not by topic."

## Questions for IDEAS For Us staff

1. What was IDEAS's actual annual operating budget last fiscal year? It decides record 10 and every funder's percentage cap.
2. Does IDEAS have cash or in-kind support it could commit to a 20% match (record 07)? Who is allowed to approve a match?
3. Are any past grant reports outstanding that would block new applications (record 11)?

---

## Team Summary

### All Personas (4)
- **grant writer** by Gabe Cioffi (11/12/2026, 4:06:08 PM)
- **Operations Manager** by Leonardo Takeshi (11/12/2026, 4:19:46 PM)
- **Grant Cordinater** by Charlotte Groton (11/12/2026, 4:24:03 PM)
- **Program Manager** by Tristan Willing (11/17/2026, 4:02:49 PM)

### All Feedback Sessions (4)
- **grant writer** by Gabe Cioffi (11/12/2026, 4:21:29 PM)
- **Operations Manager** by Leonardo Takeshi (11/12/2026, 4:27:08 PM)
- **Grant Cordinater** by Charlotte Groton (11/12/2026, 4:32:17 PM)
- **Program Manager** by Tristan Willing (11/17/2026, 4:14:40 PM)

### Triage
By Charlotte Groton (11/17/2026, 3:52:02 PM)

# IDEAS Grant Runway: Grant Writer Persona Test Feedback

**Tester persona:** Sarah Mitchell (fictional), Grant Writer, IDEAS For Us. Five years in nonprofit fundraising, moderate tech comfort, about 10 minutes to try a new tool.
**Tool tested:** Editable copy of IDEAS Grant Runway (https://claude.ai/artifact/7KfahagB98FfFw8nzQSsCo)
**Test date:** November 12, 2026
**Method:** Live clicks in Chrome on the published copy. Nothing was submitted, sent or approved. Filters and search were reset afterward.

## Test setup and limitations

- The Runway was actually opened and used. The search, filters, requirements view and packet window were all clicked through live.
- **The tool has no way to import a spreadsheet.** The 15 messy test records could not be loaded, so the import and edge-case steps could not be run. The record audit below is a manual reading of the test rules, not tool output.
- Funder links and grant facts in the Runway were not re-checked against live websites during this test.
- The 15 test records are fictional. None of them can be called genuinely open.

## Sarah's walkthrough

### 1. First impression

- **What she sees:** A "This week" view with three grant cards (deadline, owner, next step, and Sent / Not sending / Missed buttons), pipeline money totals, urgency counts, and a 120-day timeline.
- **What works:** She understands it within a minute. It reads like her Monday deadline spreadsheet.
- **What confuses her:** Terms like "Ready 43", "Priority 31", "Gate" and "Grant Nexus", and file names like `applications/_owners.json` and `_open-questions.md`. These mean nothing to her.
- **Impact:** Lost trust and time on the first screen.
- **Fix:** Add a one-line explanation beside Ready and Priority, and replace file names with plain words such as "add an owner".

### 2. First search: environmental grants, Florida or nationwide, $10K–$100K, open now

| What she typed or clicked | Result |
|---|---|
| "environmental sustainability" | **0 dated · 0 rolling.** No message, and the page jumped to the Missed list |
| "sustainability" | **0 results** |
| "Florida" | 15 dated · 21 rolling |
| "Florida" + Apply directly | 11 dated · 15 rolling |
| "California" | 0 results (correct) |

- **Problem:** Search only matches funder and grant names and locations, not topics. For an environmental grant tool, getting nothing back for "sustainability" looks broken.
- **Problem:** There is no award filter. $250–$5K, $1M and $2.5M–$100M grants all appear alongside her $10K–$100K preference.
- **Problem:** Grants a Florida nonprofit can't apply to still appear. The Keidanren Nature Conservation Fund (developing countries / Japan) is listed with an "Apply: Online application" tag.
- **Impact:** Sarah wastes time or decides the tool doesn't work. Unqualified results bury good ones.
- **Fixes:**
  - Search the summary, eligibility text and focus areas too, not just names.
  - Show "No matches — try the Water or Ecology filter" next to the search box when nothing is found.
  - Add an award-range filter that ranks by preference instead of hiding results.
  - Hide grants with a known geographic exclusion by default, with a "Show ineligible" toggle.

### 3. Eligibility details (the Requirements view)

- **What works:** This is the best part of the tool. Each requirement is marked Met, Condition, Unknown, Not met or Note, with the evidence written underneath, including where facts are still open questions. This is exactly what Sarah wants.
- **Problem:** The ranking contradicts the details. Duke Energy Foundation Florida Grants has two **Not met** items (no electricity-generating equipment, no weatherization or energy-efficiency work), yet it is still ranked **96 Strong**, tagged with the Energy pillar, and labelled "Apply: Online application". Its own notes say the process starts by contacting Duke's state representative.
- **Problem:** "Not met" here means "this funder bans part of IDEAS's work", but Sarah reads it as "IDEAS is ineligible".
- **Impact:** Wrong prioritization. This is the exact mistake Sarah calls a dealbreaker.
- **Fixes:**
  - Rename "Not met" on restrictions to "Excluded activity".
  - Lower the fit score, or show a warning on the card, whenever any item is Not met.
  - Tag grants that need a contact first as "Contact funder first", not "Online application".

### 4. Deadlines and expired grants

- **What works:** Passed deadlines move into a separate "Missed & decided" section. The notes at the bottom say 12 grants whose deadlines had passed were dropped. Each grant shows days left and the exact date.
- **Problem:** The Impact Polk packet is still listed under "Drafted, still live" after its Nov 9 internal deadline (gate) passed. Its text still says "12 days from this draft" when only 4 days are left.
- **Fix:** Work out day counts in packet text when the page loads, and move a packet out of "still live" once its internal deadline has passed and nothing is recorded.

### 5. Review and submission controls

- **What works:**
  - Packets say "Nothing has been submitted. A person reviews and submits."
  - Unknown figures are left blank as `[NEEDS FIGURE]` instead of made up.
  - Official funder and guideline links are cited.
  - Nothing in the tool sends or submits anything.
- **Problem:** The **"Sent"** button sounds like it sends the application. It only records that a person already submitted it.
- **Problem:** **"Approve for applications/"** doesn't say what happens when you click it.
- **Impact:** Risk of a false belief that something went out, or fear of clicking at all.
- **Fixes:** Rename "Sent" to "Mark as submitted" and "Approve for applications/" to "Approve draft (does not submit)".

### 6. Messy-data import

- **Result:** Not testable. The Runway has no way to import or paste spreadsheet rows, only its own research data.
- **Impact:** Sarah can't check her existing Google Sheets tracker against the tool.
- **Fix:** Add a CSV / Google Sheets import that keeps every row, stores the original values beside the cleaned ones, flags duplicates, and never drops rows without saying so.

## Messy synthetic data test (live attempt)

Sarah tried to run her 15-row tracker through the tool.

| What she tried | What happened |
|---|---|
| Look for an import, upload or paste option | **None exists.** The only data in the tool is the Runway's own research records |
| Search "Green Futures" (records 01/04) | 0 dated · 0 rolling, with no message |
| Search "O'Connor" (record 11, apostrophe) | 0 results. The page did **not** break on the apostrophe, but there's no record to find |
| Search "$10k-50k" (record 02 raw amount) | 0 results, because amounts aren't searchable |
| Each search | The page jumped down to the Missed list, away from the search box |

**What breaks:** the whole import step. None of the edge cases (duplicate 01/04, expired 06, California-only 08, blank deadline 09, $2.5M / $5M budget 10, fiscal sponsor 13, invitation-only 05) can reach the tool, so none of its handling can be checked.

**What gets silently wrong:** an empty result shows "0 dated · 0 rolling" with no explanation. Sarah can't tell "no such grant", "not imported" and "search doesn't look there" apart. She might wrongly conclude a grant from her tracker is ineligible or closed.

**What Sarah notices immediately:** "Where do I put my spreadsheet?" Without import, the tool can't replace her Google Sheets tracker. She'd have to keep both.

**How the tool's own data handles the same kinds of edge cases (from browsing it):**

| Edge case | Runway behavior | Verdict |
|---|---|---|
| Expired deadline (like 06) | Moved to "Missed & decided"; 12 stale records disclosed at the bottom | Good |
| Geographic exclusion (like 08) | Keidanren (Japan / developing countries) still listed as "Apply: Online application" | Fails |
| Month-only or unclear deadline (like 10) | Not observed in this test | Untested |
| Invitation-only or contact-first (like 05) | "Letter of inquiry first" and "Contact funder first" tags exist, but Duke is mis-tagged "Online application" | Mixed |
| Budget threshold (like 10) | Shown as "Condition" / "Unknown" with evidence (e.g. DARRP notes say the $2.5M minimum is about twice IDEAS's revenue) | Good |
| Duplicates (like 01/04) | Not observed in this test | Untested |
| Unknown facts | Left as `[NEEDS FIGURE]` / "Unknown", never made up | Good |

**Fix:** add a CSV / Google Sheets import that:
- keeps every row and its raw values;
- turns "25k", "$40k" and "$10k-50k" into numbers while keeping the original text;
- reads "12/15/26", "12-15-2026" and "Dec 1 2026" as dates, and marks "Mar 2027" as month-only;
- flags likely duplicates for a person to confirm;
- marks blanks as "unknown";
- runs every row through the same Requirements check.

Also show why a search returned nothing.

## 15-record audit (manual, not tool output)

| ID | Funder | Award | Deadline | Duplicate? | Status | Issue / next action |
|---|---|---|---|---|---|---|
| 01 | Green Futures Foundation | $25,000 | Dec 15, 2026 | Yes, with 04 | possible match | Keep one record; confirm the program page |
| 02 | EcoAction Community Grant | $10,000–$50,000 | Dec 1, 2026 | No | needs verification | Confirm the 501(c)(3) requirement and documents |
| 03 | Sunshine Enviro Fund | $75,000 | Nov 30, 2026 | No | possible match | Florida only; confirm IDEAS has a watershed project |
| 04 | Green Futures Fdn. | $25,000 (raw "25k") | Dec 15, 2026 | Yes, with 01 | duplicate | Merge with 01 |
| 05 | National Climate Initiative | $100,000 | TBD | No | needs verification | Possibly invitation only; don't show as open |
| 06 | Urban Tree Project Grants | $15,000 | Oct 1, 2026 | No | expired | A live "APPLY" button doesn't prove it's open |
| 07 | BlueWater Conservation Fund | $40,000 (raw "$40k") | Jan 15, 2027 | No | needs verification | 20% match: confirm whether it's based on the request or the total project cost; don't commit funds |
| 08 | CA Green Cities Grant | $60,000 | Feb 1, 2027 | No | excluded by known restriction | California applicants only |
| 09 | Community Roots Initiative | $8,500 | Unknown (blank) | No | needs verification | No deadline; below the preferred range but not ineligible |
| 10 | Global Eco Impact Fund | $2,500,000 | March 2027 (month only) | No | needs verification | Requires a $5M+ annual budget; IDEAS's budget not confirmed |
| 11 | O'Connor Environmental Trust | $20,000 | Jan 20, 2027 | No | needs verification | Apostrophe kept; confirm the past grant report was filed |
| 12 | RiverKeepers Fund | $30,000 | Dec 10, 2026 | No | needs verification | Reimbursement only; IDEAS must spend the money first |
| 13 | Clean Earth Foundation | $35,000 | Nov 18, 2026 | No | needs verification | Fiscal-sponsor rule unclear; due in 6 days |
| 14 | Neighborhood Green Grants | $12,000 | Rolling | No | needs verification | Link missing; needs a project location |
| 15 | Eco Innovations Program | $50,000 | Dec 31, 2026 | No | needs verification | Research institutions only; a university may have to lead |

## Critical failures: fix now

| # | Problem | Found in | Fix |
|---|---|---|---|
| 1 | Topic search returns nothing ("sustainability" = 0) | First search | Search summaries, eligibility and focus areas; show a no-results hint |
| 2 | Top-ranked grants carry "Not met" items | Requirements view (Duke Energy) | "Not met" lowers the score and shows a warning on the card |
| 3 | No spreadsheet import | Messy-data import | Add a CSV / Sheets import that keeps raw values and flags duplicates |
| 4 | "Sent" and "Approve for applications/" are misleading | Review controls | Rename to "Mark as submitted" and "Approve draft (does not submit)" |
| 5 | Geographically ineligible grants shown as appliable | First search (Keidanren) | Hide known exclusions by default |

## Improvements: fix later

- An award-range filter, treated as a preference.
- Plain-language explanations for Ready, Priority and Gate.
- Packet day counts worked out live, not frozen at the date the packet was drafted.
- Separate tags for "Match required", "Reimbursement only", "Invitation only" and "Contact funder first".
- Filters that also apply to the "This week" cards (today they only change the counts and lists below).
- Remove file names (`applications/…`, `_open-questions.md`) from staff-facing text.

## Out of scope / ignore

- **Light/dark switch and chart styling:** these don't affect grant decisions.
- **Export format details (CSV/PDF columns):** useful later, but not part of Sarah's first 10 minutes.

## Closing answers in Sarah's voice

1. **Would you use this tool next week?**
   "Yes, but carefully. The requirements breakdown would save me hours. It shows which rules we meet, which we don't, and why. I'd use it to cut my list down, then check anything marked 'Strong' myself, because one top-ranked grant had two 'Not met' items. And I'd stop searching by topic, since 'environmental sustainability' gave me nothing."

2. **Single most important fix before you'd trust it?**
   "The ranking has to agree with the details. If a grant says 'Not met' anywhere, it can't also say '96 Strong' and 'Apply: Online application.' That's exactly the mistake I'm trying to avoid."

3. **What did it get right about your workflow?**
   "It never pretends. It leaves blanks instead of making up figures, links to the funder's own page, and says plainly that nothing was submitted. Expired deadlines are kept separate, and the 'This week' view shows what's due, who owns it and what's blocking it, which is what my Monday spreadsheet is supposed to do."

4. **One sentence for a coworker:**
   "It's a grant deadline board that does the eligibility homework for you. Just don't trust the 'Strong' label without opening the requirements, and search by state, not by topic."

## Questions for IDEAS For Us staff

1. What was IDEAS's actual annual operating budget last fiscal year? It decides record 10 and every funder's percentage cap.
2. Does IDEAS have cash or in-kind support it could commit to a 20% match (record 07)? Who is allowed to approve a match?
3. Are any past grant reports outstanding that would block new applications (record 11)?

### Fix Plan
By Tristan Willing (11/17/2026, 4:26:55 PM)

| 3 | No spreadsheet import | Messy-data import | Add a CSV / Sheets import that keeps raw values and flags duplicates - Charlotte - Organize and import data I clean and legible format. 

| 1 | Topic search returns nothing ("sustainability" = 0) | First search | Search summaries, eligibility and focus areas; show a no-results hint - Gabe - add geographic filter for the correct grants and ensure accuracy. 

| 4 | "Sent" and "Approve for applications/" are misleading | Review controls | Rename to "Mark as submitted" and "Approve draft (does not submit)" - Leo - Rename labels for more accurate application updates.

| 5 | Geographically ineligible grants shown as appliable | First search (Keidanren) | Hide known exclusions by default - Tristan - filter Geographically ineligible grants out of the system and dont show these.

---

## Activity Log

- 11/12/2026, 4:03:03 PM -- **Gabe Cioffi** Saved user map
