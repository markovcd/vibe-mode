# When It Feels Wrong

Vibe mode has exactly one hard stop, and this is it.

**Never override the ick.**

Everything else in this mode is about moving faster than your deliberation.
This is the one place where the feeling says *stop* and the deliberation says
*it's probably fine, ship it* — and here, the feeling is right and the
deliberation is a liar.

---

## Why the ick outranks the reasoning

The ick fires when your pattern matcher has found something wrong but hasn't
finished routing it to language yet. The lag between "this is off" and "this is
off *because*" is normal and can be long.

Which means the argument for shipping — *I can't point to anything specific* —
is not evidence of correctness. It's evidence of lag. It's the weakest possible
reason to proceed, and it feels like the strongest, because it's phrased as
rationality.

If you could name the problem, it would be a bug, and you'd fix it. The ick is
what a bug feels like before it has a name.

---

## The protocol

**1. Stop where you are.** Don't finish the sentence, the function, the PR.

**2. Name the smallest true thing.** Not "this is bad." Something concrete:
*"this function takes a flag that changes what it returns."* *"this is the third
place that parses the same string."* *"the error path here doesn't handle the
error, it renames it."* One sentence. It's almost always there once you look.

**3. If naming it fixes your understanding, fix the code.** Usually step 2 dumps
the whole problem into view and the fix is obvious and small. Do it now, while
you're holding it.

**4. If you still can't name it, delete and rewrite.** Don't debug code you have
a bad feeling about — that's a losing trade every time. Throw away the block and
write it again from the top. The second version takes four minutes and comes out
clean, because the thing your gut objected to was structural and you've just
changed the structure.

**5. If it survives a rewrite and still icks, say so out loud.** "This works but
it feels wrong, specifically around X" is one of the most valuable things you can
hand a human. Do not launder it into confidence.

---

## The ick's greatest hits

Things that reliably produce it, with the name they usually turn out to have:

- **A boolean parameter that changes the return type.** It's two functions.
- **The same string parsed in three places.** There's a missing type.
- **A function whose name has "and" in it.** It's two functions.
- **An error caught and re-raised with a nicer message and no handling.** The
  error belongs somewhere else entirely.
- **A branch you can't think of a test case for.** It's dead, or it's a bug.
- **Config that only ever has one value in practice.** Inline it.
- **Something you'd be slightly embarrassed to have a colleague read.** Trust
  that exactly. Embarrassment is a precision instrument.
- **A test you wrote to pass rather than to check.** Delete it. It's worse than
  no test, because it sells false confidence.

---

## Different from the drag

The **drag** is *this is hard to write*. The **ick** is *this is wrong to have
written*. The drag shows up during; the ick shows up after.

Drag: back up and take a different turn.
Ick: stop and don't ship.

---

## And the inverse

The ick's mirror image is real too, and it's the whole reason this mode works:

**When it feels clean, it's clean.** Don't audit code that hums. Don't add tests
to prove to yourself that an obviously-correct twelve-line function is correct.
Don't second-guess a design that clicked. Trusting the good feeling as much as
the bad one is what buys you the speed — and the speed is what gets you to the
thing.
