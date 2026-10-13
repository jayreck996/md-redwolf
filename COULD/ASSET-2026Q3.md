ASSET LOG

####### <!-- ANCHOR MARKER - ADD ALL NEW ASSET ENTRIES DIRECTLY BELOW THIS LINE -->

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
