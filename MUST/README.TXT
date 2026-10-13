MUST — Tree Document Guide
Last updated: 2026-10-13

============================================================
WHAT THIS IS
============================================================
TREE-2026Q3.json is the content strategy skeleton for Red Wolf
LinkedIn posts. It defines the categories, types, and subtypes
that all posts in TABLE-2026Q3.csv must map to.

============================================================
STRUCTURE
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
CONTENT GENERATION RULES
============================================================
1. One post per pillar per week — 6 posts per batch.
2. Do not repeat the same subtype within the same quarter.
3. Scores: AUTHORITY/Awards=10, TRUST/Case Study=9,
   INDUSTRY/PEOPLE=8, SERVICES/ENGAGEMENT=7.
   Adjust by subtype quality (e.g. Thought Leadership=8,
   Testimonials=8, Staff Profiles=7).
4. Research all connection LinkedIn pages before generating
   content that tags or references them.
5. Only tag partners when the post is directly relevant to
   their product or domain.
6. All new posts go into TABLE-2026Q3.csv with status BLOCKED
   until media and any required approvals are in place.

============================================================
EXTENDING THE TREE
============================================================
- New subtypes can be added to any existing type.
- New types require a new entry under the relevant category.
- New categories require a new pillar entry and a justification
  for why it fits the Red Wolf brand strategy.
- Connection slugs must be verified on LinkedIn before adding.
============================================================
