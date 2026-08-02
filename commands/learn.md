---
description: Capture a correction as a durable lesson, file it in the right place, and check whether it should graduate into a standing rule.
argument-hint: "[the lesson, or leave blank to infer it from the conversation]"
---

The user is banking a lesson. Do the whole thing in one shot. They should never have to
know which file it goes in, or open one afterwards.

## 1. Work out what the lesson is

- If `$ARGUMENTS` is non-empty, that is the lesson. Use it.
- If it is empty, infer it from the recent conversation: the last correction, the version
  they approved against the one they rejected, a preference they stated in passing, or a
  fact of theirs that changed. State in one line what you extracted, then keep going. Only
  stop to ask if it is genuinely ambiguous between two different lessons.

## 2. Apply the bar

Capture durable, repeatable patterns and real changes of fact. Skip one-off typos, a phrase
used once, and anything that only applies to today's task. If it does not clear the bar, say
so in one line and stop. A folder of noise is worse than a folder of four good lessons.

## 3. File it

- Look for `lessons/` in the current project. If it does not exist, create it along with
  `lessons/index.md`.
- Pick the matching category file. Start with these four and create a new one only when
  nothing fits: `working-with-claude.md`, `writing.md`, `product-and-decisions.md`,
  `apps-and-code.md`.
- Append the lesson using exactly this template:

```markdown
## YYYY-MM-DD - Short description

**What I did:** the wrong thing, in one sentence
**What you wanted:** the right thing, in one sentence
**Rule:** Never [X]. Always [Y].
**Seen in:** <project name>
```

- Add one line to `lessons/index.md` under the matching heading: the date, the short
  description, and the rule in under fifteen words. The index is what gets read at the start
  of every session, so it has to stay scannable.

## 4. Check for graduation

Search the existing lessons, in this project and in `~/.claude/rules/`, for the same root
cause. Do not match on wording, match on what actually went wrong.

- **Second time in the same project:** tighten the existing lesson rather than adding a
  near-duplicate. Say what you tightened.
- **Second time in a different project:** it has earned promotion. Draft it as a standing
  rule in the house style (one plain sentence stating the rule, then why it exists, then how
  to apply it, under 250 words, no em dashes) and show the draft. Write it to
  `~/.claude/rules/` only after the user says yes, because that file loads into every session
  everywhere and it is theirs to approve.
- **Names a version of a tool or model:** add a review date about six months out and one
  line saying what makes it obsolete.

## 5. Report

Two lines, no more. The lesson in one sentence, then exactly which files changed. If you
promoted something, say what it now applies to.

## Fire this without the command

Run this same flow, without waiting to be asked for it by name, whenever the user says
things like: remember this, learn from that, note this, do not do that again, bank this, or
from now on I want X. Decide the placement yourself and report it afterwards. Only pause if
a fact you would be writing down is unverified, or if the change would meaningfully alter
how they are represented.
