# Start here

You have used Claude in a browser. Claude Code is the same Claude with access to the files in one folder you choose, so it hands you a finished spreadsheet instead of describing one, and it can remember your project between conversations if you set it up to.

It comes in two forms. Most guides you will find describe the one that runs in a terminal. **This one uses the desktop app, which is the same Claude Code with a normal Mac interface**, and Anthropic's own documentation on it says *"No terminal required."* Setting it up is clicking and pasting the whole way through.

**This kit adds to what you already have. It never replaces it.** If you have used Claude Code before and have your own rules, your own instructions file, your own skills, none of them are replaced, renamed or deleted. The one thing that can change is your project instructions file, and only by having a section added that you said yes to. The setup looks at what is there first, tells you where this kit fills a gap, tells you where it overlaps with something of yours, and asks you to decide. Nothing is copied over anything. If you are starting from an empty machine, there is simply nothing to decide and it all goes in.

**Part 1 is clicking, about ten minutes.** Then you paste a brief into Claude and it sets itself up while you watch, stopping after each step to show you it worked. Part 2 takes longer than it used to, usually twenty to forty minutes, because it now downloads a handful of skills and because you are making real choices in the middle of it rather than watching a copy run.

Three things before you start.

**You need a paid Claude plan.** Pro, Max, Team or Enterprise. The free plan does not include Claude Code, so check this before you begin. Nothing later on this page works around it.

**You need macOS 11 (Big Sur) or later.** Apple menu, then About This Mac. That is the app's requirement; the terminal version in the fold at the bottom needs macOS 13.

**You need Git, and this is the one thing that might not already be true.** Git is a standard developer tool that most Macs already have. Day one uses it, because every skill is downloaded from the repository that maintains it rather than shipped inside this kit, so you can update them later. If your Mac turns out not to have it, Claude can install it for you and a normal macOS window appears for you to click. That is covered under "If something went wrong" at the bottom of this page.

You do **not** need Node.js, npm or Homebrew. The app includes everything else.

---

# Part 1: clicking

## 1.1 Make a folder for your first project

In Finder, make a folder for something you are actually working on. `Documents` is a fine home for it. Anything real beats a folder called `test`, because the last step of this setup produces actual work and you want it somewhere you will look again.

If you already have a project you use Claude Code on, use that one. The setup is built to land on top of an existing setup without disturbing it.

## 1.2 Put this kit inside that folder

**If you are reading this on GitHub:** click the green **Code** button near the top of this web page and choose **Download ZIP**. That is GitHub's button, in your browser. It is not the **Code** tab inside the Claude app, which you will meet in 1.4 and which is a different thing with the same name. Then look in your Downloads folder. If you see a zip file, double-click it to unzip. If you see a folder already, Safari unzipped it for you, which it does by default, and there is nothing to click.

**If someone sent you the folder directly:** you already have it.

Now drag that folder into your project folder and rename it to `starter-kit`. Downloads from GitHub arrive with `-main` on the end of the name, which is normal and is why you are renaming it.

Your project folder should now contain one folder called `starter-kit`. That is all Part 1 needs from you in Finder.

## 1.3 Install the Claude app

[**Download for macOS**](https://claude.ai/api/desktop/darwin/universal/dmg/latest/redirect). One build works on both Intel and Apple Silicon, so you do not need to know which you have.

Open the downloaded file and drag Claude into your Applications folder, the same as any other Mac app. Launch it and sign in with the account your paid plan is on.

If you already have it installed, skip to 1.4.

## 1.4 Open the Code tab

Three tabs sit across the top: **Chat**, **Cowork** and **Code**.

- **Chat** is the Claude you already know. No access to your files.
- **Cowork** runs longer jobs on its own in the background.
- **Code** is the one you want. It works with the files in a folder you pick, and proposes every edit for you to accept before it happens.

Click **Code**.

If it asks you to upgrade, your plan does not include Claude Code yet. If it asks you to sign in online, do that and restart the app.

## 1.5 Point it at your folder

Choose **Local** for the environment. That means Claude works on your own machine with your own files, which is what you want.

Then click **Select folder**.

**Choose the outer folder, the one you made in 1.1. Do not choose `starter-kit`.** This is the easiest thing on the page to get wrong, because `starter-kit` is the folder you were just handling and it has the more interesting name. Pick it and every instruction in Part 2 points one level too deep, and the setup fails on its second step.

You have it right if the folder you selected *contains* `starter-kit` rather than being it.

Claude now works with the files in that folder. It will ask you before doing anything outside it. There are three expected reasons to leave it during this setup, all worth understanding now rather than being surprised by: writing down what gets installed, putting the rules into your settings folder, and downloading skills into it. All three are flagged in the steps where they happen. If it asks for something you did not expect, that is your cue to ask why before saying yes.

## 1.6 Understand what it will and will not do

This is the part worth thirty seconds, because it is what makes everything after it safe to try.

The Code tab starts in **Manual mode**. Claude does not edit your files. It *proposes* a change, shows you a diff, which is a side-by-side of exactly what would change, and waits. You press **Accept** or **Reject**. Anthropic's documentation is unambiguous: *"Your files aren't modified until you accept."*

If you reject something, Claude asks how you would rather do it.

Two more controls worth knowing before you need them:

- **The promise covers edits, not commands.** When Claude proposes an edit to a file, you get the diff and it waits. When it asks to *run a command*, such as copying a file or downloading one, you are approving the command rather than seeing a preview of everything it will change on disk. Those changes also sit outside `/rewind`. The setup below is written to tell you what each command will touch before it asks, and it is fair to make it say so if it does not.
- **Stop it any time.** Click the stop button. Or just type what you actually wanted and press Enter, which redirects it without stopping first.
- **Other modes exist**, in a selector next to the send button. *Accept edits* stops asking, which is faster once you trust it. *Plan* makes it think out loud without touching anything. There are more than these, and which you see depends on your plan and setup, so read the selector rather than trusting this list. Stay in Manual for now.

You are set up. Everything from here is Claude doing the work.

---

# Part 2: hand this to Claude

Copy everything between the two lines and paste it into the Code tab.

In Manual mode, which is where you start, expect it to ask before it edits a file or runs a command. Permissions you have already granted, on this machine or by whoever set it up, can change which further prompts appear. Read what it asks.

Some requests will look alarming and are not. In Steps 2, 4 and 6 it asks to write into `~/.claude/`, a hidden settings folder in your home directory, **outside your project**. That is the point: the list of what was installed, the rules and the skills all go there so they apply in every project from now on, not just this one. If they went in your project folder they would only ever apply here. Say yes to those three. Anything else that wants to leave your project folder, ask it why first.

**Know the way out before you go in.** [`reference/undo.md`](reference/undo.md) shows you exactly what was added and where, and it is worth two minutes now.

✂ ---------- copy below this line ----------

I am using the Claude Code desktop app, not the terminal. I have signed in, I am in the Code tab, and I have selected my project folder. Inside it is a folder called `starter-kit`.

Work through the steps below **in order**, and **stop after each numbered step** to show me what you did and what proof you have that it worked. Do not run several and then summarise. I want to see each one land.

Ground rules for this whole setup:

- Explain what each step does in plain words **before** you do it, in a sentence or two, the way you would to a smart friend. No jargon without explaining it in the same sentence.
- Never tell me something worked because you expect it to. Run a check, show me the result, tell me what I should be seeing.
- If a step fails, stop and tell me. Do not work around it silently and do not move on.
- Some steps below are mine to click, not yours to run. When you reach one, hand it to me clearly and wait.
- If anything in these instructions turns out to be wrong on my machine, say so plainly rather than making it fit.
- **Never delete, move, rename or overwrite anything of mine.** This kit adds; it does not replace. That applies to every file already on this machine, whether it is in my project or in `~/.claude/`, and whether or not it has the same name as something you are about to add. If something you want to add would collide with something I have, that is a decision for me, not a problem for you to solve quietly. The rules below say how to bring it to me.
- **Where the two of us overlap, show me the choice.** When this kit offers something and I already have something covering the same ground, tell me what each one does, what I would gain and lose either way, and which you would pick and why. Say how confident you are, and say what would change your mind. If combining them genuinely makes more sense than picking one, propose the combination and show me what it would look like. Then wait. I decide.
- **Write down what you add, as you go.** Keep a file at `~/.claude/starter-kit-manifest.md` listing every file you add, where it came from, and today's date. Create it in Step 2 and add a line to it every time you install something. It is what makes Step 11 honest.

**Step 1. Show me where I am and what you can reach.**
Tell me which folder you are working in and list what is in it. Then explain in two sentences how your access actually works: that you can see this folder, that you will ask before touching anything outside it, and that you are about to ask exactly that in Steps 2, 4 and 6 when you write into my settings folder. I would rather understand the real boundary than be told a comforting version of it.

**Step 2. Look at what I already have, before you offer me anything.**
This is the step that makes the rest of the setup safe, so do it properly rather than quickly.

Look in all of these and tell me plainly what is there, or that it is empty:

- `~/.claude/rules/` and `~/.claude/commands/`
- `~/.claude/skills/` (report just the names and roughly how many, but read enough of any `SKILL.md` that looks related to tell me what it actually does; a skill of mine with an unrelated name can still cover the same ground)
- `CLAUDE.md` in my project folder
- `.claude/wiki/` in my project folder

Then read `starter-kit/reference/what-this-adds.md`, which is the catalogue of everything this kit can install and what each thing is for. Compare the two and give me **three lists**:

1. **Gaps.** Things this kit offers where I currently have nothing. These are pure additions and there is nothing for me to decide beyond whether I want them.
2. **Overlaps.** Things where I already have something covering the same ground. For each one, name mine, name the kit's, say what is actually different between them, and give me your recommendation with your reasoning and what you are unsure about. Do not decide any of these yourself.
3. **Already covered better.** Anything where what I have is stronger than what the kit offers. Say so plainly and take it off the list. I would rather install less than be told everything is an upgrade.

Judge overlap by **what a thing does, not what its file is called.** A rule of mine called something completely different may cover exactly the same ground as one of yours, and two files with the same name may do unrelated things. Read enough of each to tell.

Then ask me to accept or skip, **including the gaps**. A gap is still something landing on my machine, so silence is not agreement.

Give me the gaps as a compact table, one row per thing, with three columns: what it is in plain words, what it would do for me, and anything it collides with or "nothing found". Group the rules into their three blocks rather than listing eighteen rows. Then say which ones you would take and why, and tell me I can accept the lot, accept by group, or name individual ones to skip. **Do not treat a general yes as covering an item you never showed me.**

Then deal with the list of what gets installed. It lives at `~/.claude/starter-kit-manifest.md`. **This one is not optional and I am not being asked about it**, because it is the record that makes removing things later exact instead of guesswork. Tell me that plainly rather than slipping it past me. **If that file already exists, this setup has run on this machine before. Do not replace it.** Read it to me, then add a new dated section to the bottom for this run, headed with today's date and the full path of this project. If it does not exist, create it with that same first section. Either way the old entries survive, because they are the only record of what an earlier run put where.

**Step 3. Create or extend my project instructions file.**
`CLAUDE.md` is the file you read at the start of every conversation about this project, which is why it has to stay short and true. Explain that before you touch it.

**If I do not have one:** copy `starter-kit/templates/CLAUDE.md` to `CLAUDE.md` in my project folder, then interview me to fill it in: what this project is, who it is for, what it is built with if anything, and how I want you to work with me. Ask one question at a time, do not dump a list. Keep the finished file under one page.

**If I already have one:** do not replace it and do not rewrite it. Read it, then read the template, and tell me which sections the template has that mine does not. For each one, show me the section and ask whether I want it added. Add only what I say yes to, and add it without disturbing what is already there. If mine already says something the template says differently, show me both versions side by side and tell me they differ. **Existing text is never replaced by this setup.** If I prefer the template's wording, say plainly that changing my own sentence is an edit I should make deliberately, offer to do it as a separate task once the setup is finished, and move on rather than doing it here.

Either way, record in the manifest what you created or which sections you appended.

**Step 4. Install the rules, without touching any rule I already have.**
The rules are short instruction files that load at the start of every conversation, in every project. Explain that first, and explain that this is the step that writes outside my project folder.

Install the numbered `.md` files from `starter-kit/rules/` into `~/.claude/rules/`, creating that folder if it does not exist. **Add `starter-kit-` to the front of each filename as you install it**, so `03-write-the-project-instructions.md` lands as `starter-kit-03-write-the-project-instructions.md`. Tell me why: it makes it impossible for one of these to land on top of a rule I already have, and it means Step 11 can tell mine from yours without guessing. Do not copy `rules/README.md`, which explains the set rather than being part of it. Then copy `starter-kit/commands/learn.md` into `~/.claude/commands/`, **keeping the name `learn.md` exactly**. Do not add the prefix to this one. Claude Code takes a command's name from its filename, so renaming it would give me `/starter-kit-learn` while every other page here promises `/learn`. If a `learn.md` is already in that folder, stop and bring it to me under the overlap rule rather than touching it, and tell me that installing it under a different name would change what I type.

**Install only the ones I agreed to in Step 2.** If I said no to one because it overlaps with something of mine, skip it and say so in your count.

**If a `starter-kit-` file is already there,** this setup has run on this machine before, probably for a different project. Do not overwrite it, because I may have edited it since. Tell me it is already installed, and if the version in `starter-kit/rules/` differs from the one on disk, show me the difference and ask before changing anything.

Verify by listing both folders and showing me the count, and add each installed file to the manifest.

Then tell me the honest limitation, because it would be easy to let me assume otherwise. Claude Code reads that folder when a conversation **starts**, so these files change nothing for the rest of this one. They load from my **next** conversation onward, in every project, and they work the same whether I use the app or the terminal. The same is true of `/learn`: it becomes available next time, not now.

Show me the titles so I know what I agreed to, and tell me `starter-kit/rules/README.md` says which to read first. Then tell me how to check they actually loaded: start a new conversation and ask you to list the rules you can see. If the titles come back, they are live.

**Step 5. Have me look at the plugins I already have, before either of us installs anything.**
Anthropic adds a catalogue of work plugins by default, called the Knowledge Work marketplace. That means the one I want is almost certainly listed, and it may already be installed. Those are two different things, so tell me which you are asking me to check. Looking first costs thirty seconds and saves me installing something twice.

Tell me to open **Customize** in the left sidebar and click the **Plugins** tab. Then wait for me. This screen is mine to look at, not yours to run.

While I have it open, ask me whether **Product Management** is in the list, and have me read out what I see next to it.

Being listed and being installed are not the same thing, so go by what the screen says next to it, not by whether the name appears:

- **If it says it is installed or enabled,** nothing to do. Tell me in one line what it adds, and carry on.
- **If there is an Install button next to it,** tell me to click it, and wait until I tell you it has finished.
- **If it is not in the list at all,** tell me to use the **Browse** button on that same screen to find it, and talk me through it while I look. Once I have found it, have me click **Install** and wait until the screen says it is installed or enabled before you go on.

Either way, do not tell me it worked until I have told you what I can see. Step 8 needs this plugin actually installed, so if I read out something that does not match any of the three cases above, say so rather than guessing which one I meant.

Then show me what else is in that set and let me choose one or two more, so I end up with two or three in total. Ones worth considering, depending on what I told you in Step 3 that this project is: `small-business`, `marketing`, `brand-voice`, `design`, `data`, `operations`, `engineering`. Explain each in one line. **Do not tell me to install them all.**

Two things that may not match, and I would rather you say so than smooth over: that list of names comes from the published set and what my screen offers can lag behind it, and the panel may be showing plugins for the folder I currently have open. If a name I pick is not on my screen, tell me plainly instead of assuming it is hiding somewhere.

When I say I am done, verify what I actually ended up with and show me. **Record the plugins in the manifest**, and for each one say whether it was already installed before today or installed during this run. Undo depends on that difference, because removing a plugin I already had would be taking away something that was never yours to add.

**Step 6. Install the skills I agreed to in Step 2.**
A skill is a set of instructions you load when a particular kind of job comes up, so you follow a worked method instead of improvising. Explain that in one sentence before you install anything.

**None of them are copied inside this kit.** Every one is downloaded from the repository that maintains it, so I can pull a newer version later instead of being stuck with whatever was current the day this kit was written. They come from two places and the difference matters, so tell me which is which as you go. `starter-kit/reference/what-this-adds.md` names the repository and licence for every one.

- **From the author's own public repositories.** `deep-review`, `llm-wiki`, `doc-confluence` and `audit`. Download each repository and copy the skill folder into `~/.claude/skills/`.
- **From other people's public repositories.** Five skills from `obra/superpowers`, written by Jesse Vincent, MIT licensed. Same method. Tell me who wrote them as you install them, and tell me the credits are in the kit's README.

**Never overwrite a skill folder that is already in `~/.claude/skills/`.** If one of these names already exists there, stop and bring it to me under the overlap rule above. Mine may be a version I have edited.

Be exact about where things go, because a skill in the wrong place looks installed and does nothing. Create `~/.claude/skills/` first if it is not there. Download each repository into a temporary folder outside my project, copy the skill's own folder to `~/.claude/skills/<skill-name>/` so that `SKILL.md` sits directly inside it, then delete the temporary download and tell me you have. **Never overwrite a folder that is already there**, per the rule above.

Downloading uses Git. If Git turns out to be missing, stop and tell me, and point me at the note at the bottom of `START-HERE.md`. Do not try to work around it.

After each one, check the folder actually contains a `SKILL.md` and show me. A folder that downloaded empty is the failure mode here, and it looks exactly like success until I try to use it. Add every skill to the manifest with the repository it came from.

Then tell me how to check they are actually available, rather than asserting it: ask you to list the skills you can see. If a new one is missing, the reliable fix is to start a new conversation, because that is when the folder is read afresh. Do not promise me it works in this conversation and do not promise me it does not; have me look.

**Step 7. Tell me what came with the plugins.**
Tell me the product-management plugin also brought sixteen connections to tools like Slack, Notion, Linear, Jira and Figma, and that I turn one on with the **+** button next to the prompt box, choosing **Connectors**. That is a different menu from the **Customize** screen you sent me to in Step 5, so tell me plainly that this is the **+** button next to where I type, not the sidebar.
Tell me that two of the sixteen, Gmail and Google Calendar, arrive with no address filled in and are not covered by this kit, so I should skip them rather than spend day one on mail and calendar. Say that plainly rather than letting me discover it by failing.
Tell me `starter-kit/reference/connectors.md` explains what is there and what to be careful about. Do not connect any of them now.

**Step 8. Prove it works on something real.**
Ask me what I am actually working on this week. Then use the product-management plugin to produce a real first draft of it: a spec, a competitive brief, a research synthesis, whatever fits. Not a demo, the real thing.
This step matters more than the seven before it. If I do not see something useful today I will not come back tomorrow.

**Step 9. Set up the notebook that survives between conversations.**
Every new conversation starts knowing nothing about the last one. Fix that now, before it costs me a Monday morning.

Create `.claude/wiki/` if it is not already there. Then handle `_hot.md` and `_log.md` **one at a time and independently**, because the folder may already exist for reasons that have nothing to do with either file, and I might have one of the two and not the other.

For each of the two, in turn: **if it is not there, copy it in from `starter-kit/templates/` and use Branch A. If it is already there, it is mine, so use Branch B.** Tell me which branch you used for which file.

**Branch A, the file did not exist and you just copied it.** Fill it in now rather than leaving me the template. It arrives as placeholders in square brackets with `YYYY-MM-DD` where the date goes, and a placeholder left in place is worse than an empty file, because the next conversation reads it as if it were true. Use what you already know from today: what I told you this project is in Step 3, the piece of work you produced in Step 8, and anything I said was next or unresolved. Put today's real date in it. Where you genuinely do not know, ask me one question rather than inventing an answer or leaving the bracket. `_log.md` also arrives with a second, blank entry as an example of the shape; delete that one and write a single real entry for today. Then read the finished file back to me so I can see there is no `[` and no `YYYY-MM-DD` left.

**Branch B, the file was already mine.** Change nothing yet. Show me what is in it, tell me whether it still looks current, and propose the lines you would add for today. Show me that as a diff and wait for my yes. **Do not delete anything from it, including anything that looks like a leftover example, because you cannot tell my shorthand from a template I never cleaned up.** Adding to a notebook I already keep is the whole idea; rewriting it is not.

Then add the block from `starter-kit/templates/CLAUDE-wiki-snippet.md` to the bottom of my `CLAUDE.md` so you actually read them, unless something equivalent is already in there, in which case say so and skip it. Record in the manifest that you appended it, naming the two headings, so it can be found again.
Show me what to say at the end of a working session to keep them current. Record what you created in the manifest.

**Step 10. Read the manifest back to me.**
Show me `~/.claude/starter-kit-manifest.md` in full, including any sections from earlier runs, which are history and must not be edited or "corrected".

**Check today's section only** against what you actually did in this session: every file you added should be on it and nothing should be on it that you did not do. For the older sections, check just one thing, whether the paths they record still exist, and report anything missing as information rather than as an error. Check against the file system rather than against your memory of the session. This is the file Step 11 depends on, so it being wrong is worse than it being short.

**Step 11. Talk me through how I would remove all of this. Do not remove anything.**
Read `starter-kit/reference/undo.md` and explain it to me, checking each item against the manifest and against what you actually did in this session. **This step is reading and explaining only. Do not delete, move or reverse a single thing, and do not run any command from that file.** Today I want to know the way out exists, not to take it. Tell me if anything in it does not match what you actually installed.

**Step 12. Tell me what you did NOT install and why.**
Read `starter-kit/GROWTH.md` and summarise it: what is deliberately held back, and the specific moment that should bring me back for each one. **Two of its entries, `deep-review` and `audit`, were offered today**, so say for each whether I accepted it, skipped it, or already had it, rather than listing it as missing. **Do not install any of it now.**

Then stop. I have enough for today.

✂ ---------- copy above this line ----------

---

## What you should have at the end

A project folder Claude works in. A `CLAUDE.md` it reads every time, either new or extended without losing what was already in it. A set of rules loaded into every conversation, none of which landed on top of anything of yours. A handful of skills, every one of them downloaded from the repository that maintains it, so you can update them later. Two or three plugins that do your actual job, plus sixteen tool connections waiting whenever you want them. A notebook that survives between conversations. One real piece of work already finished. And a list, at `~/.claude/starter-kit-manifest.md`, of exactly what was added and where.

Everything else waits until you feel the problem it solves, and [GROWTH.md](GROWTH.md) names those moments.

## If something went wrong

**The Code tab shows an error about Git, or Step 6 could not download something.** Most Macs have Git already, but not all. You do not need to open anything yourself. Say to Claude:

> Git seems to be missing. Run `xcode-select --install` and tell me what to expect.

A normal macOS window appears asking you to install the developer command line tools. Click **Install**. It is about a gigabyte. That window is expected and you have not broken anything. When it finishes, tell Claude and it can carry on from the step that failed.

If that does not work for any reason, the same command typed into Terminal does the same job. Terminal lives in your Applications folder inside a subfolder called **Utilities**.

**A step in Part 2 failed.** Tell Claude exactly what you saw, including the error text, and ask it to explain the error before fixing it. Understanding the failure is worth more on day one than getting past it.

**A skill installed but does not appear.** Skills load when a conversation starts. Start a new conversation and ask Claude to list the skills it can see. If it is still missing, check the folder has a `SKILL.md` in it, because an empty folder from a failed download looks exactly like a successful install.

<details>
<summary>⌨️ <b>If you would rather use the terminal version</b></summary>

<br>

The desktop app and the terminal version are the same Claude Code and share the same configuration, so everything in this kit works either way. The rules, the `CLAUDE.md`, the templates, the skills and the notebook are identical. Only the setup differs.

If you already live in a terminal, or you are on Linux, install the command-line version instead:

```bash
curl -fsSL https://claude.ai/install.sh | bash
```

Then quit Terminal and open it again, or the next line will say "command not found". Check it took:

```bash
claude --version
```

Move into your project folder and start it:

```bash
cd ~/Documents/my-project
claude
```

Two differences from the steps above. Plugins install by typing a command rather than clicking:

```
/plugin marketplace add anthropics/knowledge-work-plugins
/plugin install product-management@knowledge-work-plugins
```

followed by `/reload-plugins`. And that command downloads using Git, so you need it installed, which the Git note above covers.

You can run both the app and the terminal on the same project at once. `/usage` shows how much of your plan you have used, in either one.

</details>
