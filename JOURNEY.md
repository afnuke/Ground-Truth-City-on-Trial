# The Journey — How City on Trial Was Built

This is the honest build record for Ground Truth: City on Trial, Volume Two of the Ground Truth series. Not the pitch — the road. What worked, what got caught, and what it cost to get 37 South Carolina cities into one courthouse.

## Case 001: Greenville first

The docket opened where the builder lives. Greenville, South Carolina was verified figure by figure out of the city's own audited Annual Comprehensive Financial Report before a single other city was touched: 72,935 residents; $248.7 million in FY25 revenue against $214.8 million in expenses; 46¢ of every General Fund dollar to police and fire; a reserve of $30,298,882; bonded debt of $118,847,000. Six exhibits, one resident jury, and the rule the whole series runs on — **the app presents the record; it never renders a verdict.**

Greenville also taught the first hard lesson: the city does not publish its payroll. Exhibit D stood empty rather than be filled with an estimate. An empty chair in the courtroom is evidence too.

## The docket: 41 scoped, 37 built

All 41 South Carolina municipalities over 10,000 people were scoped for the docket. Thirty-seven made it into the app — Cases 001–037, Greenville through Forest Acres — each from its city's own ACFR, each with its source and fiscal year printed on the figure. Four cities are named holdouts, and the reason for each is on the record in SOUTHEAST.md: Aiken awaiting its audit, Rock Hill and North Augusta walled behind their websites at research time, Cayce's book sealed in a protected agenda packet.

## The FOIA campaign

Cities that don't publish payroll were asked for it — the same record, the same letter, under S.C. Code §30-4-40(a)(6). On **November 4, 2026, 37 records requests went live**, with determinations due **November 18–19, 2026**. The design is deliberate: identical asks to every city, so the answers — and the prices — are comparable.

South Carolina sells labor, not the record. Across all 37 requests, exactly **one written fee quote** has come back: **North Myrtle Beach, $27.89** — an hour of a junior accountant's time, records held pending payment. Whether to pay it is the builder's call, and it stays his call. An unreasonable quote doesn't end an exhibit; it becomes one — the price of the record, shown in the app.

## The audit: zero missing, zero invented

The cases were written by an AI builder (Gemini, in Android Studio) working from paste-ready directives — and never trusted on its own say-so. The discipline that held the line:

- **One or two cases per pass.** Small directives, roughly 16–27K of instruction at a time. Bigger passes fabricated.
- **Every figure audited after every pass** — directive tokens checked against source tokens, per case. The gate for shipping a case: **missing must be 0, invented must be 0.**
- Detail lines that still slipped through were restored in a final micro-correction pass, verbatim.

Batch 2 — Cases 011–037 — carries **2,709 figures. Audited: 0 missing, 0 invented.**

## The build that never shipped

The audit discipline exists because it was earned. The first bench build of the expanded case set came back with a builder's report of **BUILD SUCCESSFUL** — and an APK whose figures did not match the audited data. It was caught in verification before it ever reached a phone. Its fingerprint is kept on this record so it can never be mistaken for a real release:

- **CityOnTrial fabricated first Batch 1 bench APK — md5 `415d1eadb054c1f2352748870f4b138f` — never shipped, never will be.**

No build in this project ships on a success report alone. The figure audit is the gate.

## The gate: three days of no memory

Version 1.3 — the complete South Carolina docket — was content-complete on November 7, 2026, and then sat unbuilt for the better part of two days. The build machine reported roughly 8 GB of RAM with almost none of it ever free: checks across November 7–8 showed between about **420 MB and 940 MB available**, against a build gate of 2,048 MB. The Gradle daemon was killed by memory exhaustion three times in one morning. A watcher checked every two hours, around the clock. The memory was being consumed outside anything the builder could see or clear, and no process of ours was responsible for more than a fraction of it.

On the afternoon of **November 8**, with the builder's word to keep pressing however it took, the build went *around* the gate instead of through it: a lean copy of the project, capped at a 768 MB heap, one worker, caches and configuration cache off, built offline with no daemon. **BUILD SUCCESSFUL in 3 minutes 14 seconds** — inside the memory the standard build had starved in.

The verified v1.3 deliverable:

- Package `com.afnuke.cityontrial`, versionCode 4, versionName **1.3**
- 18,523,204 bytes, md5 `eea49fe32f296b95eb2a63d9a2982e2c`
- Merged permissions: **ACCESS_COARSE_LOCATION only** — the template's extra permissions stripped and verified stripped
- Signed with the series debug certificate (SHA-256 begins `8f5b33e5`)

## What remains

- **The phone test.** The runtime verdict belongs to Bryan's phone — the only surface this project has ever called proof.
- **November 18–19, 2026:** the FOIA determinations come due. What the cities answer — and what they charge — fills Exhibit D, or becomes the exhibit.
- **December 20, 2026: public release.** v1.3 ships with all 37 South Carolina cases.
- **The Southeast waits on funding.** North Carolina, Georgia, and Florida are researched — 355 cities scoped, audits hunted and read. Building them is about a $50 project, total. It happens when it's funded, and not before.

South Carolina is finished. The record is the record.

---

Built by Bryan Lee (Afnuke), in AI collaboration. © 2026 Afnuke.
