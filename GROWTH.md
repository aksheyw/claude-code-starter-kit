# What to add, and when

Almost nothing here is on day one. Every item is behind a **trigger**: a specific moment you will recognise when it happens. Two of them, `deep-review` and `audit`, are **offered** on day one, and they are kept on this page because knowing *when* to reach for them is the part that matters. If you skipped them during setup, each section below says how to add it.

**One rule holds everywhere on this page, the same as during setup: nothing here replaces anything of yours.** Every prompt below tells Claude to check whether a file already exists and to bring you the choice rather than writing over it. If one of them ever does otherwise on your machine, that is a bug in this page. That is deliberate. A tool installed before you have its problem is friction with no payoff, and installing it early can leave you with a setup you do not trust, because half of it does things you never asked for.

Read this once so you know what exists. Then come back when something on this page describes your week.

Roughly in the order the triggers tend to arrive.

---

## Week two

### Turn version control on for your project

**Trigger.** You ask for one small change, Claude edits four files, and you realise you have no way back to how things were ten minutes ago.

Version control keeps a history of your project, so you can return to any state you saved. It only protects what you have saved into that history, so a file you never added, or an hour of work since your last save, is not in it. Most of the rest of this page assumes you have this turned on.

Most Macs already have the tool it needs, called Git, so this is usually nothing to install. If Claude tells you Git is missing, ask it to run `xcode-select --install` for you, and click **Install** when the macOS window appears. That window is normal and you have not broken anything.

Ask Claude Code:

> Set up version control in this project and explain each step as you go. Then show me how to get back to how things were an hour ago, and let me actually try it on a file we do not care about.

The trying-it part is the point. An undo you have never run is not an undo you trust, and until you trust it you will keep working timidly.

One thing to settle at the same time, before it matters: ask it to **check whether you already have a `.gitignore`, show you what is in it and propose additions as a diff if you do**, and to create one and explain it if you do not. That file lists what never gets uploaded, and getting it right now is far cheaper than getting it wrong later. See the secret-scanning section below for why.

---

### A second opinion on plans, not just code

**Trigger.** Claude tells you something is done, with complete confidence, you believe it, and something obvious breaks an hour later.

The problem is structural, not a Claude flaw: the thing that wrote the plan is the worst judge of it. It already believes the plan. Anything it missed while writing, it misses again while checking.

Two ways to fix it, and the cheap one is enough at first.

**The cheap one.** Ask for the review in a way that forces a different stance, in a **new conversation** so it is not defending its own work:

> Here is a plan. Do not improve it. Try to find the reason it fails. What is the one assumption it rests on, and what happens if that assumption is wrong?

**The structured one.** A review method that runs several passes with a different angle each time, rather than one pass that sees what it saw the first time. **If you accepted it during setup you already have it**, so type `/deep-review` and it runs. Start a new conversation first if it does not appear, because that is when new skills are picked up.

If you skipped it, or it is genuinely not there, say:

> Check whether `~/.claude/skills/deep-review/` exists. If it does, leave it alone and tell me what is in it. If it does not, download [claude-code-deep-review](https://github.com/aksheyw/claude-code-deep-review) into a temporary folder, copy the skill into `~/.claude/skills/deep-review/`, delete the download, and show me the `SKILL.md` is there.

**The rule that goes with it** lives in that same repository as `rule.md`, and it is never installed by default. It makes Claude reach for the review method on its own rather than waiting to be asked. Ask for it when you find yourself typing `/deep-review` every time and wishing you did not have to:

> Fetch `rule.md` from that repository. **Before saving it, check whether a rule of that name is already in `~/.claude/rules/`.** If one is, show me both and let me choose rather than replacing mine. If not, save it as `starter-kit-deep-review.md` and tell me it loads from my next conversation.

**The most expensive version** is running your plan past a genuinely different AI model, from a different company, because two models trained differently fail differently. Worth knowing about. Not worth paying for in week two.

---

### A notebook that survives between conversations

**Trigger.** The first Monday you sit down, say "let's carry on with the pricing page", and Claude has no idea what the pricing page is or why you chose that payment provider on Thursday.

You already have the two-file version from day one (`_hot.md` and `_log.md`). If that habit has stuck and you want the fuller version, with a proper session-close routine and a generated handoff note you paste into the next conversation:

**This one uses Terminal** (Applications, then Utilities). Open it and check first whether you have Node.js, a piece of software this tool needs:

```bash
node --version
```

If that says `command not found`, go to [nodejs.org](https://nodejs.org), download the macOS installer, double-click it. No terminal needed for that part.

```bash
npx skills add aksheyw/context-bridge --global
```

```bash
ls ~/.claude/skills/context-bridge/
```

Then restart Claude Code and type `/cb-` to see if the commands appear.

> **The `--global` flag is not in that repo's README, checked 2026-08-01.** Without it the skill installs into whichever folder your terminal happens to be sitting in, so next month's project silently will not have it.
>
> **If `/cb-` shows nothing, stop and do not debug it.** Keep using your two files. They give you most of the value, and a working habit beats a broken tool.

---

## Month two

### Stop a key reaching the internet

**Trigger.** Something you are building needs an API key (OpenAI, Stripe, anything you pay for) and Claude writes that key straight into a file to make it work.

This is the one thing on this page that is genuinely unrecoverable, and not for the reason people assume. History can be rewritten, and later on this page you will see the tools for it. **What cannot be undone is that somebody already has the key.** Automated scanners find published keys within minutes of a push, so by the time you notice, scrubbing the history changes nothing. The fix is always to cancel that key and get a new one.

Two things, in this order. First, ask Claude Code:

> Set up this project so secrets never get committed. **First check whether `.env` or `.gitignore` already exists.** If either does, show me what is in it and propose additions as a diff rather than writing a new one over it. If neither exists, create them, show me both, and explain what each one does.

Second, a scan that runs automatically every time a file is written. Ask Claude to do this rather than typing it yourself:

> Download `https://github.com/aksheyw/claude-code-guardrail-hooks` into a temporary folder. **Before you copy anything, check whether `~/.claude/scripts/hooks/secret-scan-postwrite.sh` already exists.** If it does, show me both versions and what differs, and wait for me to choose rather than replacing mine. If it does not, copy just that one file across, create the folder if needed, then delete the temporary download and tell me.

**Copy only that one file.** The others in that repo are built around a different way of working. In particular, one of them blocks Claude whenever a message starts with a word like "wait", which is a natural way to redirect mid-sentence, and it will look like the tool is broken.

Copying the script does not switch it on. Rather than hand-editing a settings file, say this to Claude Code:

> Back up `~/.claude/settings.json` first. Then add only the `secret-scan-postwrite.sh` hook, matcher `Write|Edit|MultiEdit`, using its full path. Show me the change before you make it.

Then restart, ask it to write a fake API key into a test file, and check you get a warning. **If nothing happens, it is not on.**

---

### A gate before anything goes live

**Trigger.** You say "push this to GitHub", it happens instantly, and you realise nothing stood between your laptop and a public repo.

This one is not in the set Anthropic installs by default, so you add where it comes from first, then install it.

**In the desktop app:** open **Customize** in the left sidebar, click the **Plugins** tab, and use **Add** to add a source from a GitHub address. The address is `aksheyw/claude-code-ship-gate`. Then use **Browse** on that same screen to install **ship-gate**.

**If you use the terminal version**, the same thing is two typed commands:

```
/plugin marketplace add aksheyw/claude-code-ship-gate
/plugin install ship-gate@ship-gate
```

Those two only work in the terminal version. Typed into the desktop app they come back with "not available in this environment", which is a limit of that surface rather than anything you did wrong.

Then `/reload-plugins`, and inside a project that is already under version control:

```
/ship-gate:ship-init
```

The `ship-gate:` prefix is not decoration. Installed this way the commands are namespaced, and that repo's own README says so. The shorter `/ship-init` only exists if you used its personal install script instead, which this page does not.

**Learn the way out before you need it: `/ship-gate:ship off` disables it for one project.**

---

### A check before someone who is not you uses it

**Trigger.** The week you first plan to put something in front of a customer, a friend, or an app store.

**If you accepted it during setup you already have this too**, so type `/audit` and it runs. If you skipped it, ask Claude to install it from [claude-code-learned-skills](https://github.com/aksheyw/claude-code-learned-skills) the same way, checking first that the folder is not already there. It sweeps for the kinds of bug that repeat: raw database values showing up in the interface, a form that fails silently, a permission left open.

The thing worth knowing is not how to install it. It is **when to run it**, which is before somebody who is not you touches the thing, not after they report something broken.

> **Its repository holds twelve skills and day one took three** (`audit`, `llm-wiki`, `doc-confluence`). Most of the rest are about servers, containers and machine-learning data, which is not your problem. Look at [claude-code-learned-skills](https://github.com/aksheyw/claude-code-learned-skills) yourself if you become curious, and ask Claude to install any one of them the same way Step 6 did.

---

### A backup of the parts you wrote

**Trigger.** You correct Claude on something and think "I have told you this before." Or you start thinking about a new laptop. Whichever comes first, and do not wait for the second.

Reinstalling Claude Code is quick. The rules, the lessons and the project notebooks you built do not come back, because you are the only copy.

**This one uses Terminal** (Applications, then Utilities):

```bash
cd ~/Desktop
git clone https://github.com/aksheyw/claude-code-harness-backup.git
bash claude-code-harness-backup/scripts/capture-harness.sh
```

It prints a warning that it is about to copy real passwords in plain text, then **stops and waits for you to press Return.** That frozen screen is expected, not a crash.

**The folder it produces holds real credentials. Never put it in a public repo.**

---

## Deliberately not here

Not because these are bad. Because they solve problems you do not have, and each one makes your setup harder to trust.

| Thing | Why not |
|---|---|
| **The rest of the guardrail hooks** | One blocks Claude when a message opens with "wait", which is how you will naturally redirect it. Another guards code-formatting config files you do not have yet. |
| **A nine-seat review council** | A full run costs many times a normal request, which matters on a plan with usage limits, and it doubles your menu of assistants with names you cannot tell apart. |
| **Test-coverage and code-style rules** | They make Claude refuse to agree your app is finished until it hits targets that do not apply to a first small project. You will experience it as Claude being obstinate and never connect it to a file you copied. |
| **A second project notebook system** | Two notebooks in one project means neither is trusted and both go stale. Pick one and stay with it. |
| **Job-search tooling** | Built for someone applying for roles. One version loads a personal profile into every conversation in every project, which is a privacy surface, not a feature. |
| **The community plugin marketplace** | It listed 2,307 plugins when this was checked on 2026-08-01, against 276 in Anthropic's own. Anthropic states plainly that plugins run code on your machine with your privileges and that it cannot verify what they do. Install from there only when you have a specific need and have looked at the source. |

---

## One habit worth more than any of it

When you correct Claude on something, write the correction down so you never give it twice. That is what `/learn` is for, and it is in your day-one set.

Everything on this page came from somebody doing that repeatedly. The tools are the residue. The habit is the thing.
