ASSET LOG

####### <!-- ANCHOR MARKER - ADD ALL NEW ASSET ENTRIES DIRECTLY BELOW THIS LINE -->

## ASSET:redwolf 2026-10-22 -> Claude skill plan: LinkedIn fetch via macnimi server + GitHub Action

**Plan:** Replace step 1a fetch() — which LinkedIn blocks unauthenticated — with a weekly
GitHub Action that calls a macnimi server running Puppeteer, caches results as TREE-<SLUG>
files in CAN/, and Claude reads those files during step 1a.

**Architecture (Option B — scheduled cache):**
  GitHub Action (cron — weekly, before batch day)
    → calls macnimi server: GET /linkedin?slug=<slug> for each connection
        → macnimi runs Puppeteer with authenticated LinkedIn session
            → returns JSON { recentPosts[], bio, followerCount }
    → Action commits CAN/TREE-<SLUG>-2026Q3.json to repo

  Claude (step 1a)
    → reads CAN/TREE-<SLUG>-2026Q3.json (same pattern as CAN/TREE-2026Q3.json)
    → extracts recent posts/announcements per connection
    → informs 1b subtype selection

**Cache files (CAN/, per connection):**
  TREE-REDWOLF-2026Q3.json
  TREE-NZSA-2026Q3.json
  TREE-ASIS-2026Q3.json
  TREE-NZPOLICE-2026Q3.json
  TREE-JOHNSON-2026Q3.json
  TREE-GALLAGHER-2026Q3.json
  TREE-INNERRANGE-2026Q3.json
  TREE-BOSCH-2026Q3.json
  TREE-ICT-2026Q3.json
  TREE-JACQUES-2026Q3.json

**To build:**
  1. macnimi server endpoint — Node.js + Puppeteer
     GET /linkedin?slug=<slug> → JSON { recentPosts[], bio, followerCount }
     Must be publicly reachable by GitHub Actions (Cloudflare tunnel or similar)
  2. GitHub Action — .github/workflows/fetch-linkedin.yml
     Cron schedule, loops all slugs from TREE-2026Q3.json connections{},
     commits each TREE-<SLUG>-2026Q3.json result to CAN/
  3. Claude skill — .claude/skills/fetch-linkedin/SKILL.md
     Instructs agent to read CAN/TREE-*-2026Q3.json files in step 1a
  4. README update — step 1a references the skill and TREE-<SLUG> files

**Risk:** LinkedIn ToS prohibits scraping; run conservatively (one fetch per
connection per week, human-like delays) to reduce detection risk.

**Status:** PLANNED — not yet built.

## ASSET:redwolf 2026-10-22 16:20 -> Week 43 media generated for fresh batch (commit 64f00b7)

**Why:** 64f00b7 replaced all six week 43 posts again; five media URLs pointed to placeholders that did not exist (404). Media now lives in COULD/media/2026Q3/ after the folder rename (6c99c42). None of the 20 Oct week 43 graphics fit the new posts; removed (still in git history): post-007-survey-diagnostic, post-008-nzsa-departing-staff, post-009-nzsa-membership, post-011-gov-case-study-carousel (+ slides 1–5), post-012-protect-the-experience, post-010-PLACEHOLDER.md.

**Media (all png, 1080x1350):**
- post-007 IQP Inspections — compliance schedule → IQP inspection → Form 12A → Building WOF, access-controlled doors as SS 3/2: https://raw.githubusercontent.com/jayreck996/md-redwolf/main/COULD/media/2026Q3/post-007-iqp-inspections.png
- post-008 AI in Surveillance — traditional CCTV vs AI analytics split, plus "what it doesn't do": https://raw.githubusercontent.com/jayreck996/md-redwolf/main/COULD/media/2026Q3/post-008-cctv-vs-ai.png
- post-009 Expert Opinion — detect / delay / respond layers with examples; delay must outlast response: https://raw.githubusercontent.com/jayreck996/md-redwolf/main/COULD/media/2026Q3/post-009-detect-delay-respond.png
- post-010 Career Growth — technician → senior technician → team lead → lead consultant; training, NZSA qualifications, mentoring: https://raw.githubusercontent.com/jayreck996/md-redwolf/main/COULD/media/2026Q3/post-010-career-pathway.png
- post-011 NZSA Accreditation — member vs accredited, plus tender question: https://raw.githubusercontent.com/jayreck996/md-redwolf/main/COULD/media/2026Q3/post-011-nzsa-accreditation-tender.png
- post-012 Security Awareness Month — tailgating, propped doors, unmonitored visitors, outdated credentials, each with a fix; comment CTA: https://raw.githubusercontent.com/jayreck996/md-redwolf/main/COULD/media/2026Q3/post-012-awareness-month-fixes.png

**Sources checked:** building.govt.nz (IQP, Form 12A, annual BWOF; most specified systems inspected at least yearly); council SS 3/2 access controlled doors forms; security.org.nz accreditation process and membership requirements.

**Verify before publishing:**
- post-007: copy says Red Wolf "is registered to carry out IQP inspections across Wellington and Auckland" — confirm IQP registration with each council. Official term is "independent qualified person" (copy says "Independently Qualified Person").
- post-011: COPY FIX — "annual self-audit assessed by independent auditors" is the membership requirement; accreditation is an independent onsite audit against NZSA Codes of Practice (5-year term, annual declaration). VERIFY "Red Wolf has held NZSA accreditation since our founding".
- post-010: verify "several of our senior consultants and team leads started as installation technicians" and the NZSA qualifications claim. Graphic shows a generic pathway, no names or timeframes.
- post-008: copy says Red Wolf installs AI analytics for mid-market clients — confirm.
- post-009: "20 years in the industry" — still unverified.

**Note:** week 41 media (post-013 to post-018) remains in COULD/media/2026Q3/ unreferenced.

## ASSET:redwolf 2026-10-20 17:30 -> Week 43 media generated for fresh subtopics (commit 5b9220f)

**Why:** 5b9220f replaced all six week 43 posts with new subtopics and reset media URLs to placeholders (five did not exist). None of the previous week 43 graphics fit; they were removed (still in git history): post-007-noc-alarm-timeline, post-008-ai-analytics, post-009-five-gaps, post-011-late-night-response, post-012-security-awareness-month.

**Media (SHOULD/media/2026Q3/, 1080x1350):**
- post-007 Protective Security Surveys — 3-stage diagram (site assessment, gap analysis, recommendations) + compliance vs diagnostic: https://raw.githubusercontent.com/jayreck996/md-redwolf/main/SHOULD/media/2026Q3/post-007-survey-diagnostic.png
- post-008 NZ Security Industry Standards — NZSA position statement on confidential information and departing staff: employer and departing-staff obligations, access to revoke at final working time: https://raw.githubusercontent.com/jayreck996/md-redwolf/main/SHOULD/media/2026Q3/post-008-nzsa-departing-staff.png
- post-009 NZSA Membership — trust signals card + questions to ask: https://raw.githubusercontent.com/jayreck996/md-redwolf/main/SHOULD/media/2026Q3/post-009-nzsa-membership.png
- post-011 Government & Critical Infrastructure — 5-slide carousel PDF (challenge, scope/stage/deliver, result, CTA): https://raw.githubusercontent.com/jayreck996/md-redwolf/main/SHOULD/media/2026Q3/post-011-gov-case-study-carousel.pdf (+ post-011-slide-1..5.png)
- post-012 Industry News Commentary — "Security should protect the experience, not just the assets" with friction vs enabler: https://raw.githubusercontent.com/jayreck996/md-redwolf/main/SHOULD/media/2026Q3/post-012-protect-the-experience.png
- post-010 Company Culture — media-type jpg, needs a real team photo. Placeholder updated.

**Sources checked:** NZSA position statement "Confidential Information and Departing Staff" (security.org.nz/wp-content/uploads/2026/10/NZSA_Professional-Standard.pdf) — advisory "expected professional standard", not binding. NZSA membership requirements (security.org.nz, why choose an NZSA member).

**Verify before publishing:**
- post-012: the quote attributed to "NZSA Board Member Mark Knoff-Thomas" at the "Profit Protection Future Forum" could not be found online; his public role found is Newmarket Business Association. The graphic deliberately does NOT name him or present a direct quote. Confirm the quote, his title and the event (link a source) before using it in the copy.
- post-011: this presents a real government project. Confirm the facts (full access control + CCTV upgrade, staged, live operations) and get client approval; government/critical infrastructure clients often restrict publicity. Graphic names no agency or building.
- post-008: copy says NZSA "released guidance on staff transitions" — accurate; it is a position statement (advisory), not a regulation.
- post-009: copy matches NZSA membership requirements. Confirm Red Wolf is a member.
- post-010: verify culture claims; get consent for any photo.

## ASSET:redwolf 2026-10-20 17:05 -> Week 43 media re-evaluated after batch regeneration (commit 9173fbf)

**Relinked:** 9173fbf reset week 43 media URLs to PLACEHOLDER.md files; only post-010's exists, the other five returned 404. All six now point to real files.

**Kept (copy reworded, same substance):**
- post-007 https://raw.githubusercontent.com/jayreck996/md-redwolf/main/SHOULD/media/2026Q3/post-007-noc-alarm-timeline.png — 5-step alarm-to-resolution timeline still matches.
- post-008 https://raw.githubusercontent.com/jayreck996/md-redwolf/main/SHOULD/media/2026Q3/post-008-ai-analytics.png — "AI detection capabilities" infographic still matches.
- post-011 https://raw.githubusercontent.com/jayreck996/md-redwolf/main/SHOULD/media/2026Q3/post-011-late-night-response.png — incident timeline still matches.

**Updated:** post-009 https://raw.githubusercontent.com/jayreck996/md-redwolf/main/SHOULD/media/2026Q3/post-009-five-gaps.png — headline now "The 5 security gaps we see most in Wellington businesses" to match the new title; same five gaps and fixes. Removed post-009-five-mistakes.png.

**Replaced:** post-012 is now Campaigns & Seasonal / Security Awareness Month (was Hot Take). New graphic https://raw.githubusercontent.com/jayreck996/md-redwolf/main/SHOULD/media/2026Q3/post-012-security-awareness-month.png — "Don't forget the physical side": propped doors, visitor books no one checks, access never reviewed after staff departures. Removed post-012-hot-take.png.

**Still BLOCKED:** post-010 — media-type now jpg; needs a real staff/team photo and technician quotes with consent. Verify "over six years" average tenure.

**Verify:** post-011 title now says "A Client's Account" — the post presents a client's first-hand account, so written client approval is required (graphic carries no client quote). post-009 "20+ years" and post-007 "Wellington and Auckland" still unverified.

**Note:** week 41 rows were dropped in 05d2801; post-013 to post-018 media files remain in SHOULD/media/2026Q3/ unreferenced.

## ASSET:redwolf 2026-10-13 23:10 -> Week 41 media re-evaluated after batch regeneration (commit f552bd3)

**Relinked:** f552bd3 reset all six week 41 media URLs to non-existent placeholders (404). All six relinked.

**Unchanged (content identical to d2ad2a5):** post-013, post-015, post-016, post-017, post-018 — existing graphics kept.

**Replaced:** post-014 is now Cybersecurity Convergence (was Physical Security Threats). New graphic https://raw.githubusercontent.com/jayreck996/md-redwolf/main/SHOULD/media/2026Q3/post-014-cyber-physical.png — IT/physical Venn with the overlap (building automation, access control, IP cameras, intercoms), three attack vectors from the copy (outdated building automation, phished credentials, physical entry to network breach) and a four-point unified approach. Removed post-014-physical-threats.png.

**Verify:** post-014 copy calls the convergence gap "the fastest-growing risk for NZ organisations" — unsourced; soften or cite. Open items for post-016 and post-017 from the 23:00 entry still apply.

## ASSET:redwolf 2026-10-13 23:00 -> Week 41 media updated for LinkedIn-research rewrite (commit 50491bb)

**Media URLs unchanged** (same filenames, all 18 table links return 200). Files updated in place:
- post-013 access-control.png — capabilities now match copy: real-time door monitoring, tailgating alerts, audit trail, instant lockdown (replaced time-based permissions and CCTV-linked events). No Gallagher branding on the graphic.
- post-014 physical-threats.png — tag changed to "Cybersecurity Awareness Month".
- post-016 industry-involvement.png — four items: NZSA working groups, position statements, technician training, industry events and awards (NZSA awards).
- post-017 nzsa-accreditation.png — added note that members and accredited members are expected to uphold NZSA professional standards (codes of conduct, position statements incl. confidential information and departing staff, Sept 2026).
- post-018 did-you-know.png — assumptions 4 and 5 now match copy: visitor management stops at the front desk; no security audit since the last fit-out.
- post-015 unchanged.

**Source checked:** security.org.nz/position-statements — "Prof Standards: Confidential Info & Departing Staff - Sept 2026" exists.

**Still open:** post-017 copy still attributes the membership requirements (annual self-audit reviewed by independent auditors) to accreditation; "current licences across every technician" is not stated by NZSA for accreditation. post-016: verify Red Wolf's actual working-group, position-statement and awards involvement. post-018: verify "two decades in the field".

## ASSET:redwolf 2026-10-13 22:45 -> Week 41 media regenerated for redone batch (commit d41340c)

**Why:** d41340c replaced all six week 41 posts (new subtopics, titles, descriptions, media briefs) and reset media URLs to non-existent placeholders. None of the previous week 41 graphics fit; all six replaced and the old files removed (still in git history).

**Media (SHOULD/media/2026Q3/, 1080x1350, built to each row's media brief):**
- post-013 access control: credential types, door zones, 4 capabilities — https://raw.githubusercontent.com/jayreck996/md-redwolf/main/SHOULD/media/2026Q3/post-013-access-control.png
- post-014 physical threats: tailgating, credential sharing, insider risk, social engineering, each with a control — https://raw.githubusercontent.com/jayreck996/md-redwolf/main/SHOULD/media/2026Q3/post-014-physical-threats.png
- post-015 pre-consultation checklist (6 items) + 3 questions to ask — https://raw.githubusercontent.com/jayreck996/md-redwolf/main/SHOULD/media/2026Q3/post-015-briefing-checklist.png
- post-016 industry involvement: industry groups, technician training, industry events — https://raw.githubusercontent.com/jayreck996/md-redwolf/main/SHOULD/media/2026Q3/post-016-industry-involvement.png
- post-017 NZSA member vs accredited comparison — https://raw.githubusercontent.com/jayreck996/md-redwolf/main/SHOULD/media/2026Q3/post-017-nzsa-accreditation.png
- post-018 Did You Know: 5 assumptions, "usually false" — https://raw.githubusercontent.com/jayreck996/md-redwolf/main/SHOULD/media/2026Q3/post-018-did-you-know.png

**Source checked:** security.org.nz accreditation process — accreditation is an independent onsite audit against NZSA Codes of Practice, 5-year term, annual declaration of no material change; re-audit on material change. Membership (separate) = vetting incl. licence, min $1m liability cover, annual self-audit reviewed by independent auditors, Code of Ethical Conduct.

**Status / verify:**
- post-013 READY. Confirm the credential types and CCTV integration match systems Red Wolf actually installs.
- post-014 READY.
- post-015 READY.
- post-016 READY as a typographic card. VERIFY Red Wolf's actual involvement (NZSA working groups, training, events) — the graphic states it in general terms. Real event or training photos would be stronger.
- post-017 READY. COPY FIX: the description says accreditation requires "an annual self-audit reviewed by independent auditors" — that is the membership requirement. Accreditation is an independent onsite audit, 5-year term, annual declaration. "current licences across every technician" is not stated on the accreditation page. VERIFY Red Wolf is NZSA accredited (not only a member) before posting.
- post-018 READY. Overlaps post-009 (week 43: untested systems, CCTV angles) — consider spacing them apart. Copy says "two decades in the field"; verify.

## ASSET:redwolf 2026-10-13 22:20 -> Week 41 media re-evaluated after persona re-angle (commit 754ccf9)

**Relinked:** commit 754ccf9 reset all week 41 media URLs to PLACEHOLDER.md files that do not exist (404). All six now point to real media again.

**Kept (content unchanged):** post-013 https://raw.githubusercontent.com/jayreck996/md-redwolf/main/SHOULD/media/2026Q3/post-013-security-survey.png · post-015 https://raw.githubusercontent.com/jayreck996/md-redwolf/main/SHOULD/media/2026Q3/post-015-nzsa-membership.png · post-017 https://raw.githubusercontent.com/jayreck996/md-redwolf/main/SHOULD/media/2026Q3/post-017-quality-process.png (media text says "ISO 9001" but the graphic carries no ISO badge; certification still unverified).

**Updated:** post-014 https://raw.githubusercontent.com/jayreck996/md-redwolf/main/SHOULD/media/2026Q3/post-014-psr-framework.png — headline "The PSR framework in practice", checklist relabelled "Have this ready before any audit, tender or review". Earlier copy issues (critical infrastructure mandate, "what has been updated") are resolved by the new description.

**Replaced:**
- post-016 https://raw.githubusercontent.com/jayreck996/md-redwolf/main/SHOULD/media/2026Q3/post-016-project-delivery.png — values card no longer fit the new angle; new graphic shows four client commitments (one point of contact, milestones up front, proactive updates, formal close-out). Removed post-016-red-wolf-values.png.
- post-018 https://raw.githubusercontent.com/jayreck996/md-redwolf/main/SHOULD/media/2026Q3/post-018-year-end-decisions.png — three decisions: IT/physical convergence, IQP paperwork for access-controlled doors (specified system SS 3/2, building WOF), footage retention policy (Privacy Act, principle 9). Removed post-018-three-trends.png.

**Sources checked:** building.govt.nz (IQP inspection, Form 12A, annual BWoF); council SS 3/2 access controlled doors forms; privacy.org.nz principle 9 (retention).

**Verify:** post-016 commitments must match how Red Wolf actually runs projects. post-018 copy says AI cameras create "new liability" — keep it framed as a privacy obligation, not legal advice.

## ASSET:redwolf 2026-10-13 21:55 -> Week 41 media generated (post-013 to post-018)

**Media (SHOULD/media/2026Q3/, same brand system, 1080x1350):**
- post-013 survey 3-stage diagram: https://raw.githubusercontent.com/jayreck996/md-redwolf/main/SHOULD/media/2026Q3/post-013-security-survey.png
- post-014 PSR framework checklist: https://raw.githubusercontent.com/jayreck996/md-redwolf/main/SHOULD/media/2026Q3/post-014-psr-framework.png
- post-015 NZSA trust signals card: https://raw.githubusercontent.com/jayreck996/md-redwolf/main/SHOULD/media/2026Q3/post-015-nzsa-membership.png
- post-016 RED WOLF values card: https://raw.githubusercontent.com/jayreck996/md-redwolf/main/SHOULD/media/2026Q3/post-016-red-wolf-values.png
- post-017 quality process explainer: https://raw.githubusercontent.com/jayreck996/md-redwolf/main/SHOULD/media/2026Q3/post-017-quality-process.png
- post-018 three trends commentary: https://raw.githubusercontent.com/jayreck996/md-redwolf/main/SHOULD/media/2026Q3/post-018-three-trends.png

**Sources checked:** PSR via ncsc.govt.nz (4 areas: governance, personnel, information, physical; mandatory for public service agencies; annual self-assessment against 20 mandatory requirements). NZSA via security.org.nz (vetting incl. licence check; min $1m public and product liability; annual self-audit reviewed by independent auditors; Code of Ethical Conduct; complaints and disciplinary procedure).

**Status:**
- post-013 READY. Generic survey process; confirm it matches how Red Wolf runs surveys.
- post-014 READY. Copy fix: description says PSR sets obligations for "critical infrastructure providers" — the Cabinet mandate covers public service agencies (plus NZDF, Police, NZSIS, PCO), not private critical infrastructure. Also "what has been updated" — no 2026 PSR update found; remove or cite one.
- post-015 READY. Graphic does not claim Red Wolf is a member. Copy fix: "not self-certification ... independently verified" overstates it — the annual audit is a self-audit reviewed by independent auditors. Verify Red Wolf's NZSA membership before posting.
- post-016 READY as branded values card (no photo). Values from COULD/README.TXT.
- post-017 READY. No ISO badge or certification claim on the graphic. VERIFY Red Wolf holds ISO 9001 before posting — the post copy states it and it remains unverified.
- post-018 READY. Trends are Red Wolf's commentary, not cited data.

**Table:** media and media URL updated for post-013 to post-018 (placeholders were never created; links were 404 before this).

## ASSET:redwolf 2026-10-13 -> Week 41 content batch generated (post-013 to post-018)

**Posts added to SHOULD/TABLE-2026Q3.csv:**

| Item | Category | Type | Subtopic | Value | Score | Status |
|------|----------|------|----------|-------|-------|--------|
| post-013 | SERVICES | Consulting & Design | Protective Security Surveys | Ownership | 7 | BLOCKED: needs survey process diagram |
| post-014 | INDUSTRY | Regulation & Compliance | NZ Security Industry Standards | Learn | 8 | BLOCKED: needs PSR checklist graphic |
| post-015 | AUTHORITY | Accreditations & Partnerships | NZSA Membership | Excellence | 8 | BLOCKED: needs NZSA trust signals card |
| post-016 | PEOPLE | Culture & Values | Company Culture | We Before Me | 7 | BLOCKED: needs team culture photo or values card |
| post-017 | TRUST | Compliance & Certifications | ISO 9001 | Reliable | 8 | BLOCKED: needs ISO 9001 explainer card |
| post-018 | ENGAGEMENT | Community & Reposts | Industry News Commentary | Future Focused | 7 | BLOCKED: needs 3-trend commentary graphic |

**Persona alignment:** All posts written to the Security Manager persona (MUST/README.TXT) — compliance, quality, reliability, and process themes throughout.

**Tags used:** @Red Wolf High Level Security Ltd on all posts. @New Zealand Security Association on post-014, 015, 018.

**Verify before publishing:**
- post-014: confirm PSR framework details are current for 2026
- post-015: confirm NZSA membership is active and licence details are accurate
- post-017: confirm ISO 9001 certification is current before publishing

## ASSET:redwolf 2026-10-13 -> Structural updates: feedback-comment column, tree feedback counts, week number correction

**CSV — SHOULD/TABLE-2026Q3.csv:**
- Added `feedback-comment` column (last column, after `feedback`)
- Week numbers corrected to ISO week: batch 1 (post-001–006) 27 → 42 (Oct 12–18), batch 2 (post-007–012) 28 → 43 (Oct 19–25)

**Tree — MUST/TREE-2026Q3.json:**
- Added `"feedback": {"win": N, "tie": 0, "lost": N, "comments": []}` to all 54 subtypes
- Seeded with week 42 actuals: CCTV win:1, Emerging Risks lost:1, Team Certifications win:1, Polls win:1

**Workflow — .github/workflows/update-feedback.yml:**
- Now writes `feedback-comment` to CSV and appends comment to tree subtype `comments[]` on each dispatch

**Status:** READY — no media impact, structural only.

## ASSET:redwolf 2026-10-13 18:22 -> Week 28 adjustment check: media unchanged

**Change since media was generated:** post-008 partner tags changed from Bosch to Gallagher Security + Integrated Control Technology (commit 7f25753). No other week 28 content changed.

**Media impact:** none. post-008-ai-analytics.png carries no partner names or logos, so it stays valid. The earlier "confirm the Bosch tag" note is superseded.

**Verify:** post-008 is about AI video analytics. Per MUST/README.TXT rule 5, confirm Gallagher and ICT are directly relevant (e.g. video analytics integrated with their access control platforms), otherwise tag only Red Wolf.

## ASSET:redwolf 2026-10-13 18:05 -> Week 28 media generated (post-007, 008, 009, 011, 012)

**Media (SHOULD/media/2026Q3/, same brand system as week 27, 1080x1350):**
- post-007 alarm-to-resolution timeline: https://raw.githubusercontent.com/jayreck996/md-redwolf/main/SHOULD/media/2026Q3/post-007-noc-alarm-timeline.png
- post-008 AI detection event types: https://raw.githubusercontent.com/jayreck996/md-redwolf/main/SHOULD/media/2026Q3/post-008-ai-analytics.png
- post-009 five mistakes tip card: https://raw.githubusercontent.com/jayreck996/md-redwolf/main/SHOULD/media/2026Q3/post-009-five-mistakes.png
- post-011 late-night incident timeline: https://raw.githubusercontent.com/jayreck996/md-redwolf/main/SHOULD/media/2026Q3/post-011-late-night-response.png
- post-012 hot take opinion graphic: https://raw.githubusercontent.com/jayreck996/md-redwolf/main/SHOULD/media/2026Q3/post-012-hot-take.png

**Status:**
- post-007 READY as a graphic instead of a NOC photo. No response times or site counts on the graphic; verify "hundreds of sites" and "Wellington and Auckland" in post copy.
- post-008 READY. No Bosch branding on the graphic; confirm the Bosch tag fits the partnership.
- post-009 READY. Mistakes 4 and 5 (untested systems, unmanaged contractor access) added to complete the five. Verify "20+ years" in post copy.
- post-010 BLOCKED: needs staff photo and real technician quotes with consent; verify "6+ years" average tenure. Placeholder file added so its link no longer 404s.
- post-011 READY as an incident timeline, deliberately without a client quote. Add a real quote only with the client's written approval; confirm the 11pm CBD incident details.
- post-012 READY. Opinion only, no figures.

**Table:** media and media URL updated for post-007/008/009/011/012.

## ASSET:redwolf 2026-10-13 -> Week 28 content batch generated (post-007 to post-012)

**Branch:** `main`

**Posts added to SHOULD/TABLE-2026Q3.csv:**

| Item | Category | Type | Subtopic | Score | Status |
|------|----------|------|----------|-------|--------|
| post-007 | SERVICES | Monitoring & Response | Network Operations Centre | 7 | BLOCKED: needs NOC photo |
| post-008 | INDUSTRY | Technology Trends | AI in Surveillance | 8 | BLOCKED: needs AI detection infographic |
| post-009 | AUTHORITY | Thought Leadership | Expert Opinion | 8 | BLOCKED: needs 5-point tip card graphic |
| post-010 | PEOPLE | Team Spotlight | Staff Profiles | 7 | BLOCKED: needs staff/team photo |
| post-011 | TRUST | Testimonials & Social Proof | Client Quotes | 8 | BLOCKED: needs client quote graphic; verify client approval for story |
| post-012 | ENGAGEMENT | Interactive | Questions & Debates | 7 | BLOCKED: needs branded opinion graphic |

**Subtypes deliberately varied from week 27** (no repeat of CCTV, Emerging Risks, Awards, Behind the Scenes, Case Study/Commercial, Polls).

**Verify before publishing:**
- post-008: confirm Bosch tag is appropriate (check partnership scope)
- post-009: "20+ years" — Red Wolf founded 2005, so 21 years in 2026; adjust copy if needed
- post-011: client story must be anonymised or have written approval before posting

## ASSET:redwolf 2026-10-13 -> Research branch: LinkedIn connections, score, week column

**Branch:** `research`

**Changes:**
- `MUST/TREE-2026Q3.json` — added `connections` block: own (Red Wolf), associations (NZSA, ASIS International, NZ Police), partners (Johnson Controls, Gallagher Security, Inner Range ANZ, Bosch, ICT, Jacques Technologies)
- `SHOULD/TABLE-2026Q3.csv` — added `score` column (1–10, content priority) and `week` column (first column, batch key); all 6 posts set to week 27; pattern: 6 posts per week, one per category

**Score logic:** post-003 AUTHORITY/Awards=10 (strongest observed post type), post-005 TRUST/Case Study=9, post-002/004 INDUSTRY+PEOPLE=8, post-001/006 SERVICES+ENGAGEMENT=7

## ASSET:redwolf 2026-10-13 14:16 -> Q3 media generated, audited, repo cleaned up

**Brand:** Real logo (`logo.jpg`) and its colours: red `#EF1925`, shield grey `#C8C9CB`, ink `#211F20`. Font Inter. Canvas 1080x1350 portrait.

**Media (SHOULD/media/2026Q3/, all links public, HTTP 200):**
- post-002 drone threat infographic: https://raw.githubusercontent.com/jayreck996/md-redwolf/main/SHOULD/media/2026Q3/post-002-drone-threats.png
- post-005 case study carousel, 5-slide PDF: https://raw.githubusercontent.com/jayreck996/md-redwolf/main/SHOULD/media/2026Q3/post-005-case-study-carousel.pdf (downloads; preview at https://github.com/jayreck996/md-redwolf/blob/main/SHOULD/media/2026Q3/post-005-case-study-carousel.pdf)
- post-005 slides: https://raw.githubusercontent.com/jayreck996/md-redwolf/main/SHOULD/media/2026Q3/post-005-slide-1.png … post-005-slide-5.png
- post-006 poll teaser: https://raw.githubusercontent.com/jayreck996/md-redwolf/main/SHOULD/media/2026Q3/post-006-poll.png

**Table:** `media URL` in SHOULD/TABLE-2026Q3.csv points to the files above for post-002/005/006. post-001/003/004 still point to PLACEHOLDER.md.

**Status:**
- post-002 READY. Verify: jamming or bringing down a drone is illegal for private businesses in NZ.
- post-005 READY. Verify slide 2 wording against client facts; client approval needed.
- post-006 READY as teaser only (LinkedIn native polls can't carry an image). Options A–D fit the 30-char limit. Verify "We ask this every year" in post copy.
- post-001 BLOCKED: needs approved, anonymised before/after install photos.
- post-003 BLOCKED: needs award-night photo; verify NZSA award details and names.
- post-004 BLOCKED: needs install footage/photos with staff consent.

**Unverified, kept off all media:** redwolf.net.nz, ISO 9001, NZSA accreditation, Auckland office.

**Open question:** whether Johnson Controls brand/approval rules apply (Red Wolf recruitment runs via Johnson Controls).

**Posting:** LinkedIn doesn't attach media by URL; download and upload each file when creating the post.

**Repo cleanup:** Removed earlier SVG drafts (COULD/media/), the old scaffold (lowercase could/ must/ should/ would/, root ASSET/ISSUE 2026Q3 + 2026Q4 logs, README.md). ts-web still targets could/ and may recreate it until repointed.

## ASSET:redwolf 2026-10-13 -> Repo concept: LinkedIn post content generator for Red Wolf High Level Security Ltd

**Purpose:** This repo is dedicated to LinkedIn post content generation for Red Wolf High Level Security Ltd.

**LinkedIn:** https://www.linkedin.com/company/red-wolf-high-level-security-ltd/home/

**Scope:** All content, assets, tables, trees, and logs in this repo serve as structured source material for drafting, scheduling, and publishing LinkedIn posts on behalf of the Red Wolf brand.
