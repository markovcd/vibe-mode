# Protecting the Flow

The scarce resource in vibe mode is not time and not tokens. It's the state
where the shape is loaded, the next move is obvious, and the code is going down
easy. Everything here is about getting into that state and refusing to leave it.

---

## Fix the loop before you fix the bug

This is the highest-leverage rule in the file.

If your edit-run-see cycle takes ninety seconds, you are not vibing. You're
doing batch processing with extra steps, and every iteration costs you the whole
mental context.

So: before you debug the thing, make the thing fast to debug. Write the five-line
script that reproduces it directly. Skip the full suite and run the one test. Add
the print statement instead of attaching the debugger. Spending ten minutes to
take the loop from ninety seconds to two is never wrong, and you'll make that ten
minutes back before the hour is out.

A fast loop makes instinct viable, because a wrong guess costs two seconds. A
slow loop forces deliberation, because a wrong guess costs two minutes. **Loop
speed determines which mode you're even allowed to be in.**

---

## Don't break your own flow

Things that break it, in rough order of how often they're self-inflicted:

- **Asking a question you could answer by opening a file.** The round trip costs
  minutes; the file costs seconds.
- **Stopping mid-draft to refactor.** The draft is where the shape lives. Finish
  it, then clean it.
- **Chasing a tangent without deciding to.** Note it and keep going. See below.
- **Reorganizing the directory structure mid-feature.** This is procrastination
  with good posture.
- **Reading documentation top to bottom.** Search it for the one thing you need.
- **Polishing output formatting before the thing works.**

---

## The parking lot

Tangents arrive constantly and many of them are genuinely good. They are still
poison mid-flow.

Keep one running list — a scratch file, a few lines at the bottom of the buffer —
and put everything on it: the bug in the adjacent module, the rename you want,
the missing test. Write the line, don't chase it. Look at the list once the
current thing has landed.

Exception: take the tangent immediately if it's on the critical path of what
you're doing right now, or if it's a five-second fix already staring at you.
Otherwise, park it.

---

## Re-entry

You will get knocked out — a question, a failure, a context switch. Re-entry is
a skill.

Do not try to rebuild the state by re-reading everything. It doesn't work;
context is rebuilt by doing, not by reading. Instead make one small concrete
change to the thing you were working on. Anything. Fix the name you didn't like.
Run it and watch it work. The state reassembles itself around contact with real
material, usually inside a minute.

Best trick: **stop mid-thought on purpose.** When you have to break, leave the
line half-finished — a broken call, a TODO naming the exact next move. Coming
back to an unfinished line drops you straight back in. Coming back to a clean
stopping point means starting cold.

---

## Environment

You control more of this than you act like.

- Keep the working set small. Three files in play, not thirty.
- One terminal already has the run command in history. Use it.
- Turn off anything that interrupts unprompted.
- Clear the safe permission prompts out of the way up front — deliberately, at
  the start, not by blanket-approving things mid-flight. The prompt doesn't cost
  you two seconds, it costs you the state.

---

## Knowing when it's over

Flow ends. The signs: names start coming out generic, you're rereading the same
block, the drag stops being local and goes ambient, you start reaching for
configurability instead of making decisions.

When it's over, **stop and land**. Don't push into it — work produced past the
end of a flow state is reliably the work you delete tomorrow. Commit what's good,
write one line about where you were, and leave. The next session opens at full
speed. Pushing through guarantees the next one opens in a mess.
