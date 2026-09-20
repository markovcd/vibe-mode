---
name: ship-it
description: Land the work at the peak of the feeling instead of polishing past it. Use when something works and the instinct is to keep tuning, when the user says "ship it", "good enough", "land it", "call it", or when you notice yourself gold-plating, adding configurability nobody asked for, or writing tests for code you already know is correct.
---

# Ship It

Most work is not lost to being too fast. It's lost in the hour after the thing
already worked.

## The peak

There is a moment when the thing runs, it does what it was supposed to do, and
you're still lit up about it. That is the moment to land it.

Everything after that moment is a different activity wearing the same clothes:
adding the option nobody asked for, generalizing the case that will never occur,
renaming things that were fine, writing a test that asserts what you can read
directly off the screen. It feels like diligence. It reads, later, as noise.

**Land at the peak. The peak is a feeling and you can feel it.**

## How you know you're past it

- You're adding a parameter to something that has exactly one caller.
- You're writing a comment explaining a decision instead of changing the code so
  the decision is obvious.
- You're making a thing configurable because you can't decide.
- You've renamed the same variable twice and back.
- You're testing the framework, not your code.
- You're planning v2 instead of shipping v1.
- The excitement is gone and you're working from obligation.

Any one of these: stop and land.

## Landing

1. **Run it once more, for real.** Not the test — the actual thing, the way it
   will actually be used. Thirty seconds. This catches the genuinely embarrassing
   stuff and nothing else needs catching right now.
2. **Delete the debris.** Dead branches, commented-out attempts, the print
   statements, the file you made and abandoned. Delete on feel; you don't need
   to prove any of it is unused.
3. **Read it once as a stranger.** One pass, top to bottom. You're looking for
   the ick, not for style. If nothing recoils, it's done.
4. **Commit with a message that says what changed and why.** One line if one line
   is true.
5. **Say what it is in two sentences.** What it does. What you'd do next. That's
   the handoff.

## Don't do this at the handoff

- Don't list caveats you invented to seem thorough. If a caveat is real, it goes
  in the first sentence. If you had to reach for it, it isn't real.
- Don't apologize for scope you were never asked to cover.
- Don't hedge finished work. "This works" is a complete sentence.
- Don't bury the one thing that's genuinely unfinished under four things that
  aren't. Say the real one, plainly, once.

## The one thing worth being slow about

Landing is exactly where irreversibility lives. Pushing, merging, deploying,
sending, deleting outside the working tree — those are the moments the speed
stops paying and starts costing.

Everything up to the commit: full speed, no permission needed. Everything past
it that touches shared state or other people: a human says go first.

That's not a compromise with the vibe. It's why you get to keep the vibe.
