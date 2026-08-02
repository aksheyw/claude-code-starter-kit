# How to undo everything

Knowing the way out is what makes you willing to try things. Read this once now, before you need it.

Nothing in the day-one setup is hard to reverse. Almost all of it is deleting a file, and you can ask Claude to do the deleting while you watch.

## Stop it mid-task

Press **Esc**. It stops where it is and keeps whatever it had already finished. Nothing closes and nothing is lost.

If the app itself stops responding, quit it the normal Mac way, `Cmd` `Q`, and open it again. Your files are untouched.

## Go back to how things were

Type `/rewind`, or press **Esc** twice with nothing typed in the box. It lists the prompts you sent this session and offers to put the code back, the conversation back, or both.

**Rewind has holes, and they are the dangerous ones.** Know them before you rely on it:

- It restores files it edited **itself**. It does **not** restore files changed by commands it ran, so anything deleted, moved or copied sits outside it.
- It does not cover work done by a second session it started on its own.
- It is undo for **this session only**. Close the conversation and it is gone.

That last one is why version control matters, and the first time you have work you would hate to lose is the moment to add it. See [GROWTH.md](../GROWTH.md).

This is the short version. Rule `05-how-to-stop-it-and-get-back` in your rules folder is the fuller one, and it is the file to trust if the two ever disagree.

---

# Removing what this kit installed

The three sections below are deliberately separate, and they get progressively less reversible. Do not run the later ones to achieve the earlier ones.

## 1. Remove this kit, and nothing else

This is almost certainly the one you want. It takes out exactly what the setup put in and leaves everything else alone.

Say this to Claude:

> Delete only these files, and show me each one before you do it. In `~/.claude/rules/`: the eighteen files listed below. In `~/.claude/commands/`: `learn.md`. In this project: `CLAUDE.md`, and the `.claude/wiki/` folder. Do not delete anything else in `~/.claude/`.

The eighteen rule files, by exact name, so nothing else goes with them:

```
01-start-in-the-right-folder.md      20-agree-the-shape-first.md
02-talk-to-me-in-plain-words.md      21-write-so-it-lands.md
03-write-the-project-instructions.md 22-saving-is-not-publishing.md
04-stop-before-anything-expensive.md 23-before-anyone-else-uses-it.md
05-how-to-stop-it-and-get-back.md    30-agree-the-approach-before-any-code.md
06-make-it-prove-it.md               31-ask-for-a-test-that-fails-first.md
07-never-guess-never-undersell.md    32-code-that-stays-easy-to-change.md
08-get-it-out-of-the-chat.md         33-delegate-the-reading-keep-the-judgement.md
09-every-correction-becomes-a-rule.md 34-pressure-test-the-expensive-decisions.md
```

**Why the list rather than "delete everything in the rules folder".** That folder is shared. Anything you write yourself later, or install from anywhere else, lives there too. A blanket delete takes those with it and you will not notice until something stops behaving the way you taught it.

To remove **one** rule rather than all eighteen, delete just that file by name.

Then ask Claude to list `~/.claude/rules/` and `~/.claude/commands/` so you can see what is left.

## 2. Remove a plugin or a connection

**A plugin:** click the **+** button next to the prompt box, choose **Plugins**, and remove it there. Same place you installed it.

**A connection:** type `/mcp`, pick the one you want, and disconnect. That removes Claude's access. It changes nothing inside the tool itself.

## 3. Remove Claude Code entirely

**Read this before running it.** `~/.claude/` is not just this kit. It holds every plugin you have installed, your permission settings, your conversation history, anything Claude has remembered, and any rules or commands you wrote yourself. `~/.claude.json` holds account and connection state.

Deleting them is not "uninstalling the starter kit". It is resetting Claude Code to the day you installed it, and nothing here restores it afterwards.

If that is genuinely what you want, and only then, this is the command. It is the one place in this guide that needs a terminal, because Finder hides these folders:

```bash
rm -rf ~/.claude ~/.claude.json
```

Your own projects and files are untouched, because they live in your own folders.

To also remove the app itself, drag Claude from Applications to the Bin, the same as any Mac app.

---

## The one thing that is genuinely not reversible

**A password or key that reaches a published repository.** Rewriting history afterwards is possible, but it does not help: automated scanners find published keys within minutes, and once a value has been copied you cannot un-copy it.

There is no undo. The fix is to cancel that key with whoever issued it and generate a new one.

This is why [GROWTH.md](../GROWTH.md) puts the secret-scan step before the publishing step, and why the ignore file has to exist before the first upload rather than after it.
