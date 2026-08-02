# Start here

You have used Claude in a browser. Claude Code is the same Claude running on your own computer, able to read and change the files in one folder you choose. That is the whole difference and it is a big one: it hands you a finished spreadsheet instead of describing one, and it can remember your project between conversations if you set it up to.

**Part 1 you do by hand and it takes about fifteen minutes.** Then you paste a brief into Claude Code and it sets itself up while you watch, stopping after each step to show you it worked.

Three things before you start.

**You need a paid Claude plan.** Pro, Max, Team, Enterprise, or a Console account. The free plan does not include Claude Code, and this is the most common way day one stops dead.

**You need macOS 13 or later.** Apple menu, then About This Mac.

**You do not need Node.js, npm, or Homebrew.** Some guides say otherwise; they describe an older install path. You do need one developer tool called git, and step 1.4 installs it for you.

---

# Part 1: by hand

## 1.1 Get this kit onto your computer

Do this first, in your browser, because everything in Part 2 reads from it.

**If you are reading this on GitHub:** click the green **Code** button near the top, choose **Download ZIP**, then double-click the downloaded file to unzip it. It lands in your Downloads folder.

**If someone sent you the folder directly:** put it in your Downloads folder and skip ahead.

One thing that will look wrong and is not: a folder downloaded from GitHub arrives with `-main` on the end of its name, so you get `claude-code-starter-kit-main`. That is normal. Step 1.5 renames it.

## 1.2 Open Terminal

Press `Cmd` and `Space` together, type `terminal`, press Return. A window opens with some text and a blinking cursor.

That window takes instructions one line at a time. You will paste six lines into it today and then mostly never come back.

Four things worth knowing, because they are what confuses everyone at first:

- **`~` means your home folder.** So `~/Documents/my-project` means a folder called `Documents` in your home folder, with `my-project` inside it.
- **A name starting with a dot is hidden.** Finder does not show `.claude` by default. Press `Cmd` `Shift` `.` in any Finder window to show hidden files, and again to hide them.
- **Silence means it worked.** This is the big one. Most commands print nothing when they succeed and just give you a fresh prompt back. An empty screen is success. Commands complain when they fail, not when they work.
- **A line starting with `/` is different.** Those get typed *inside Claude Code*, not into Terminal. Everything else on this page goes into Terminal. Getting these two mixed up is the single most common way people get stuck, so the rest of this page always says which.

## 1.3 Install Claude Code

```bash
curl -fsSL https://claude.ai/install.sh | bash
```

This is the install Anthropic recommends for a Mac and it keeps itself updated from then on.

Then **quit Terminal completely and open it again.** The installer adds Claude Code to the list of programs your terminal knows about, and that list is only read when a window opens. Skipping this is the usual reason the next line says "command not found".

```bash
claude --version
```

You should see a version number followed by `(Claude Code)`.

## 1.4 Install git

```bash
xcode-select --install
```

**A system window will pop up asking to install developer tools. That window is normal. It is not an error and you have not broken anything.** Click Install. It is roughly a gigabyte and takes a few minutes.

If it instead says the tools are already installed, you are fine, carry on.

You need this because the plugins in Step 4 are downloaded using git, and without it that step fails partway through. Better to pay this cost now, deliberately, than to hit the popup mid-setup and think something went wrong.

```bash
git --version
```

You should see a version number.

## 1.5 Make your project folder and put the kit in it

```bash
mkdir -p ~/Documents/my-project
```

Use a real name for something you are actually working on rather than `my-project`.

Now move the kit inside it. Use the first line if you downloaded the ZIP from GitHub, the second if someone sent you a folder called `claude-code-starter-kit`:

```bash
mv ~/Downloads/claude-code-starter-kit-main ~/Documents/my-project/starter-kit
```

```bash
mv ~/Downloads/claude-code-starter-kit ~/Documents/my-project/starter-kit
```

Then go into the project folder:

```bash
cd ~/Documents/my-project
```

Check it all landed:

```bash
ls starter-kit
```

You should see `README.md`, `START-HERE.md`, `GROWTH.md`, `rules`, `commands`, `templates` and `reference`.

## 1.6 Start it and sign in

```bash
claude
```

A browser window opens asking you to log in. Sign in with the account your paid plan is on. The terminal then says `Login successful` and asks you to press Return. If the browser does not open, press `c` to copy the login link and paste it in yourself.

You are now in a conversation with Claude, inside that folder. Type `/help` to see what it can do, or `/usage` at any point to see how much of your plan you have used.

**If it will not log you in**, the usual cause is an old API key sitting in your environment, which quietly overrides your subscription. Quit Claude Code, run `unset ANTHROPIC_API_KEY`, and start `claude` again.

---

# Part 2: hand this to Claude Code

Two things to know before you paste.

**It will ask permission before it does anything.** Read what it asks. It will ask to read the `starter-kit` folder and to write into `~/.claude`, and both of those are expected. Say yes. If it ever asks to delete something you were not expecting, say no and ask it why.

**Know the way out before you go in.** [`reference/undo.md`](reference/undo.md) reverses every single thing below, and it is worth two minutes now. Almost all of it is deleting a file.

Copy everything between the two lines and paste it into Claude Code.

✂ ---------- copy below this line ----------

I am new to Claude Code. I have it installed, I am signed in, and I am in my project folder. The starter kit is in a folder called `starter-kit` inside this folder.

Work through the steps below **in order**, and **stop after each numbered step** to show me what you did and what proof you have that it worked. Do not run several and then summarise. I want to see each one land.

Ground rules for this whole setup:

- Explain what each step does in plain words **before** you do it, in a sentence or two, the way you would to a smart friend who does not code. No jargon without explaining it in the same sentence.
- Never tell me something worked because you expect it to. Run a check, show me the output, tell me what I should be seeing.
- If a step fails, stop and tell me. Do not work around it silently and do not move on.
- If anything in these instructions turns out to be wrong on my machine, say so plainly rather than making it fit.

**Step 1. Show me where I am and what you can reach.**
Tell me which folder you are working in and list what is in it. Then explain in two sentences how your access actually works: that you operate in the folder I started you in, that you will ask before touching anything outside it, and that you are about to ask exactly that in Step 3 when you write into my settings folder. I would rather understand the real boundary than be told a comforting version of it.

**Step 2. Create my project instructions file.**
Copy `starter-kit/templates/CLAUDE.md` to `CLAUDE.md` in my project folder. Then interview me to fill it in: what this project is, who it is for, what it is built with if anything, and how I want you to work with me. Ask one question at a time, do not dump a list. Keep the finished file under one page.
Explain that you read this file at the start of every conversation about this project, which is why it has to stay short and true.

**Step 3. Install the rules.**
Copy every **numbered** `.md` file from `starter-kit/rules/` into `~/.claude/rules/`, creating that folder if it does not exist. Do not copy `rules/README.md`, which explains the set rather than being part of it. Then copy `starter-kit/commands/learn.md` into `~/.claude/commands/`.
Verify by listing both folders and showing me the count. There should be 18 rules.
Then tell me honestly that nothing visible changes after this. These files load silently into every conversation from now on, in every project. Show me the 18 titles so I know what I just agreed to, and tell me `starter-kit/rules/README.md` says which to read first and in what order.

**Step 4a. Install the plugins that do product work.**
Anthropic publishes plugins built for people who do knowledge work rather than engineering. Run these in the terminal for me:

```
claude plugin marketplace add anthropics/knowledge-work-plugins
claude plugin install product-management@knowledge-work-plugins
```

Then show me what else is in that marketplace and let me choose. Ones that likely fit someone running her own business and building her own apps: `small-business`, `marketing`, `brand-voice`, `design`, `data`, `operations`, `engineering`. Explain each in one line. **Do not install them all.** Let me pick two or three.

Then stop and tell me to do Step 4b myself.

**Step 4b. This one is mine to type, not yours.**
Tell me to type `/reload-plugins` into Claude Code, and explain that a line starting with `/` is a Claude Code command, which is why you cannot run it for me. Wait until I say I have done it. Then run `claude plugin list` and show me the output so we both know it took.

Then tell me that the product-management plugin also brought twelve connections to tools like Slack, Notion, Linear, Jira and Figma, that I connect them by typing `/mcp`, and that `starter-kit/reference/connectors.md` explains which are there and what to be careful about. Do not connect any of them now.

**Step 5. Prove it works on something real.**
Ask me what I am actually working on this week. Then use the product-management plugin to produce a real first draft of it: a spec, a competitive brief, a research synthesis, whatever fits. Not a demo, the real thing.
This step matters more than the four before it. If I do not see something useful today I will not come back tomorrow.

**Step 6. Set up the notebook that survives between conversations.**
Every new conversation starts knowing nothing about the last one. Fix that now, before it costs me a Monday morning.
Create `.claude/wiki/` in my project and copy `_hot.md` and `_log.md` into it from `starter-kit/templates/`. Then add the block from `starter-kit/templates/CLAUDE-wiki-snippet.md` to the bottom of my `CLAUDE.md` so you actually read them.
Show me what to say at the end of a working session to keep them current.

**Step 7. Walk me through undoing all of it.**
Read `starter-kit/reference/undo.md` and walk me through it, checking each command against what you actually did in this session. Tell me if anything in it does not match. I want to know the way out before I go further, including how to stop you mid-task.

**Step 8. Tell me what you did NOT install and why.**
Read `starter-kit/GROWTH.md` and summarise it: what is deliberately missing, and the specific moment that should bring me back for each one. **Do not install any of it now.**

Then stop. I have enough for today.

✂ ---------- copy above this line ----------

---

## What you should have at the end

A project folder Claude works in. A `CLAUDE.md` it reads every time. Eighteen rules loaded into every conversation. Two or three plugins that do your actual job, plus twelve tool connections waiting whenever you want them. A notebook that survives between conversations. One real piece of work already finished.

Everything else waits until you feel the problem it solves, and [GROWTH.md](GROWTH.md) names those moments.

## If something went wrong

Run `claude doctor` in Terminal. It checks the install and reports what is broken.

If a step in Part 2 failed, tell Claude Code exactly what you saw including the error text, and ask it to explain the error before fixing it. Understanding the failure is worth more on day one than getting past it.
