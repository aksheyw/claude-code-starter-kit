<!--
Add the block below to your project's CLAUDE.md, at the bottom.

It is what makes the notebook actually get read. Creating the files is not enough:
without these lines nothing tells Claude Code to open them, and they quietly rot.
-->

## Start of every conversation

Read `.claude/wiki/_hot.md` first, then the most recent entry in `.claude/wiki/_log.md`.
Then tell me in three bullets where things stand and what you think today's first task is,
before doing anything else.

## End of every working session

When I say **"save and sync"**, do this:

1. Update `.claude/wiki/_hot.md` so it matches reality now. Move anything no longer current out of it.
2. Add one entry to the top of `.claude/wiki/_log.md`: what changed, what we learned that was not obvious, and where to pick up.
3. Show me both diffs before writing them, so I can correct anything wrong.
4. Tell me anything worth recording that you were not sure about, rather than deciding alone.
