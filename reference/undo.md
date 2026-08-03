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
- It belongs to **one conversation**, not to your project. Closing the conversation does not destroy it, and you can still rewind after coming back to it, but it is deleted along with the conversation after thirty days by default. That window is a setting, `cleanupPeriodDays`, so on a machine somebody else configured it may be shorter.

That last one is why version control matters, and the first time you have work you would hate to lose is the moment to add it. See [GROWTH.md](../GROWTH.md).

This is the short version. Rule `05-how-to-stop-it-and-get-back` in your rules folder is the fuller one, and it is the file to trust if the two ever disagree.

---

# Removing what this kit installed

The three sections below are deliberately separate, and they get progressively less reversible. Do not run the later ones to achieve the earlier ones.

## 1. Remove this kit, and nothing else

This is almost certainly the one you want. It takes the kit out of the way and leaves everything else alone.

**Nothing here is deleted outright.** Everything the kit installed is *moved* into one folder in your project called `starter-kit-undo-kept`, so you can look through it before you throw anything away. That matters more than it sounds: `CLAUDE.md` and the two notebook files started as templates, but Steps 2 and 7 filled them with **your** project information. By the time you undo, they are your writing, not the kit's. Deleting them because the kit created them would throw away exactly the work the kit was for.

**If you already had a file with one of these names before you ran the setup**, the setup was told to ask you first and to rename yours by adding `.before-starter-kit` to the end. Undoing puts that one back.

Say this to Claude:

> Undo the starter kit. Show me every file before you touch it, and do not touch anything not on this list.
>
> The list is exactly: in `~/.claude/rules/`, the eighteen files named below. In `~/.claude/commands/`: `learn.md`. In this project: `CLAUDE.md`, and inside `.claude/wiki/`, the two files `_hot.md` and `_log.md`.
>
> **Delete nothing.** Make a folder in my project called `starter-kit-undo-kept`, and for each file on the list that exists, move it in there, keeping the folder it came from as a subfolder so I can tell a rule from a notebook file. If `starter-kit-undo-kept` already exists, stop and tell me rather than writing into it.
>
> Then, for any file on the list that has a `.before-starter-kit` copy sitting beside where it was, rename that copy back to the original name. That is the file I had before the setup, and it goes back where it was.
>
> Then, only if `.claude/wiki/` is now completely empty, remove the folder itself. If anything else is in there it is mine, so leave the folder and tell me what is in it.
>
> Finally, list what is now in `starter-kit-undo-kept` and tell me plainly that nothing has been destroyed and I can delete that folder myself once I have looked through it.
>
> Do not touch anything else in `~/.claude/`, do not search the rest of my project for backup files, and tell me if anything on the list is missing rather than assuming.

Once you have looked inside `starter-kit-undo-kept` and are sure there is nothing in it you want, drag it to the Bin. That is the only deletion in this section, and you are the one doing it.

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

**A plugin:** open **Customize** in the left sidebar and click the **Plugins** tab. Same screen you checked during setup.

**A connection:** click the **+** button next to the prompt box, choose **Connectors**, pick the one you want, and disconnect. Same place you turned it on. That removes Claude's access. It changes nothing inside the tool itself.

## 3. Remove Claude Code entirely

**Read this before running it.** `~/.claude/` is not just this kit. It holds every plugin you have installed, your permission settings, your conversation history, anything Claude has remembered, and any rules or commands you wrote yourself. `~/.claude.json` holds account and connection state.

Deleting them is not "uninstalling the starter kit". It is resetting Claude Code to the day you installed it, and nothing here restores it afterwards.

If that is genuinely what you want, and only then, this is the command. It is one of the terminal situations flagged at the top of [START-HERE.md](../START-HERE.md). Finder can reach hidden folders through **Go** then **Go to Folder**, so you could delete them by hand instead; the documented route is the typed one below. Open Terminal, which lives in your Applications folder inside a subfolder called **Utilities**, and type:

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
