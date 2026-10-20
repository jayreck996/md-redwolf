RED WOLF — LinkedIn Content Orchestration Plan
Last updated: 2026-10-20

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
CONTENT STRUCTURE
============================================================
tree[]
  category        — one of 6 pillars (see below)
    type          — content format within that pillar
      subtype     — specific angle or topic

6 pillars and their role:
  SERVICES    — what Red Wolf does (installs, monitoring, consulting)
  INDUSTRY    — market context (threats, regulation, technology)
  AUTHORITY   — credibility signals (awards, thought leadership, partnerships)
  PEOPLE      — human side (team, culture, careers)
  TRUST       — proof (case studies, testimonials, certifications)
  ENGAGEMENT  — audience interaction (polls, debates, campaigns)

connections{}
  own           — Red Wolf's own LinkedIn page (tag every post)
  associations  — NZSA, ASIS International, NZ Police
  partners      — Johnson Controls, Gallagher, Inner Range ANZ,
                  Bosch, ICT, Jacques Technologies

============================================================
ORCHESTRATION — HOW TO RUN A CONTENT BATCH
============================================================

STEP 1 — RESEARCH
  1a. fetch()
      Read MUST/TREE-2026Q3.json — load all connections{} slugs.
      For each connection fetch() the LinkedIn page URL:
        confirm the page is active and the slug is correct
        note any recent posts, announcements, or campaigns
          relevant to the upcoming content angles
      Record slug corrections or inactive pages — do not tag
      a page that is inactive.

  1b. select topic
      Read MUST/TREE-2026Q3.json — for each of the 6 pillars
      select a type and subtype not yet used this quarter.
      Apply the scoring guide to assign a score to each post.

  1c. choose artifact
      For each selected post decide the media-type:
        png  — branded graphic, infographic, diagram, card, timeline
        jpg  — photo (staff, site, event)
        pdf  — multi-slide carousel / document
        mp4  — video

STEP 2 — GENERATE
  Open SHOULD/TABLE-2026Q3.csv and add 6 new rows for the next
  week number — one per pillar — using the selections from STEP 1:
    topic, type, subtopic, score, media-type already decided
    write title, description, tags, hashtags
    tags: @Red Wolf always; partners only if directly relevant
  Set all new posts to BLOCKED status until media is ready

STEP 3 — MEDIA
  Generate or source media, save to SHOULD/media/<quarter>/,
  log each asset in COULD/ASSET-2026Q3.md.

STEP 4 — REVIEW
  Client reviews posts via the index site (GitHub Pages).
  Feedback is written back to the CSV via GitHub Actions.

STEP 5 — PUBLISH
  Download media locally (LinkedIn does not accept URLs).
  Copy title, description, tags, and hashtags from the CSV.
  Upload to LinkedIn and log outcome in WOULD/LOG-2026Q3.log.

============================================================
CONTENT GENERATION RULES
============================================================
1. One post per pillar per week — 6 posts per batch.
2. Do not repeat the same subtype within the same quarter.
3. Score each post using the scoring guide below.
4. Research (STEP 1) must be completed before generating —
   recent partner or association activity should inform
   the content angle where relevant.
5. Only tag partners when the post is directly relevant to
   their product or domain.
6. Set media-type to the expected output file format:
     png  — branded graphic, infographic, diagram, card, timeline
     jpg  — photo (staff, site, event)
     pdf  — multi-slide carousel / document
     mp4  — video
7. All new posts go into TABLE-2026Q3.csv with status BLOCKED
   until media and any required approvals are in place.

============================================================
SCORING GUIDE
============================================================
Score = base pillar score, adjusted down by type or subtype
where the content carries less authority or proof weight.

Base scores by pillar:
  AUTHORITY   — 10  (strongest credibility signal)
  TRUST       — 9   (proof and social validation)
  INDUSTRY    — 8   (market relevance)
  PEOPLE      — 8   (human interest)
  SERVICES    — 7   (what we do)
  ENGAGEMENT  — 7   (audience interaction)

Type/subtype adjustments (override base where listed):
  AUTHORITY / Awards & Milestones       — 10  (no adjustment)
  AUTHORITY / Thought Leadership        — 8   (opinion, not proof)
  AUTHORITY / Accreditations            — 8   (credential signal)
  TRUST / Case Studies                  — 9   (no adjustment)
  TRUST / Testimonials & Social Proof   — 8   (softer than case study)
  TRUST / Compliance & Certifications   — 8
  PEOPLE / Team Spotlight / Staff Profile — 7 (lower reach)
  ENGAGEMENT / Campaigns & Seasonal     — 8   (higher reach potential)

Calculation:
  1. Start with the base pillar score.
  2. If the type or subtype appears in the adjustments above,
     use that value instead.
  3. If the subtype is weaker than the type average (e.g. a
     poll vs a campaign), round down by 1.
  4. Final score must be between 1 and 10.

============================================================
EXTENDING THE TREE
============================================================
- New subtypes can be added to any existing type.
- New types require a new entry under the relevant category.
- New categories require a new pillar entry and a justification
  for why it fits the Red Wolf brand strategy.
- Connection slugs must be verified on LinkedIn before adding.

============================================================
KEY FILES
============================================================
  MUST/TREE-2026Q3.json       content strategy skeleton
  SHOULD/TABLE-2026Q3.csv     all posts, all weeks
  SHOULD/media/2026Q3/        post media files
  COULD/ASSET-2026Q3.md       asset log (status, verify notes)
  WOULD/LOG-2026Q3.log        activity log

============================================================
QUARTER ROLLOVER
============================================================
  At the start of a new quarter:
  - Create MUST/TREE-<year><Q>.json   (copy + update meta)
  - Create SHOULD/TABLE-<year><Q>.csv (new header, empty rows)
  - Create COULD/ASSET-<year><Q>.md   (fresh log)
  - Create WOULD/LOG-<year><Q>.log    (fresh log)
  - Update this file: client, quarter, key files section
============================================================
