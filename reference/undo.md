# How to undo everything

Knowing the way out is what makes you willing to try things. Read this once now, before you need it.

Nothing in the day-one setup is hard to reverse. Almost all of it is deleting a file.

## Stop Claude mid-task

Press `Esc`. It stops where it is and keeps whatever it had already finished. Nothing closes and nothing is lost.

If the whole thing is unresponsive, `Ctrl` and `C` together quits Claude Code. Your files are untouched. Start it again with `claude`.

## Go back to how things were

Type `/rewind`, or press `Esc` twice with nothing typed in the box. It lists the prompts you sent this session and offers to put the code back, the conversation back, or both.

**Rewind has holes, and they are the dangerous ones.** Know them before you rely on it:

- It restores files it edited **itself**. It does **not** restore files changed by commands it ran, so anything deleted, moved or copied sits outside it.
- It does not cover work done by a second session it started on its own.
- It is undo for **this session only**. Close the conversation and it is gone.

That last one is why version control matters, and the first time you have work you would hate to lose is the moment to add it. See [GROWTH.md](../GROWTH.md).

This is the short version. Rule `05-how-to-stop-it-and-get-back` in your rules folder is the fuller one, and it is the file to trust if the two ever disagree.

## Remove the rules

```bash
rm ~/.claude/rules/*.md
```

Then check, because this is exactly the kind of command that looks like it worked when it did not:

```bash
ls ~/.claude/rules/
```

That should print nothing. If it still lists files, they are still loading into every conversation.

To remove one rule rather than all of them, delete it by its full name:

```bash
rm ~/.claude/rules/07-write-so-it-lands.md
```

Nothing else depends on that folder. Emptying it returns Claude Code to how it behaves out of the box.

## Remove the /learn command

```bash
rm ~/.claude/commands/learn.md
```

## Remove a plugin

Inside Claude Code:

```
/plugin uninstall <name>@<marketplace>
```

Or to keep it installed but switch it off:

```
/plugin disable <name>@<marketplace>
```

Then `/reload-plugins`. Use `claude plugin list` to see the exact names.

## Disconnect a connector

Inside Claude Code, `/mcp`, then choose the one you want and disconnect it. That removes Claude's access. It does not change anything in the tool itself.

## Remove the project notebook

It is two files inside your own project:

```bash
rm -rf .claude/wiki/
```

Also delete the block you added to your `CLAUDE.md` telling Claude to read them, otherwise it will look for files that are no longer there.

## Remove Claude Code entirely

```bash
rm -rf ~/.claude ~/.claude.json
```

That removes the rules, commands, plugins, and its memory of your setup. Your projects and your own files are untouched, because they live in your own folders.

To also remove the program itself, use whichever method you installed it with.

## The one thing that is genuinely not reversible

**A password or key that reaches published history.** Once something is pushed to a shared code host, deleting it in a later change does not remove it from the history, and automated scanners find published keys within minutes.

There is no undo. The fix is to cancel that key with whoever issued it and generate a new one.

This is why [GROWTH.md](../GROWTH.md) puts the secret-scan step before the publishing step, and why the ignore file has to exist before the first upload rather than after it.
