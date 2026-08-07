# How to stop, go back, and take this kit out again

Knowing the way out is what makes you willing to try things. Read this once now, before you need it.

**The short version: this kit never removes anything.** The setup only ever adds, and it writes down everything it adds. So there is nothing to restore, nothing to dig out of a folder, and no way for undoing it to cost you work. Taking it out is you deleting files you can see on a list, if and when you want to.

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

# Taking this kit back out

The four sections below are deliberately separate, and they get progressively less reversible. Do not run the later ones to achieve the earlier ones.

## 1. See exactly what was added

Everything the setup installed is written down as it happens, in a file at `~/.claude/starter-kit-manifest.md`. That is the list. Nothing was added that is not on it.

Beside it sits `~/.claude/starter-kit-baseline/`, an untouched copy of every file exactly as it was installed. It is never written to again and never used to repair anything. Its only job is to answer one question later: did I change this file, or did it always look like that?

Say this to Claude:

> Show me `~/.claude/starter-kit-manifest.md`. For each line on it, check whether that file is actually still on disk and tell me. Do not change or remove anything.

You will see three kinds of thing.

**Files the kit added under its own name.** Every rule it installed starts with `starter-kit-`. That prefix exists for exactly this moment: those files are unambiguously the kit's, so removing them can never catch a rule of yours by accident. The skills it downloaded sit in their own named folders in `~/.claude/skills/`. The one thing without a prefix is `~/.claude/commands/learn.md`, because Claude Code takes a command's name from its filename and renaming it would turn `/learn` into something else.

**Files that were already yours.** None of them were replaced, renamed or moved. If you had a rule, a notebook file or a skill before you started, it is untouched.

There is one exception and it is worth knowing precisely. **If you already had a `CLAUDE.md`, the setup may have added sections to it, but only ones you said yes to at the time.** Nothing in it was rewritten or removed. The manifest names every block that was appended, so the file is still yours and the additions are still identifiable. Removing them is covered below.

**Files that are now yours, whatever created them.** If you did not have a `CLAUDE.md` and the setup made one, it then interviewed you and filled it with your answers. The same is true of the two notebook files. Those started as this kit's templates and stopped being templates the moment you answered. **They are your writing, and nothing in this document treats them as the kit's to remove.** If you take everything else out, leave those exactly where they are. They are what makes Claude useful in this project, and they keep working on their own.

Three things are left over even after all of the above, and none of them does anything: the `starter-kit` folder you dragged into your project, which you can drag to the Bin whenever you like, and the manifest and baseline folder in `~/.claude/`. Keep those last two while any of this is still installed anywhere, because together they are the only record of what was put where and what it looked like. They are small, and they cost nothing to leave.

## 2. Remove the parts you no longer want

There is no command here that sweeps up. You look at the list and remove what you choose, and Claude does the removing while you watch.

**One thing to know before you start, because it is easy to get wrong.** The rules, the skills and the `/learn` command live in `~/.claude/`, which is **your whole machine, not this project**. If you have run this setup for more than one project, removing them here removes them everywhere. Only the `CLAUDE.md` and the notebook are specific to a single project. The manifest records which run installed what, so read it first and decide deliberately rather than assuming you are only affecting the folder you are sitting in.

**To take out the rules,** say:

> List every file in `~/.claude/rules/` whose name starts with `starter-kit-`, show me the list, and wait. Do not touch any other file in that folder, and do not touch anything not on the manifest. When I say go ahead, delete just the ones I name.

The reason for listing before deleting is that the folder is shared. Anything you have written yourself, or installed from anywhere else, lives there too, and a blanket delete would take those with it. You would not notice until something stopped behaving the way you taught it.

**If you edited one of the kit's rules, you will want to keep your version,** and a file you improved six weeks ago does not look any different from one you never opened. So do not trust your memory. Say:

> Compare every `starter-kit-` rule in `~/.claude/rules/` against its copy in `~/.claude/starter-kit-baseline/rules/` and show me every file that differs, with the differences.

Anything that differs is something you changed, because the baseline is what was installed and nothing has written to it since. Keep those. **When you are not sure, keep the file anyway.** An extra rule costs you nothing; a deleted one you had improved is gone.

**To take out a skill,** name it from the manifest list and have Claude delete that folder in `~/.claude/skills/`. Same principle as the rules: name the ones you mean.

**And check the same way first.** Have Claude compare the folder against its copy in `~/.claude/starter-kit-baseline/skills/`. Anything that differs is yours. That comparison is reliable because the baseline never changes, whereas comparing against the repository online is not: those authors keep working, so a difference there might be their newer version rather than your edit.

**To take out what the kit added to your `CLAUDE.md`,** say:

> Read the manifest and list every block it records as appended to my `CLAUDE.md`, including the two notebook headings `## Start of every conversation` and `## End of every working session`. Show me each block as it stands **now**, and compare it against what the manifest says was originally added. If I have edited or added anything inside one of them, show me that first and ask, because those words are mine even though the heading came from the kit. Then remove only the ones I name and leave the rest of the file exactly as it is.

Provided you look at that comparison, none of it touches a word you wrote. If the setup created the file rather than adding to it, skip this entirely: the file is yours now, and taking sections out of it is just editing your own notes.

**To take out the `/learn` command,** delete `~/.claude/commands/learn.md`. Check the manifest first, because if you already had a `learn.md` of your own, the setup will have left yours alone and installed nothing there.

**To remove one rule rather than all of them,** delete just that file by name. Nothing else depends on any single one.

Then ask Claude to list `~/.claude/rules/`, `~/.claude/commands/` and `~/.claude/skills/` so you can see what is left.

## 3. Remove a plugin or a connection

**A plugin:** open **Customize** in the left sidebar and click the **Plugins** tab. Same screen you checked during setup.

**A connection:** click the **+** button next to the prompt box, choose **Connectors**, pick the one you want, and disconnect. Same place you turned it on. That removes Claude's access. It changes nothing inside the tool itself.

## 4. Remove Claude Code entirely

**Read this before running it.** `~/.claude/` is not just this kit. It holds every plugin you have installed, your permission settings, your conversation history, anything Claude has remembered, and any rules, skills or commands you wrote yourself. `~/.claude.json` holds account and connection state.

Deleting them is not "uninstalling the starter kit". It is resetting Claude Code to the day you installed it, and nothing here restores it afterwards.

If that is genuinely what you want, and only then, this is the command. It is deliberately one you type yourself rather than one you ask Claude to run, because asking Claude Code to delete its own settings while it is running is a bad idea. Finder can reach hidden folders through **Go** then **Go to Folder**, so you could delete them by hand instead; the documented route is the typed one below. Open Terminal, which lives in your Applications folder inside a subfolder called **Utilities**, and type:

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
