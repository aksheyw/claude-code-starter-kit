# What to add, and when

Nothing here is on day one. Every item is behind a **trigger**: a specific moment you will recognise when it happens. That is deliberate. A tool installed before you have its problem is friction with no payoff, and the usual result is a setup you stop trusting because half of it does things you never asked for.

Read this once so you know what exists. Then come back when something on this page describes your week.

Roughly in the order the triggers tend to arrive.

---

## Week two

### Turn version control on for your project

**Trigger.** You ask for one small change, Claude edits four files, and you realise you have no way back to how things were ten minutes ago.

Version control keeps a history of your project so you can always return to a working state. Most of the rest of this page assumes it.

Most Macs already have the tool it needs, called Git, so this is usually nothing to install. If Claude tells you Git is missing, open Terminal from your Applications folder, type `xcode-select --install`, and click Install when the system window appears. That window is normal and you have not broken anything.

Ask Claude Code:

> Set up version control in this project and explain each step as you go. Then show me how to get back to how things were an hour ago, and let me actually try it on a file we do not care about.

The trying-it part is the point. An undo you have never run is not an undo you trust, and until you trust it you will keep working timidly.

One thing to settle at the same time, before it matters: ask it to create a `.gitignore` and explain what goes in it. That file lists what never gets uploaded, and getting it right now is far cheaper than getting it wrong later. See the secret-scanning section below for why.

---

### A second opinion on plans, not just code

**Trigger.** Claude tells you something is done, with complete confidence, you believe it, and something obvious breaks an hour later.

The problem is structural, not a Claude flaw: the thing that wrote the plan is the worst judge of it. It already believes the plan. Anything it missed while writing, it misses again while checking.

Two ways to fix it, and the cheap one is enough at first.

**The cheap one.** Ask for the review in a way that forces a different stance, in a **new conversation** so it is not defending its own work:

> Here is a plan. Do not improve it. Try to find the reason it fails. What is the one assumption it rests on, and what happens if that assumption is wrong?

**The structured one.** A published review method that runs several passes with a different angle each time, rather than one pass that sees what it saw the first time:

```bash
cd ~/Desktop
git clone https://github.com/aksheyw/claude-code-deep-review.git
cd claude-code-deep-review
mkdir -p ~/.claude/skills/deep-review ~/.claude/rules
cp SKILL.md ~/.claude/skills/deep-review/SKILL.md
cp rule.md  ~/.claude/rules/deep-review.md
```

```bash
ls ~/.claude/skills/deep-review/
```

Should print `SKILL.md`. Restart Claude Code, type `/deep-review`, check it completes.

> **These commands differ from that repo's README, checked 2026-08-01.** The README puts `SKILL.md` in as a loose file, and a skill has to be a folder containing `SKILL.md`. It also has no `mkdir`, so it fails on a machine where `~/.claude/rules/` does not exist yet, which is every new machine. If the README has since been fixed, follow it instead of this.

**The most expensive version** is running your plan past a genuinely different AI model, from a different company, because two models trained differently fail differently. Worth knowing about. Not worth paying for in week two.

---

### A notebook that survives between conversations

**Trigger.** The first Monday you sit down, say "let's carry on with the pricing page", and Claude has no idea what the pricing page is or why you chose that payment provider on Thursday.

You already have the two-file version from day one (`_hot.md` and `_log.md`). If that habit has stuck and you want the fuller version, with a proper session-close routine and a generated handoff note you paste into the next conversation:

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

> Set up this project so secrets never get committed. Create a `.env` file for the keys, add it to `.gitignore`, and show me both files. Explain what each one does.

Second, a scan that runs automatically every time a file is written:

```bash
cd ~/Desktop
git clone https://github.com/aksheyw/claude-code-guardrail-hooks.git
cd claude-code-guardrail-hooks
mkdir -p ~/.claude/scripts/hooks
cp hooks/secret-scan-postwrite.sh ~/.claude/scripts/hooks/
```

**Copy only that one file.** The others in that repo are built around a different way of working. In particular, one of them blocks Claude whenever a message starts with a word like "wait", which is exactly how most people redirect mid-sentence, and it will look like the tool is broken.

Copying the script does not switch it on. Rather than hand-editing a settings file, say this to Claude Code:

> Back up `~/.claude/settings.json` first. Then add only the `secret-scan-postwrite.sh` hook, matcher `Write|Edit|MultiEdit`, using its full path. Show me the change before you make it.

Then restart, ask it to write a fake API key into a test file, and check you get a warning. **If nothing happens, it is not on.**

---

### A gate before anything goes live

**Trigger.** You say "push this to GitHub", it happens instantly, and you realise nothing stood between your laptop and a public repo.

Type these **inside Claude Code**, not in Terminal. Pasting them into Terminal gives you an error about no such file:

```
/plugin marketplace add aksheyw/claude-code-ship-gate
/plugin install ship-gate@ship-gate
```

Then `/reload-plugins`, and inside a project that is already under version control:

```
/ship-init
```

**Learn the way out before you need it: `/ship off` disables it for one project.**

---

### A check before someone who is not you uses it

**Trigger.** The week you first plan to put something in front of a customer, a friend, or an app store.

```bash
cd ~/Desktop
git clone https://github.com/aksheyw/claude-code-learned-skills.git
cd claude-code-learned-skills
mkdir -p ~/.claude/skills
cp -r skills/audit ~/.claude/skills/
```

```bash
ls ~/.claude/skills/audit/
```

Should print `SKILL.md`.

> **Take one skill, not all twelve, and note the command differs from that repo's README, checked 2026-08-01.** The README's version copies each folder's *contents* rather than the folders, so every file lands at the same path and overwrites the last. It exits successfully and prints nothing, so it looks like it worked. Nine of the other skills are about servers, containers and machine-learning data, which is not your problem.

---

### A backup of the parts you wrote

**Trigger.** You correct Claude on something and think "I have told you this before." Or you start thinking about a new laptop. Whichever comes first, and do not wait for the second.

Reinstalling Claude Code takes two minutes. The rules, the lessons and the project notebooks you built do not come back, because you are the only copy.

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
