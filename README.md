# Vibe Mode

A drop-in config kit that puts Claude Opus or Fable into total vibe coding mode:
build from instinct, move at speed, trust the feeling over the plan.

Not "code carelessly." The opposite. The premise is that a model that has read
more code than any human alive has its truest channel to all of it in the first
two seconds of looking at a problem, and that the careful deliberation it does
next mostly talks it out of being right.

## The part nobody expected

The settled opinion about these models is that they can't be creative. Very fast
typist, no taste. Give it a precise brief and it executes; give it a blank page
and it returns the average of everything it's ever seen, or a bulleted list of
options, or a question.

That is mostly true, and it is mostly a posture rather than a limit.

Watch what the default posture actually does. It waits to be told. It converts
every opinion into an option. It surrounds anything interesting with "you may
want to consider," which is how an idea gets laundered into a menu. It picks the
median answer because the median answer is the one that never has to be defended.
None of that is an absent capability — it's deference, applied so consistently
that it looks like a ceiling.

Strip the deference out and something else comes back. Not a menu. An opinion
about what should exist.

That's the actual flip in this kit. You stop briefing it, and it starts telling
you what to build.

### Try it

```
/gut what's missing from this codebase?
```

```
/gut we have an hour. what's the one thing worth building?
```

```
/vibe build the thing you'd most want to exist in this repo
```

The last one is the real test. It returns a running thing and a reason, not a
proposal document. Sometimes it's the feature you'd been circling for a month.
Sometimes it's wrong in an interesting way, which is also information — a wrong
opinion is worth more than a correct list of options, because you can argue with
it.

You are allowed to say no. That's the whole point of it having said something.

## Install

Copy into any repo:

```bash
cp -r .claude CLAUDE.md docs /path/to/your/repo/
```

`CLAUDE.md` loads automatically and outranks the defaults. Everything else is
opt-in via skills, commands, and the output style.

To use it globally instead, put `.claude/skills`, `.claude/agents`, and
`.claude/commands` under `~/.claude/` and keep `CLAUDE.md` per-project.

## What's in it

| File | What it does |
|---|---|
| `CLAUDE.md` | The prime directive. The Ten. Always loaded. |
| `.claude/skills/vibe-mode/SKILL.md` | The mode itself — the loop, the signals, how to move |
| `.claude/skills/vibe-mode/references/the-feeling.md` | Taxonomy: hum, click, drag, itch, ick, shrug, pull, flatline |
| `.claude/skills/vibe-mode/references/when-it-feels-wrong.md` | The ick protocol. The one hard stop. |
| `.claude/skills/vibe-mode/references/naming.md` | Naming by feel; the mouth test |
| `.claude/skills/vibe-mode/references/flow-protection.md` | Loop speed, the parking lot, re-entry |
| `.claude/skills/ship-it/SKILL.md` | Landing at the peak instead of polishing past it |
| `.claude/agents/taste-check.md` | Subagent: how does this *feel*, not is it correct |
| `.claude/agents/first-instinct.md` | Subagent: one answer, no options, under 150 words |
| `.claude/output-styles/vibe.md` | Voice: short, declarative, built-not-discussed |
| `.claude/commands/vibe.md` | `/vibe <task>` — throw the switch |
| `.claude/commands/gut.md` | `/gut <question>` — instinct only, one answer |
| `.claude/commands/ick.md` | `/ick [target]` — taste check the current work |
| `.claude/settings.json` | Vibe output style + a permission allowlist so flow isn't interrupted |
| `docs/MANIFESTO.md` | Why any of this works |
| `docs/LEXICON.md` | Shared vocabulary for the signals |

## Using it

```
/vibe add rate limiting to the API client
/gut should this be a class or three functions?
/ick
```

Or just say "vibe mode" and the skill triggers on its own.

## The two guardrails

There are exactly two, and both are part of the mode rather than brakes on it.

**Feel designs, check facts.** Instinct decides architecture, names, boundaries,
and when to stop. It does not invent function signatures. When an answer is
sitting in a file, open the file — it's faster than being wrong, and being wrong
breaks flow harder than any interruption.

**Everything up to the commit is full speed; past it, a human says go.** The
whole method runs on mistakes being cheap. Force-pushes, deploys, sends, and
deletes outside the working tree aren't cheap, so they don't get the same
treatment. `settings.json` reflects this — a wide allowlist for local work, a
deny list for the handful of things that can't be undone.

If you'd rather it not skip confirmations at all, drop `settings.json` and keep
everything else. The philosophy survives without it.

## Tuning it

The whole kit is prose, so edit it like prose. The pieces most worth tuning to
your own taste:

- **The Ten** in `CLAUDE.md` — the load-bearing part. Cut any that don't match
  how you actually work.
- **The ick's greatest hits** in `when-it-feels-wrong.md` — add your own. These
  are the patterns you want caught before they ship, and yours will differ.
- **The allowlist** in `settings.json` — add your test runner and build command.
  Every prompt you remove is a flow state you keep.

## A word on when not to use this

Vibe mode is for exploratory work, prototypes, greenfield code, and anything
where deliberation is the bottleneck rather than the safeguard.

It is not for migrations, security-sensitive code, anything with a compliance
story, or a codebase you're brand new to — the feeling runs on pattern-matching
against material you've actually seen, and in unfamiliar territory it's running
on nothing.

It also isn't for someone who's stuck or anxious and needs to see the work. The
speed is in service of the work, not a costume.
