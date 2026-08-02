# Before anyone else uses it

*Trigger: your first publish, or your first outside user.*

Scan the whole history for secrets, then walk a short list.

**Why this exists.** A key that reaches a shared history is exposed permanently: deleting the line later leaves the old version behind it.

**How to apply it.**

- Keys and passwords belong in `.env`, a file that never travels with the code, listed in `.gitignore`, the file naming what git keeps out of the history. Ask me to set up both and show you them.
- Before publishing, ask for exactly this: "search the entire version history, not just current files, for keys, passwords, tokens and any database address with a password in it, and show me every match."
- If anything turns up, change that key where it was issued: that alone makes the exposed copy useless. Scrubbing it from the history rewrites every past version, so treat that as its own careful job, not a rushed step before publishing.
- Private does not mean safe: one added collaborator can read the whole history.
- Then make me show the line that does each of these, on your server, not the browser. "I do not see a problem" is not an answer.
  - checks what a person types before it reaches a database instruction
  - checks who is asking and whether they are allowed, on every screen and request. Hiding a button is not access control.
  - caps how often one person can hit anything expensive
