---
name: handoff-audit
description: Use at the START of any conversation that inherits context from a previous one (a handoff note, a session log, a project notebook, a status doc, somebody else's plan), and at the END when writing one. Turns inherited claims into checked ones, and writes handoffs the next conversation can audit. Invoke when a conversation opens with "read this and carry on", "pick up where we left off", "continue from last time", or before acting on any number, constraint, status or tooling choice that came from a previous conversation.
---

# Handoff audit: read inherited context as claims, write it so it can be checked

Every new conversation starts knowing nothing, so it reads what the last one wrote. The problem is
that a note written by a previous conversation **arrives wearing the costume of an established fact**.
It sits in a notebook or a status doc in the same confident voice as things that were actually
verified, and nothing strips that costume off. So it gets built on, repeated to other people, and only
questioned when somebody happens to get suspicious.

**You should never be the detection mechanism for your own tools.**

## The one distinction that makes this workable

- **A decision YOU made carries forward and is binding.** Do not re-open it. Re-litigating settled
  calls wastes your time in the opposite direction.
- **A claim, number, recommendation or constraint written by a previous conversation is a
  HYPOTHESIS.** It carries forward as something to re-check, never as a fact.

Handoffs and notebooks are written by the assistant, so most of what is in one is the assistant's. If
you cannot tell which it is, treat it as the assistant's and check it.

---

## Part A: opening a conversation that inherits context

### A1. Read once for orientation, then re-read as a list of claims

First pass: understand the shape of the work. Second pass: for each substantive statement ask **"who
produced this, and did anyone verify it?"** Anything that cannot be traced to a decision the person
made, or to a named file, document or command output, is unverified.

### A2. Pull out only the claims that are load-bearing today

Do not audit the whole document. Audit what this conversation will **act on or repeat**. For each one
write: *their call* · *verified, and here is the evidence* · *unverified*.

### A3. Re-check these five categories before building on them

| Category | What to do |
|---|---|
| **A number**, especially one about to be said to somebody else | Trace it to the thing that produced it, and name that thing in the same breath |
| **A tool or approach** carried from a previous handoff | Re-derive it from the shape of today's task. Do not inherit it |
| **A constraint** ("we only get four slides", "the limit is two", "that tool cannot do X") | Find and quote the sentence that states it. **If you cannot find that sentence, treat the constraint as unverified rather than real**, and if the work depends on it, go to whoever set it and ask before designing around it |
| **A claim that something exists and works** ("it is wired up", "we sent that", "it is live") | Go and look. Installed is not running. Drafted is not sent. Written is not deployed |
| **A status** ("done", "blocked", "three of five") | Check the live source, not the note about it |

### A4. Spend the checking where the damage would be

Not every claim earns a trace. Prioritise anything going in front of someone else, anything that gates
a decision, and anything expensive to reverse. A stale note about where a file lives costs a minute. A
wrong number in front of a customer costs credibility.

### A5. Say what you re-checked and what you did not

One line, early: what was verified, what is being taken on trust, and why. That is the line that stops
the person having to be the one who catches it. **If a carried claim turns out to be wrong, say so
plainly and say how long it survived.**

---

## Part B: writing a handoff, a notebook entry or a status doc

**B1. Open by telling the reader it is a list of claims,** not a briefing. The next conversation's
default is to treat it as settled; say explicitly that it is not.

**B2. Label where every substantive item came from.** *Their call*, binding. *Verified*, with the file
or the command that proved it. *My judgement*, a hypothesis. Priority orderings are almost always the
third one.

**B3. Never write "do not re-check this."** That sentence promotes a guess to a fact with no evidence,
and it is the exact mechanism this exists to break. Write instead: *"the evidence is in this file;
spot-check two or three before building on them."*

**B4. Say why a recommendation changed, not just what it is.** A bare instruction gets copied forward
forever. A recommendation with its reasoning can be argued with, which is the point.

**B5. Carry open questions as questions.** Do not quietly resolve something the person never answered.
If a decision is owed, mark it owed and name who owes it.

---

## The self-check that catches the pattern

Before finishing a handoff: **would this document let the next conversation repeat a mistake, because
it states a conclusion without the evidence?**

And when auditing: **am I applying the same scepticism to my own inherited notes that I would apply to
somebody else's document?** This exists because it is very easy to run a careful audit on everyone
else's claims and none on your own handoff.

## When a person's claim contradicts the evidence, suspect the WORD before the person

Both sides are often right about different things, and the disagreement is one word meaning two
things. Someone says a component is "built and working"; the code says it is never called. It can turn
out that their word named the whole service, which genuinely was live, while the same word also names
one piece inside it, which was never invoked. Nobody was wrong and nobody was lying.

So before telling anyone their claim is false: **write down what each side means by the contested
word.** If the meanings differ you have your answer and nobody has to be wrong. Then go to the running
system rather than the files, and report it as a collision rather than a correction.
