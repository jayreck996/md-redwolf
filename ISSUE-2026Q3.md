ISSUE LOG
INSTRUCTION FOR AI MODEL:

ALWAYS ADD NEW ISSUE ENTRIES AT THE TOP, DIRECTLY BELOW THIS HEADER.

NEVER DELETE OR EDIT PREVIOUS ISSUE ENTRIES.

REQUIRED FORMAT FOR EACH ISSUE ENTRY:

## ISSUE:{NAME OF ENVIRONMENT} {YYYY-MM-DD HH:MM} → {CONTENT}

####### <!-- ANCHOR MARKER - ADD ALL NEW ISSUE ENTRIES DIRECTLY BELOW THIS LINE, NEVER DELETE OR EDIT PREVIOUS ISSUE ENTRIES-->
## ISSUE:ts-web 2026-07-05 08:58 → PENDING: (1) re-copy skill to mac-mini ~/.claude/commands/ts-web/ so format + header-steering fixes take effect on next run; (2) before Oct 1, verify the workflow's make_header template carries CUSTOM PROMPT/URLS into next-quarter files — ts-repo's template doesn't, sections may need re-adding quarterly.
## ISSUE:ts-web 2026-07-04 12:06 → PENDING mac-mini setup: (1) git clone https://github.com/jayreck996/ts-web.git next to ts-repo; (2) cp ts-web/.claude/commands/ts-web/could-update-md.md ~/.claude/commands/ts-web/; (3) pm2 start could-update-md.js --name ts-web (listener port 3457, endpoint /ts-web/could-update-md); env needed: MACMINI_TRIGGER_TOKEN + TSREPO_TOKEN; (4) gh secret set TSREPO_TOKEN --repo jayreck996/ts-web (masked paste, never on command line).
