<div align="center">

# 🚪 claude-code-starter-kit: finish something real in one evening, on a Mac, usually without opening a terminal

### You finish a real piece of your own work, and Claude still knows the project on Monday morning.

![requires the Claude desktop app](https://img.shields.io/badge/requires-Claude%20desktop%20app-D97757) ![needs a paid plan](https://img.shields.io/badge/needs-a%20paid%20plan-B42318) ![day one is clicking and pasting](https://img.shields.io/badge/day%20one-clicking%20and%20pasting-0E9384) ![never overwrites your files](https://img.shields.io/badge/never-overwrites%20your%20files-1B2A4A) ![MIT license](https://img.shields.io/badge/license-MIT-green)

</div>

---

<img src="docs/without-a-door-vs-day-one.svg" width="100%"
     alt="Without a front door, a newcomer meets eight separate Claude Code repos with no order and no starting point, installs all eight, understands none of them, and stops trusting the setup. With this kit, day one is ten minutes of clicking to install the Claude desktop app and pick one project folder where every edit is proposed for you to accept, then twelve guided steps in which Claude sets itself up: it offers a CLAUDE.md, eighteen rules, two or three plugins bringing sixteen tool connections, twelve skills, most of them downloaded from the repositories that maintain them, and a notebook that carries what you agreed into the next conversation, installing only what you accept, and finishes one real piece of work. Nothing already on the machine is replaced, and edits are proposed for you to accept before they happen. Everything else stays locked behind a trigger, a specific moment that tells you when to add it, described in GROWTH.md.">

Claude Code is Anthropic's assistant with access to the files in one folder you choose, so it hands you a finished document rather than describing one. By the end of the evening it will have drafted whatever you are working on this week, and it will still know the project next time you open it. Almost every guide starts at a terminal. This one uses the desktop app, which Anthropic's docs say works without a terminal. The clicking part is about ten minutes.

## Two files, and you only read one today

**[START-HERE.md](START-HERE.md)** is the whole day-one path, and it is about two hours. It stops after each step to show you proof that step worked, and its payoff step is Claude drafting a real piece of your own work and saving it into your folder. [`reference/example-first-draft.md`](reference/example-first-draft.md) is one it actually produced, so you can see the shape before you commit the evening.

**[GROWTH.md](GROWTH.md)** is everything left out, each item behind the moment that earns it. Read it once. Install none of it.

## Why the day-one list stops where it does

A tool installed before you have its problem is friction with no payoff. Install all eight of the repos this kit sits in front of and you get a setup you stop trusting, because half of it does things you never asked for and cannot explain.

So the test for day one is strict: you feel the value the same afternoon, it is something the author genuinely uses rather than something that sounded good, and it cannot fail silently.

**Seven things pass**, and on a machine that already has some of them you take only what you are missing: the app and one project folder, a `CLAUDE.md` it reads every time, up to eighteen rules of which nine apply from day one, two or three plugins bringing sixteen tool connections, up to twelve skills, a notebook that carries what you agreed into the next conversation, and one real piece of work finished.

Most things fail. Secret scanning, which checks you have not pasted a password into a file where it can leak, waits until an app you are building needs a paid key. So do version control, which keeps every earlier version of your work so you can go back to one, and quality gates, which are checks that have to pass before your work goes live. [GROWTH.md](GROWTH.md) names the moment that earns each one.

## If you already use Claude Code, nothing here lands on top of yours

If you are starting from an empty machine there is nothing of yours for any of it to collide with. You are still shown every item, and asked about every optional one.

The setup **looks first**, then shows you three lists: where it fills a gap, where it overlaps with something of yours, and where what you have is already better. For each overlap it says what both versions do, what you gain and lose either way, and which it would pick and why. Then it waits. You decide.

Nothing is renamed, moved or copied over. Three files of yours can gain lines, and only if you say yes to the exact lines first: your `CLAUDE.md`, and either of the two notebook files if you already keep them. Those are only ever added to, never rewritten. Its rules install with a `starter-kit-` prefix so they cannot collide with yours, and everything it adds goes on a list you can read at any time. The full catalogue is [`reference/what-this-adds.md`](reference/what-this-adds.md), readable before you install a thing, and [`reference/undo.md`](reference/undo.md) is the way back out, worth reading before you start rather than after.

<details>
<summary>📦 <b>What is in here</b>, and where the depth went</summary>

<br>

| Path | What it is |
|---|---|
| [`START-HERE.md`](START-HERE.md) | The day-one path. Part 1 by hand, Part 2 pasted into Claude Code. |
| [`GROWTH.md`](GROWTH.md) | The growth menu. Every item behind a trigger, plus what to deliberately skip. |
| [`reference/what-this-adds.md`](reference/what-this-adds.md) | The full catalogue: every rule, skill and template, where each comes from, and how to judge an overlap with something you already have. |
| [`rules/`](rules) | 18 rules that load into every session, plus an index with the reading order. |
| [`skills/`](skills) | The two skills written for this kit. The other ten are downloaded from the repositories that maintain them. |
| [`commands/learn.md`](commands/learn.md) | `/learn`: turn a correction into a rule you never have to give twice. |
| [`templates/`](templates) | A `CLAUDE.md` skeleton, the two notebook files, and the lines that make them get read. |
| [`reference/undo.md`](reference/undo.md) | What was added, where it went, and how to take out the parts you no longer want. |
| [`reference/connectors.md`](reference/connectors.md) | The sixteen tool connections that arrive on day one, and how to switch one on. |

One install note in `GROWTH.md` differs from the repo it points at, and says so in place with the date it was checked and the reason. It was run on a Mac before being written down. If that repo has since fixed its own instructions, follow the repo.

</details>

## The one habit the rest of it is downstream of

When you correct Claude on something, write the correction down so you never have to give it twice.

You type `/learn`. It writes the correction into a lessons file, and points your project's `CLAUDE.md` at that file so it actually gets read next time. Both halves matter: a lesson nothing loads is a diary. Every rule in this repo started as one.

**The tools are the residue. The habit is the thing.** Your set will look different from this one within a couple of months, and that is the point, not drift.

## When to skip this

**You are on the free Claude plan.** Claude Code needs Pro, Max, Team or Enterprise, and nothing here works around that.

**You are not on a Mac.** The clicking path is the whole point and it is macOS only. The terminal version works anywhere, and this kit's rules, templates and skills work with it, but Part 1 will not help you.

**You want every tool on day one.** This holds things back on purpose, because the failure it is built against is installing all eight and being able to explain none of them.

<details>
<summary>📄 <b>Credits</b>: six skills from Jesse Vincent's obra/superpowers, and Anthropic's own plugin catalogue</summary>

<br>

Other people's work is downloaded from the repository that maintains it, never copied in here, so you can pull newer versions the same way anyone else would.

- **[obra/superpowers](https://github.com/obra/superpowers)** by Jesse Vincent, MIT. Six of its fifteen skills are on the day-one list: brainstorming, writing plans, test-driven development, systematic debugging, requesting code review, and verification before completion.
- **Anthropic's Knowledge Work marketplace**, which ships with the Claude app and is where day one's plugins come from.

</details>

<details>
<summary>🔍 <b>Where to go once you outgrow it</b>: the eight layer repos, and which day one already used</summary>

<br>

Day one installs skills from two of these, `claude-code-deep-review` and `claude-code-learned-skills`. [GROWTH.md](GROWTH.md) says which of the rest to reach for and when.

- [claude-code-rules](https://github.com/aksheyw/claude-code-rules): the full rules layer. The eighteen here are its day-one subset
- [claude-code-learned-skills](https://github.com/aksheyw/claude-code-learned-skills): skills pulled out of real sessions. Three are on the day-one list
- [claude-code-deep-review](https://github.com/aksheyw/claude-code-deep-review): review in several passes, a different angle each time
- [claude-code-pm-agents](https://github.com/aksheyw/claude-code-pm-agents): product-manager subagents, including the review council
- [context-bridge](https://github.com/aksheyw/context-bridge): the fuller notebook, and a handoff note for the next conversation
- [claude-code-ship-gate](https://github.com/aksheyw/claude-code-ship-gate): checks that must pass before anything reaches your live branch
- [claude-code-guardrail-hooks](https://github.com/aksheyw/claude-code-guardrail-hooks): checks that fire the moment a file is written
- [claude-code-harness-backup](https://github.com/aksheyw/claude-code-harness-backup): moving your setup to a new machine intact

</details>

## License

MIT. See [LICENSE](LICENSE).

---

Built by [Akshey Walia](https://github.com/aksheyw). If a step breaks on your machine, open an issue and say exactly what you saw, including the error text. A step that fails silently is a bug in this repo, not in you.
