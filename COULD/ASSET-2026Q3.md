ASSET LOG
INSTRUCTION FOR AI MODEL:
ALWAYS ADD NEW ASSET ENTRIES AT THE TOP, DIRECTLY BELOW THIS HEADER.
NEVER DELETE OR EDIT PREVIOUS ASSET ENTRIES.

####### <!-- ANCHOR MARKER - ADD ALL NEW ASSET ENTRIES DIRECTLY BELOW THIS LINE -->

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
