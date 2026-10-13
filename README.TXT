RED WOLF — LinkedIn Content Orchestration Plan
Last updated: 2026-10-13

Client:   Red Wolf High Level Security Ltd
Platform: LinkedIn
Purpose:  Structured weekly content generation, review, and publishing

============================================================
REPO STRUCTURE
============================================================
  MUST/   — what the content must follow (strategy, rules)
  SHOULD/ — what the content should contain (posts, media)
  COULD/  — what the content could reference (assets, values)
  WOULD/  — what has happened (activity log)

============================================================
ORCHESTRATION — HOW TO RUN A CONTENT BATCH
============================================================

STEP 0 — LEARN
  When client submits feedback, GitHub Actions writes win/tie/lost
  and any comment back to the CSV automatically.
  Before generating the next batch, read TABLE-2026Q3.csv —
  check feedback per post to inform subtype selection and content angle.

STEP 1 — RESEARCH
  Read MUST/README.TXT        content generation rules
  Read MUST/TREE-2026Q3.json  pillars, subtypes, connections
  Read COULD/README.TXT       brand values, asset rules
  Research LinkedIn pages for any connections to be tagged
  (verify slugs before use — see MUST/README.TXT rule 5)

STEP 2 — GENERATE
  Open SHOULD/TABLE-2026Q3.csv
  Add 6 new rows — one per pillar — for the next week number
  For each post assign:
    topic     — one of the 6 pillars
    type      — from the pillar's type list in the tree
    subtopic  — from the type's subtype list (no repeats in quarter)
    score     — using the scoring logic in MUST/README.TXT
    tags      — @Red Wolf always; partners only if directly relevant
  Set all new posts to BLOCKED status until media is ready

STEP 3 — MEDIA
  Generate or source media for each post
  Save to SHOULD/media/<quarter>/
  Update media and media URL columns in the CSV
  Log each asset in COULD/ASSET-2026Q3.md with status and verify notes

STEP 4 — REVIEW
  Client reviews posts via the index site (GitHub Pages)
  Client submits Win / Tie / Lost feedback per post
  Feedback is written back to the CSV via GitHub Actions

STEP 5 — PUBLISH
  Download media files locally (LinkedIn does not accept URLs)
  Copy post title, description, tags, and hashtags from the CSV
  Upload to LinkedIn manually or via scheduling tool
  Update WOULD/LOG-2026Q3.md with publish date and outcome

============================================================
KEY FILES
============================================================
  MUST/TREE-2026Q3.json       content strategy skeleton
  MUST/README.TXT             rules for content generation
  SHOULD/TABLE-2026Q3.csv     all posts, all weeks
  SHOULD/media/2026Q3/        post media files
  COULD/ASSET-2026Q3.md       asset log (status, verify notes)
  COULD/README.TXT            brand values + asset rules
  WOULD/LOG-2026Q3.md         activity log

============================================================
QUARTER ROLLOVER
============================================================
  At the start of a new quarter:
  - Create MUST/TREE-<year><Q>.json   (copy + update meta)
  - Create SHOULD/TABLE-<year><Q>.csv (new header, empty rows)
  - Create COULD/ASSET-<year><Q>.md   (fresh log)
  - Create WOULD/LOG-<year><Q>.md     (fresh log)
  - Update this file: client, quarter, key files section
============================================================
