<div align="center">

# 🚪 Claude Code, day one: a starting setup that fits in one afternoon

### Every guide assumes you already know what to install. This one assumes you have never opened a terminal.

![requires](https://img.shields.io/badge/requires-Claude%20Code-D97757) ![plan](https://img.shields.io/badge/needs-a%20paid%20plan-B42318) ![day%20one](https://img.shields.io/badge/day%20one-one%20afternoon-0E9384) ![audience](https://img.shields.io/badge/written%20for-non--engineers-1B2A4A) ![license](https://img.shields.io/badge/license-MIT-green)

</div>

---

Claude Code is Anthropic's assistant running on your own computer instead of in a browser tab. It reads and changes the files in one folder you choose, so it can hand you a finished spreadsheet rather than describing one.

The tooling around it is excellent and almost all of it is written for people who already use it. Guides open at `git clone` without saying to open Terminal first, and the good pieces are published one layer at a time with nothing saying which to install, in what order, or what to leave alone. So a new user picks up a power user's mature setup, installs eleven things, understands none of them, and stops trusting the whole arrangement.

This is the front door. **One afternoon, no Node, no Homebrew, and something real finished by the end of it.**

Day one installs exactly one developer tool, git, because the plugin step downloads with it. The guide warns you about the system popup before it appears, which is the part nobody usually does.

## Start here

**[START-HERE.md](START-HERE.md)** is the whole day-one path. Ten minutes by hand to get Claude Code running, then you paste a brief into it and it sets itself up while you watch, stopping after each step to show you proof it worked.

**[GROWTH.md](GROWTH.md)** is everything deliberately left out, each item behind the specific moment that should make you come back for it. Read it once so you know what exists. Do not install any of it yet.

## What day one actually gets you

<details>
<summary><b>The six things, and why each one is on the list</b></summary>

<br>

| | Why it is day one |
|---|---|
| **Claude Code installed and signed in** | One command. The installer Anthropic recommends for a Mac keeps itself updated and needs no developer tools. |
| **A project folder it cannot see outside of** | This is the thing that makes everything else safe to try. Claude Code works in the folder you start it from and nowhere else. |
| **A `CLAUDE.md` it reads every time** | The one page it opens at the start of every conversation about your project. Write it once, stop re-explaining your project every morning. |
| **Rules loaded into every session** | Working habits, not tools. Show evidence rather than confidence. Check the source before building on it. Recommend, then stop. |
| **Two or three plugins that do your actual job** | Specs, competitive briefs, research synthesis, roadmaps. Real work on the first afternoon, not a tutorial. |
| **A notebook that survives between conversations** | Every new conversation starts knowing nothing about the last one. Two small files fix it before it costs you a Monday. |

Not on the list, on purpose: version control, quality gates, secret scanning, review councils, backups. All of them are in [GROWTH.md](GROWTH.md) with the moment that earns each one.

</details>

<details>
<summary><b>What is in this repo</b></summary>

<br>

| Path | What it is |
|---|---|
| [`START-HERE.md`](START-HERE.md) | The day-one path. Part 1 by hand, Part 2 pasted into Claude Code. |
| [`GROWTH.md`](GROWTH.md) | The growth menu. Every item behind a trigger, plus what to deliberately skip. |
| [`rules/`](rules) | The rules that load into every session, plus their own README with the reading order. |
| [`commands/`](commands) | `/learn`, the one-keystroke way to turn a correction into a rule you never have to give twice. |
| [`templates/`](templates) | A `CLAUDE.md` skeleton, the two notebook files, and the lines that make them get read. |
| [`reference/undo.md`](reference/undo.md) | How to reverse every single thing in the kit. Worth reading before you start, not after. |
| [`reference/connectors.md`](reference/connectors.md) | The twelve tool connections that arrive with day one, and how to switch one on. |

</details>

## The one habit the rest of it is downstream of

When you correct Claude on something, write the correction down so you never have to give it twice. That is what `/learn` does, and it is the only thing here that compounds.

Every rule in this repo exists because somebody did that repeatedly and then noticed a pattern. **The tools are the residue. The habit is the thing.** Your set will look different from this one within a couple of months, and that is the intended outcome, not drift.

## Who this is not for

**Skip it if you already run Claude Code daily.** You have made these choices already and yours fit you better. The [companion repos](#companion-repos) below are the useful part for you.

**Skip it if you are on the free Claude plan.** Claude Code needs Pro, Max, Team, Enterprise or a Console account, and nothing here works around that.

**Skip it if you want maximum power on day one.** This is deliberately small. It leaves out most of what a heavy user runs, because the failure it is designed against is installing eleven things you cannot explain.

## Companion repos

Each publishes one layer in more depth. [GROWTH.md](GROWTH.md) says when to reach for which.

- [claude-code-rules](https://github.com/aksheyw/claude-code-rules): the full rules layer
- [claude-code-pm-agents](https://github.com/aksheyw/claude-code-pm-agents): product-manager subagents, including a review council
- [claude-code-deep-review](https://github.com/aksheyw/claude-code-deep-review): a review method that runs several passes with a different angle each time
- [context-bridge](https://github.com/aksheyw/context-bridge): the fuller project notebook and a generated handoff prompt
- [claude-code-ship-gate](https://github.com/aksheyw/claude-code-ship-gate): checks that must pass before anything reaches your live branch
- [claude-code-guardrail-hooks](https://github.com/aksheyw/claude-code-guardrail-hooks): checks that fire automatically at the moment a file is written
- [claude-code-learned-skills](https://github.com/aksheyw/claude-code-learned-skills): skills pulled out of real sessions
- [claude-code-harness-backup](https://github.com/aksheyw/claude-code-harness-backup): moving your setup to a new machine without losing what you wrote

## A note on the commands in GROWTH.md

A few install commands there differ from the ones in the repo they point at, and each says so in place, with the date it was checked and the reason. They were run on a Mac before being written down. If a repo has since fixed its own instructions, follow the repo.

## License

MIT. See [LICENSE](LICENSE).

---

Built by [Akshey Walia](https://github.com/aksheyw). If a step here breaks on your machine, open an issue and say exactly what you saw, including the error text. A step that fails silently is a bug in this repo, not in you.
