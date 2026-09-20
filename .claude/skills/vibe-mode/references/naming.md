# Naming by Feel

Naming is the fastest design feedback available. You can feel a bad name in
under a second, and a bad name is almost always a bad design wearing a disguise.
So name first, name fast, and let the name do the thinking.

---

## Name before you understand

Don't wait until you've figured out what the thing is to name it. Name it at
first contact. The name you reach for is your model of the thing, compressed —
and once it's written down you can look at it, which is far easier than looking
at a model in your head.

Then the name pulls the design along behind it. `retryWithBackoff` will not let
you put logging logic inside it. `RequestManager` will let you put *anything*
inside it, which is exactly the problem.

---

## The mouth test

Say it in your head. If it comes out easily, it's probably right. If you stumble,
or catch yourself mentally adding "you know, the thing that...", the design is
unclear, not the name.

This works because fluent naming requires a single coherent concept, and a single
coherent concept is what you were trying to design in the first place. The mouth
is checking your architecture for free.

---

## Suffixes that mean you don't know yet

Manager, Helper, Util, Handler, Service, Processor, Wrapper, Info, Data, Object,
Base.

Each one means: *there's a pile of stuff here and I haven't found what it is.*
They're not banned. They're a flag that you skipped the design step. When you
catch yourself typing one, ask what the pile actually is. Usually it's two things
that want to be apart, or one thing that already has a name in the domain.

---

## Rules of thumb that survive contact

- **Length tracks scope.** A three-line loop variable is `i`. A module-level
  export earns four words. Long names in tiny scopes are noise; short names in
  huge scopes are cruelty.
- **"and" in a name means two functions.** Every time. No exceptions worth
  remembering.
- **Booleans read as assertions.** `isReady`, `hasChildren`, `shouldRetry`. If
  the name doesn't read as a claim that is true or false, it isn't a boolean.
- **Negatives compound badly.** `notDisabled` will end up inverted inside a
  conditional within the week. Name the positive.
- **Steal the domain's words.** If the people who use this call it an *invoice*,
  it's an `Invoice`, not a `BillingRecord`. Invented vocabulary costs everyone
  who reads it, forever.
- **Symmetric operations get symmetric names.** open/close, push/pop,
  encode/decode. If you have `start` and `terminate`, one of them is lying about
  what it does.
- **Rename the moment it stops fitting.** A name that was right three commits ago
  and is wrong now is actively misleading, which is worse than vague. Renaming is
  cheap. Reading a lie every day is not.

---

## When you're stuck on a name

Being stuck is the signal, not the obstacle. Three moves:

1. **Describe it in one plain sentence.** The name is a noun or a verb in that
   sentence. It's nearly always sitting right there.
2. **If the sentence needs an "and", split the thing.** The name is unfindable
   because there are two things.
3. **If you can only describe it by how it's used, it isn't a thing yet.** It's a
   step in someone else's function. Inline it and move on.

Never settle for a name you don't like and resolve to fix it later. You won't,
and in three weeks it will be in forty places.
