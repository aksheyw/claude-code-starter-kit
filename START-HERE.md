# Start here

You have used Claude in a browser. Claude Code is the same Claude with access to the files in one folder you choose, so it hands you a finished spreadsheet instead of describing one, and it can remember your project between conversations if you set it up to.

It comes in two forms. Most guides you will find describe the one that runs in a terminal. **This one uses the desktop app, which is the same Claude Code with a normal Mac interface**, and Anthropic's own documentation on it says *"No terminal required."* Setting it up is clicking. The one exception is rare and is at the bottom of this page.

**Part 1 is clicking, about ten minutes.** Then you paste a brief into Claude and it sets itself up while you watch, stopping after each step to show you it worked.

Two things before you start.

**You need a paid Claude plan.** Pro, Max, Team or Enterprise. The free plan does not include Claude Code, and this is the most common way day one stops dead.

**You need macOS 13 or later.** Apple menu, then About This Mac.

You do **not** need Node.js, npm, Homebrew, or the command line. The app includes everything.

---

# Part 1: clicking

## 1.1 Make a folder for your first project

In Finder, make a folder for something you are actually working on. `Documents` is a fine home for it. Anything real beats a folder called `test`, because the last step of this setup produces actual work and you want it somewhere you will look again.

## 1.2 Put this kit inside that folder

**If you are reading this on GitHub:** click the green **Code** button near the top and choose **Download ZIP**. Then look in your Downloads folder. If you see a zip file, double-click it to unzip. If you see a folder already, Safari unzipped it for you, which it does by default, and there is nothing to click.

**If someone sent you the folder directly:** you already have it.

Now drag that folder into your project folder and rename it to `starter-kit`. Downloads from GitHub arrive with `-main` on the end of the name, which is normal and is why you are renaming it.

Your project folder should now contain one folder called `starter-kit`. That is all Part 1 needs from you in Finder.

## 1.3 Install the Claude app

[**Download for macOS**](https://claude.ai/api/desktop/darwin/universal/dmg/latest/redirect). One build works on both Intel and Apple Silicon, so you do not need to know which you have.

Open the downloaded file and drag Claude into your Applications folder, the same as any other Mac app. Launch it and sign in with the account your paid plan is on.

## 1.4 Open the Code tab

Three tabs sit across the top: **Chat**, **Cowork** and **Code**.

- **Chat** is the Claude you already know. No access to your files.
- **Cowork** runs longer jobs on its own in the background.
- **Code** is the one you want. It works with the files in a folder you pick, and shows you every change before it happens.

Click **Code**.

If it asks you to upgrade, your plan does not include Claude Code yet. If it asks you to sign in online, do that and restart the app.

## 1.5 Point it at your folder

Choose **Local** for the environment. That means Claude works on your own machine with your own files, which is what you want.

Then click **Select folder**.

**Choose the outer folder, the one you made in 1.1. Do not choose `starter-kit`.** This is the easiest thing on the page to get wrong, because `starter-kit` is the folder you were just handling and it has the more interesting name. Pick it and every instruction in Part 2 points one level too deep, and the setup fails on its second step.

You have it right if the folder you selected *contains* `starter-kit` rather than being it.

Claude now works with the files in that folder. It will ask you before doing anything outside it, and it will ask exactly once during setup, in Step 3, for a reason worth understanding now rather than being surprised by.

## 1.6 Understand what it will and will not do

This is the part worth thirty seconds, because it is what makes everything after it safe to try.

The Code tab starts in **Manual mode**. Claude does not edit your files. It *proposes* a change, shows you a diff, which is a side-by-side of exactly what would change, and waits. You press **Accept** or **Reject**. Anthropic's documentation is unambiguous: *"Your files aren't modified until you accept."*

If you reject something, Claude asks how you would rather do it.

Two more controls worth knowing before you need them:

- **Stop it any time.** Click the stop button. Or just type what you actually wanted and press Enter, which redirects it without stopping first.
- **Two other modes exist.** *Accept edits* stops asking, which is faster once you trust it. *Plan* makes it think out loud without touching anything. Stay in Manual for now.

You are set up. Everything from here is Claude doing the work.

---

# Part 2: hand this to Claude

Copy everything between the two lines and paste it into the Code tab.

It will ask permission before it does anything. Read what it asks.

One request will look alarming and is not. In Step 3 it asks to write into `~/.claude/`, a hidden settings folder in your home directory, **outside your project**. That is the point: the rules go there so they load in every project from now on, not just this one. If they went in your project folder they would only ever apply here. Say yes to that one. Anything else that wants to leave your project folder, ask it why first.

**Know the way out before you go in.** [`reference/undo.md`](reference/undo.md) reverses every single thing below, and it is worth two minutes now.

✂ ---------- copy below this line ----------

I am new to Claude Code and I am using the desktop app, not the terminal. I have signed in, I am in the Code tab, and I have selected my project folder. Inside it is a folder called `starter-kit`.

Work through the steps below **in order**, and **stop after each numbered step** to show me what you did and what proof you have that it worked. Do not run several and then summarise. I want to see each one land.

Ground rules for this whole setup:

- Explain what each step does in plain words **before** you do it, in a sentence or two, the way you would to a smart friend who does not code. No jargon without explaining it in the same sentence.
- Never tell me something worked because you expect it to. Run a check, show me the result, tell me what I should be seeing.
- If a step fails, stop and tell me. Do not work around it silently and do not move on.
- Some steps below are mine to click, not yours to run. When you reach one, hand it to me clearly and wait.
- If anything in these instructions turns out to be wrong on my machine, say so plainly rather than making it fit.

**Step 1. Show me where I am and what you can reach.**
Tell me which folder you are working in and list what is in it. Then explain in two sentences how your access actually works: that you can see this folder, that you will ask before touching anything outside it, and that you are about to ask exactly that in Step 3 when you write into my settings folder. I would rather understand the real boundary than be told a comforting version of it.

**Step 2. Create my project instructions file.**
Copy `starter-kit/templates/CLAUDE.md` to `CLAUDE.md` in my project folder. Then interview me to fill it in: what this project is, who it is for, what it is built with if anything, and how I want you to work with me. Ask one question at a time, do not dump a list. Keep the finished file under one page.
Explain that you read this file at the start of every conversation about this project, which is why it has to stay short and true.

**Step 3. Install the rules.**
Copy every **numbered** `.md` file from `starter-kit/rules/` into `~/.claude/rules/`, creating that folder if it does not exist. Do not copy `rules/README.md`, which explains the set rather than being part of it. Then copy `starter-kit/commands/learn.md` into `~/.claude/commands/`.
Verify by listing both folders and showing me the count. There should be 18 rules.
Then tell me honestly that nothing visible changes after this. These files load silently into every conversation from now on, in every project, and they work the same whether I use the app or the terminal. Show me the 18 titles so I know what I agreed to, and tell me `starter-kit/rules/README.md` says which to read first.

**Step 4. Hand me the plugin install, because it is mine to click.**
Tell me to click the **+** button next to the prompt box and choose **Plugins**, then wait for me.

Walk me through it while I look: I want the `product-management` plugin from Anthropic's knowledge-work set. Tell me what it adds in one line before I install it.

Then show me what else is in that set and let me choose one or two more, so I end up with two or three in total. Ones that likely fit someone running her own business and building her own apps: `small-business`, `marketing`, `brand-voice`, `design`, `data`, `operations`, `engineering`. Explain each in one line. **Do not tell me to install them all.**

When I say I am done, verify what actually got installed and show me. If a plugin I picked is not there, say so rather than assuming it worked.

**Step 5. Tell me what came with it.**
Tell me the product-management plugin also brought sixteen connections to tools like Slack, Gmail, Google Calendar, Notion, Linear, Jira and Figma, that I turn one on by typing `/mcp`, and that `starter-kit/reference/connectors.md` explains what is there and what to be careful about. Do not connect any of them now.

**Step 6. Prove it works on something real.**
Ask me what I am actually working on this week. Then use the product-management plugin to produce a real first draft of it: a spec, a competitive brief, a research synthesis, whatever fits. Not a demo, the real thing.
This step matters more than the five before it. If I do not see something useful today I will not come back tomorrow.

**Step 7. Set up the notebook that survives between conversations.**
Every new conversation starts knowing nothing about the last one. Fix that now, before it costs me a Monday morning.
Create `.claude/wiki/` in my project and copy `_hot.md` and `_log.md` into it from `starter-kit/templates/`. Then add the block from `starter-kit/templates/CLAUDE-wiki-snippet.md` to the bottom of my `CLAUDE.md` so you actually read them.
Show me what to say at the end of a working session to keep them current.

**Step 8. Walk me through undoing all of it.**
Read `starter-kit/reference/undo.md` and walk me through it, checking each item against what you actually did in this session. Tell me if anything in it does not match what the desktop app does. I want to know the way out before I go further.

**Step 9. Tell me what you did NOT install and why.**
Read `starter-kit/GROWTH.md` and summarise it: what is deliberately missing, and the specific moment that should bring me back for each one. **Do not install any of it now.**

Then stop. I have enough for today.

✂ ---------- copy above this line ----------

---

## What you should have at the end

A project folder Claude works in. A `CLAUDE.md` it reads every time. Eighteen rules loaded into every conversation. Two or three plugins that do your actual job, plus sixteen tool connections waiting whenever you want them. A notebook that survives between conversations. One real piece of work already finished.

Everything else waits until you feel the problem it solves, and [GROWTH.md](GROWTH.md) names those moments.

## If something went wrong

**The Code tab shows an error about Git.** Most Macs have Git already, but not all. Open Terminal from your Applications folder, type `xcode-select --install`, press Return, and click Install when the system window appears. It is about a gigabyte. That window is normal and you have not broken anything. This is the only step in this whole guide that touches a terminal, and most people never hit it.

**A step in Part 2 failed.** Tell Claude exactly what you saw, including the error text, and ask it to explain the error before fixing it. Understanding the failure is worth more on day one than getting past it.

<details>
<summary>⌨️ <b>If you would rather use the terminal version</b></summary>

<br>

The desktop app and the terminal version are the same Claude Code and share the same configuration, so everything in this kit works either way. The rules, the `CLAUDE.md`, the templates and the notebook are identical. Only the setup differs.

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
