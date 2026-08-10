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

Beside it sits `~/.claude/starter-kit-baseline/`, holding an untouched copy of everything the setup put on your machine: the rules, the `/learn` command, each skill folder, and the exact text of any block it added to your `CLAUDE.md` or to a notebook you already kept, filed under the name of the project it happened in. A copy already in there is never overwritten, and none of it is ever used to repair anything. Its only job is to answer one question later: did I change this, or did it always look like that?

Say this to Claude:

> Show me `~/.claude/starter-kit-manifest.md`. For each line on it, check whether that file is actually still on disk and tell me. Do not change or remove anything.

You will see four kinds of thing.

**Files the kit added under its own name.** Every rule it installed starts with `starter-kit-`. That prefix exists for exactly this moment: those files are unambiguously the kit's, so removing them can never catch a rule of yours by accident.

**Things the kit added that carry NO prefix, and this is the part to read slowly.** The skills sit in their own named folders in `~/.claude/skills/`, and the `/learn` command is `~/.claude/commands/learn.md`. Neither is marked. `learn.md` cannot be, because Claude Code takes a command's name from its filename and renaming it would turn `/learn` into something else. The skill folders are not either, because a skill has to be found by its real name to work.

So for skills and for `learn.md`, the name alone does not tell you who put it there. The manifest does, and it is the only thing that does. It records each one as either installed by this kit or already yours and left alone. **Nothing in this section is safe to remove on the strength of its name.**

**Files that were already yours.** None of them were replaced, renamed or moved. If you had a rule, a `learn.md` command or a skill before you started, it is untouched. **Three of your files may have gained lines, and only ones you approved at the time:** your `CLAUDE.md`, and either or both of your two notebook files, `_hot.md` and `_log.md`, if you already kept them. Nothing in any of them was rewritten or removed, the manifest names every addition, and the baseline holds a copy of the added text so you can tell it from your own writing. Removing them is covered below. **That includes ones with the same name as something the kit offers:** if you already had a skill called `deep-review`, the setup stopped, showed you the collision and installed nothing over it. Your version is still there and **the kit never owned it.** The manifest records that as skipped rather than installed.

Those three are worth knowing precisely, because they are the only files of yours this setup writes into at all. **It only ever appends, only ever a block you approved when it showed you, and never once rewrites or removes a line you wrote.** The manifest names every block, and the baseline holds its exact text, so the file is still yours and the kit's additions are still identifiable years later. Removing them is covered below.

**Files that are now yours, whatever created them.** If you did not have a `CLAUDE.md` and the setup made one, it then interviewed you and filled it with your answers. The same is true of the two notebook files. Those started as this kit's templates and stopped being templates the moment you answered. **They are your writing, and nothing in this document treats them as the kit's to remove.** If you take everything else out, leave those exactly where they are. They are what makes Claude useful in this project, and they keep working on their own.

## 2. Remove the parts you no longer want

There is no command here that sweeps up. You look at the list and remove what you choose, and Claude does the removing while you watch.

**One thing to know before you start, because it is easy to get wrong.** The rules, the skills and the `/learn` command live in `~/.claude/`, which is **your whole machine, not this project**. If you have run this setup for more than one project, removing them here removes them everywhere. Only the `CLAUDE.md` and the notebook are specific to a single project. The manifest records which run installed what, so read it first and decide deliberately rather than assuming you are only affecting the folder you are sitting in.

**Do the comparison first, before you delete anything.** This is the step that stops you throwing away your own work, and it only takes one message:

> Compare everything the manifest lists against its copy in `~/.claude/starter-kit-baseline/`: the `starter-kit-` rules, `~/.claude/commands/learn.md`, each installed skill folder, and every block recorded as appended to my `CLAUDE.md` or to a notebook file, checking the folder for this project inside `appended-blocks/`. Show me every single thing that differs, with the differences. **Change and delete nothing.**

Four things can come back, and the last two matter most.

- **Identical to the baseline.** The kit installed it and you never touched it. Safe to remove.
- **Differs from the baseline.** Something changed it after it was installed, and the baseline itself never changes, so the difference is real. **It is usually you, but not always.** If you ran the setup again later and agreed to update a rule when it showed you the difference, that is the kit's change wearing the same appearance. The manifest's later dated sections are what tell the two apart, so read those before assuming the edit was yours. Either way, **a file in this category is worth looking at before you remove it.**
- **No baseline copy at all.** Usually this means **the kit never installed it**, so the thing on your disk is yours, or something you got somewhere else. The most likely case is a skill you already had, where the setup saw the collision and correctly installed nothing, or a rule you added later yourself from somewhere on the growth page. **Never delete anything in this category.** Check the manifest, which will show it as skipped rather than installed, or not name it at all.
- **One exception to that last one, and it is not a problem.** Your `CLAUDE.md` and your two notebook files have no baseline copy of the whole file, by design. Whether the setup created them and you filled them in, or they were already yours and only gained a block you approved, the file itself is your writing rather than the kit's. What the baseline holds for those is only the exact blocks that were **added**. They are on the manifest and they are not the kit's to remove, so they belong under "files that are now yours" above rather than in this list.

Work through that list before you read any further.

Then remove what you have decided to remove.

**The rules:**

> List every file in `~/.claude/rules/` whose name starts with `starter-kit-`, show me the list, and wait. Do not touch any other file in that folder, and do not touch anything not on the manifest. When I say go ahead, delete just the ones I name.

The reason for listing before deleting is that the folder is shared. Anything you have written yourself, or installed from anywhere else, lives there too, and a blanket delete would take those with it. You would not notice until something stopped behaving the way you taught it.

**A skill:** skill folders carry no prefix, so **check the manifest says this kit installed it, not that it found it already there and skipped it**, and check it has a baseline copy. A skill with no baseline copy is one the kit never installed, which means it is yours. Then name it and have Claude delete that folder in `~/.claude/skills/`. Same principle: name the ones you mean, and being on the manifest is not the same as having been installed by it.

**The `/learn` command:** delete `~/.claude/commands/learn.md`. Check the manifest first, because if you already had a `learn.md` of your own the setup left yours alone and installed nothing.

**What the kit added to a notebook you already kept:** if Step 9 added lines to a `_hot.md` or `_log.md` that was already yours, the manifest names them and the baseline holds their exact text under this project's folder. Ask Claude to show you those lines beside the copy in the baseline, and to remove only the ones you name. **Everything else in those files is your own writing and nothing here treats it as removable.** If the setup created the notebook rather than finding it, there is nothing to take out: the file is yours, see above.

**What the kit added to your `CLAUDE.md`:**

> List every block the manifest records as appended to my `CLAUDE.md`, including the two notebook headings `## Start of every conversation` and `## End of every working session`. Show me each one as it stands now beside the copy in the baseline. Then remove only the ones I name, and leave the rest of the file exactly as it is.

If the setup created that file rather than adding to it, skip this entirely. The file is yours now, and taking sections out of it is just editing your own notes.

**To remove one rule rather than all of them,** delete just that file by name. Nothing else depends on any single one.

**When you are not sure about anything, keep it.** An extra rule costs you nothing. A deleted file you had improved is gone.

Then ask Claude to list `~/.claude/rules/`, `~/.claude/commands/` and `~/.claude/skills/` so you can see what is left.

**Three things are left over once you are done, and none of them does anything.** The `starter-kit` folder in your project, which you can drag to the Bin whenever you like. And the manifest and the baseline folder in `~/.claude/`. **Keep those last two while any of this is still installed anywhere**, because together they are the only record of what was put where and what it looked like. They are small and they cost nothing to leave. Once you have removed everything from every project, they are safe to delete too.

## 3. Remove a plugin or a connection

**A plugin:** **check the manifest first.** It records, for each plugin, whether it was already installed before your setup ran or installed during it. Removing one you already had would be taking away something that was never the kit's to add, and the screen itself cannot tell you which is which. Then open **Customize** in the left sidebar and click the **Plugins** tab. Same screen you checked during setup.

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
