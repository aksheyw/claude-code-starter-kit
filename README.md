<div align="center">

# 🚪 claude-code-starter-kit: day one with the Claude Code desktop app, for people who have never opened a terminal

### Every guide starts at a command line. This one starts with a download.

![requires the Claude desktop app](https://img.shields.io/badge/requires-Claude%20desktop%20app-D97757) ![needs a paid plan](https://img.shields.io/badge/needs-a%20paid%20plan-B42318) ![day one is clicking not commands](https://img.shields.io/badge/day%20one-clicking%2C%20not%20commands-0E9384) ![18 rules, 9 on day one](https://img.shields.io/badge/rules-18%2C%209%20on%20day%20one-1B2A4A) ![MIT license](https://img.shields.io/badge/license-MIT-green)

</div>

---

<img src="docs/without-a-door-vs-day-one.svg" width="100%"
     alt="Without a front door, a newcomer meets eight separate Claude Code repos with no order and no starting point, installs all eight, understands none of them, and stops trusting the setup. With this kit, day one is ten minutes of clicking to install the Claude desktop app and pick one project folder where every change is shown before it happens, then nine guided steps in which Claude sets itself up: a CLAUDE.md, eighteen rules, two or three plugins bringing sixteen tool connections, and one real piece of work finished. Everything else stays locked behind a trigger, a specific moment that tells you when to add it, described in GROWTH.md.">

Claude Code is Anthropic's assistant with access to the files in one folder you choose, so it hands you a finished document rather than describing one. Almost every guide describes the version that runs in a terminal. This one uses the desktop app, which is the same Claude Code with a normal Mac interface, and the docs put it plainly: no terminal required.

This is the door. Ten minutes of clicking, then nine guided steps, ending in something you actually needed.

## Two files, and you only read one today

**[START-HERE.md](START-HERE.md)** is the whole day-one path. Fifteen minutes by hand, then you paste a brief into Claude Code and it sets itself up while you watch, stopping after each step to show you proof it worked.

**[GROWTH.md](GROWTH.md)** is everything left out, each item behind the moment that earns it. Read it once. Install none of it.

## Why almost nothing is on the day-one list

A tool installed before you have its problem is friction with no payoff. Install all eight and you get a setup you stop trusting, because half of it does things you never asked for and cannot explain.

So the test for day one is strict: you feel the value the same afternoon, it needs no engineering knowledge, and it cannot fail silently.

**Six things pass:** the app itself, one project folder, a `CLAUDE.md` it reads every time, eighteen rules of which nine apply from day one, two or three plugins, and one real piece of work finished.

Most things fail. Secret scanning, which checks you have not pasted a password into a file where it can leak, waits until the first time an app you are building needs a paid key. Version control, quality gates, review councils and backups wait too, and [GROWTH.md](GROWTH.md) names the moment that earns each one.

<details>
<summary>📦 <b>What is in here</b>, and where the depth went</summary>

<br>

| Path | What it is |
|---|---|
| [`START-HERE.md`](START-HERE.md) | The day-one path. Part 1 by hand, Part 2 pasted into Claude Code. |
| [`GROWTH.md`](GROWTH.md) | The growth menu. Every item behind a trigger, plus what to deliberately skip. |
| [`rules/`](rules) | 18 rules that load into every session, plus an index with the reading order. |
| [`commands/learn.md`](commands/learn.md) | `/learn`: turn a correction into a rule you never have to give twice. |
| [`templates/`](templates) | A `CLAUDE.md` skeleton, the two notebook files, and the lines that make them get read. |
| [`reference/undo.md`](reference/undo.md) | How to reverse everything here. Worth reading before you start, not after. |
| [`reference/connectors.md`](reference/connectors.md) | The sixteen tool connections that arrive on day one, and how to switch one on. |

A few install commands in `GROWTH.md` differ from the repo they point at. Each says so in place, with the date it was checked and the reason. They were run on a Mac before being written down. If a repo has since fixed its own instructions, follow the repo.

</details>

## The one habit the rest of it is downstream of

When you correct Claude on something, write the correction down so you never have to give it twice.

You type `/learn`. It writes the correction into a lessons file, and points your project's `CLAUDE.md` at that file so it actually gets read next time. Both halves matter: a lesson nothing loads is a diary. Every rule in this repo started as one.

**The tools are the residue. The habit is the thing.** Your set will look different from this one within a couple of months, and that is the point, not drift.

## When to skip this

**You already run Claude Code daily.** You have made these calls already and yours fit you better. The repos below are the useful part for you.

**You are on the free Claude plan.** Claude Code needs Pro, Max, Team, Enterprise or a Console account, and nothing here works around that.

**You want maximum power today.** This is deliberately small, because the failure it is built against is installing all eight and being able to explain none of them.

## Where to go once you outgrow it

Each of these publishes one layer in depth. [GROWTH.md](GROWTH.md) says which to reach for and when.

- [claude-code-rules](https://github.com/aksheyw/claude-code-rules): the full rules layer
- [claude-code-pm-agents](https://github.com/aksheyw/claude-code-pm-agents): product-manager subagents, including a review council
- [claude-code-deep-review](https://github.com/aksheyw/claude-code-deep-review): a review method that runs several passes, a different angle each time
- [context-bridge](https://github.com/aksheyw/context-bridge): the fuller project notebook and a generated handoff prompt
- [claude-code-ship-gate](https://github.com/aksheyw/claude-code-ship-gate): checks that must pass before anything reaches your live branch
- [claude-code-guardrail-hooks](https://github.com/aksheyw/claude-code-guardrail-hooks): checks that fire the moment a file is written
- [claude-code-learned-skills](https://github.com/aksheyw/claude-code-learned-skills): skills pulled out of real sessions
- [claude-code-harness-backup](https://github.com/aksheyw/claude-code-harness-backup): moving your setup to a new machine without losing what you wrote

## License

MIT. See [LICENSE](LICENSE).

---

Built by [Akshey Walia](https://github.com/aksheyw). If a step breaks on your machine, open an issue and say exactly what you saw, including the error text. A step that fails silently is a bug in this repo, not in you.
