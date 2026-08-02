# Ask for a test that fails first

*Trigger: something you will rely on more than once.*

For anything you will rely on, ask for an automated check, and ask to see it fail before the fix and pass after it.

**Why this exists.** Walking the thing yourself is the best evidence there is, and it stops the moment you stop watching. A check that runs on its own keeps working after you have moved on. But one written after the fix and never seen to fail proves nothing, because it may be passing for the wrong reason.

**How to apply it.**

- The order is the whole point: write the check, watch it fail, make the fix, watch it pass. Ask to see both runs, not a summary of them.
- Every bug you hit gets one. Turn it into a failing check before it is fixed, and that bug can never come back quietly.
- No checks in the project at all? Do not backfill hundreds. Start with the one thing that would hurt most if it broke without a sound: taking money, letting someone in, losing data.
- Have them run before you publish (rule 22), and after anything that touched more than a couple of files.
- A check that passes on a broken app is worse than no check, because it is trusted. If one has never failed, ask to see it fail on purpose.
