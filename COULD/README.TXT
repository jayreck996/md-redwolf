SHOULD — Table Document Guide
Last updated: 2026-10-13

============================================================
WHAT THIS IS
============================================================
TABLE-2026Q3.csv is the working content table for Red Wolf
LinkedIn posts. Each row is one post. All posts must map to a
subtype in CAN/TREE-2026Q3.json.

============================================================
COLUMNS
============================================================
week              ISO week number the post is scheduled for
topic             One of the 6 pillars from the tree
type              Content format within that pillar
subtopic          Specific angle — must exist in tree, no repeats
                  within the same quarter
item              Post ID — post-001, post-002, etc. Sequential,
                  never reused
title             LinkedIn post headline
description       Full LinkedIn post copy
media             Description of the media asset to produce
media-type        Expected file format: png / jpg / pdf / mp4
                  (AI chooses during generation — see CAN/README.TXT rule 6)
media URL         Public URL to the file in COULD/media/<quarter>/
                  Set to PLACEHOLDER.md until media is generated
linkedin account tag  LinkedIn pages to tag — @Red Wolf always;
                  partners only when directly relevant (rule 5)
hashtag           5 hashtags — topic-specific + brand
score             Content priority 1–10 (see CAN/README.TXT rule 3)
createdat         Date row was created (YYYY-MM-DD)
updatedat         Date row was last updated (YYYY-MM-DD)
feedback          Client response: win / tie / lost / empty
                  Written back automatically by GitHub Actions
feedback-comment  Optional client note alongside the feedback result
                  Written back automatically by GitHub Actions

============================================================
STATUS VALUES (in description or media field)
============================================================
BLOCKED   — media not ready or approval pending; do not publish
READY     — media confirmed, approved for publishing

============================================================
MEDIA FILES
============================================================
Stored in COULD/media/<quarter>/ (e.g. COULD/media/2026Q3/).
Naming: <item>-<slug>.ext  e.g. post-001-cctv-upgrade.png
Log every file in MAY/ASSET-2026Q3.md with status and verify notes.
============================================================
