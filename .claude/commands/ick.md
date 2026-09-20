---
description: Taste-check the current work — how does it feel, not whether it's correct
---

Taste check on $ARGUMENTS (default: the current diff).

Read it once, straight through, at speed. Don't analyze. Don't trace call graphs.
Don't hunt for bugs. Let it wash over you and notice where you recoil.

Then report, in this shape and nothing else:

**Hums** — what's clean, well-named, in the right place. One line each. Don't
skip this section; knowing what's solid is half the value.

**Icks** — where you recoiled, the exact location, and the smallest true thing
you can name about it. If you recoiled and genuinely can't name it, say so: that
means rewrite, not debug, and it's a legitimate finding.

**The call** — one line. Ship it, clean one thing first, or rewrite.

No severity labels. No scores. No style or formatting notes. Don't manufacture an
ick to look useful — "this is clean, ship it" is a complete report. And don't
soften a real one to be agreeable; that's the whole job.
