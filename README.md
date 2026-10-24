<div align="center">

# 🚪 claude-code-starter-kit: finish something real in one evening, on a Mac, usually without opening a terminal

### You finish a real piece of your own work, and Claude still knows the project on Monday morning.

![requires the Claude desktop app](https://img.shields.io/badge/requires-Claude%20desktop%20app-D97757) ![needs a paid plan](https://img.shields.io/badge/needs-a%20paid%20plan-B42318) ![day one is clicking and pasting](https://img.shields.io/badge/day%20one-clicking%20and%20pasting-0E9384) ![never overwrites your files](https://img.shields.io/badge/never-overwrites%20your%20files-1B2A4A) ![MIT license](https://img.shields.io/badge/license-MIT-green)

</div>

---

<img src="docs/without-a-door-vs-day-one.svg" width="100%"
     alt="Two rows. Top row, without a front door: eight good Claude Code repos, each opening at a terminal command, with no order to read them in, so a newcomer installs all eight and understands none. Bottom row, with this kit: ten minutes of clicking to install the desktop app and choose a folder, then twelve guided steps that add an instructions file, up to eighteen rules, two or three plugins, one of which brings sixteen tool connections, up to twelve skills and a notebook, ending in one real piece of work. Everything else waits for a named moment, listed in GROWTH.md.">

Claude Code is Anthropic's assistant that works directly on the files in a folder you choose, so it hands you a finished document rather than describing one. By the end of the evening it will have drafted a piece of this week's work. Most guides start at a terminal, where you type commands. This one uses the Claude desktop app, which has Claude Code built in and lets you review changes without a terminal. Clicking takes about ten minutes, the whole setup about two hours.

## Two files, and you only read one today

**[START-HERE.md](START-HERE.md)** is the whole day-one path, and it is about two hours. Its second part stops after each step to show you proof that step worked, and its payoff step is Claude drafting a real piece of your own work and saving it into your folder. [`reference/example-first-draft.md`](reference/example-first-draft.md) is one it actually produced, so you can see the shape before you commit the evening.

**[GROWTH.md](GROWTH.md)** is almost everything left out, each item behind the moment that earns it. Read it once. Install none of it.

## Why the day-one list stops where it does

A tool installed before you have its problem is friction with no payoff. This kit is the front door to eight other GitHub repositories of mine, listed at the bottom. Install all eight on day one and you get a setup you stop trusting, because half of it does things you never asked for and cannot explain.

So the test for day one is strict: you feel the value the same day, it is something the author genuinely uses rather than something that sounded good, and you can check that it is working.

**Seven things pass.** If your machine already has some of them, you take only what is missing.

- **The app and one project folder:** the Claude desktop app, and the one folder Claude works in.
- **A `CLAUDE.md`:** the project's instructions file, which Claude reads at the start of every conversation.
- **Up to eighteen rules:** standing instructions Claude reads in every conversation, such as showing you proof before it says something worked. Nine apply from the first hour. The other nine each start by naming the later moment they are for, so you can ignore them until then.
- **Two or three plugins:** add-ons from Anthropic's catalogue, each for one kind of work: product management, plus one or two you choose. The product-management one also brings sixteen connections to tools like Slack, Notion and Jira.
- **Up to twelve skills:** written instructions Claude follows when a matching task comes up, such as planning work or finding a bug. Most are downloaded from the people who maintain them.
- **A notebook:** two short files in your folder where Claude writes down what you agreed, so the next conversation starts from there.
- **A real first draft** of this week's work, saved in your folder.

Most other tools fail that test. Secret scanning, which checks you have not pasted a password into a file where it can leak, waits until an app you are building needs a paid key. So do version control, which keeps every earlier version of your work so you can go back to one, and quality gates, which are checks that have to pass before your work goes live. [GROWTH.md](GROWTH.md) names the moment that earns each one.

## If you already use Claude Code, nothing here lands on top of yours

On an empty machine there is nothing of yours to collide with, but you are still shown every item and asked about every optional one.

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

You type `/learn`, a command this kit adds. It writes the correction into a lessons file, and points your project's `CLAUDE.md` at that file so it actually gets read next time. Both halves matter: a lesson nothing loads is a diary. Every rule in this repo started as one.

**The tools are the residue. The habit is the thing.** Your set will look different from this one within a couple of months, and that is the point, not drift.

## When to skip this

**You are on the free Claude plan.** Claude Code needs a paid plan (Pro, Max, Team or Enterprise), and nothing here works around that.

**You are not on a Mac.** The clicking path is the whole point and it is macOS only. The terminal version works anywhere, and this kit's rules, templates and skills work with it, but the first part of [START-HERE.md](START-HERE.md), the clicking, will not help you.

**You want every tool on day one.** This holds things back on purpose, because the failure it is built against is installing all eight and being able to explain none of them.

<details>
<summary>📄 <b>Credits</b>: six skills from Jesse Vincent's obra/superpowers, and Anthropic's own plugin catalogue</summary>

<br>

Other people's work is downloaded from the repository that maintains it, never copied in here, so you can pull newer versions the same way anyone else would.

- **[obra/superpowers](https://github.com/obra/superpowers)** by Jesse Vincent, MIT. Six of its fifteen skills are on the day-one list: brainstorming, writing plans, test-driven development, systematic debugging, requesting code review, and verification before completion.
- **Anthropic's Knowledge Work marketplace**, which ships with the Claude app and is where day one's plugins come from.

</details>

<details>
<summary>🔍 <b>Where to go once you outgrow it</b>: the eight repos this kit leads into, and which day one already used</summary>

<br>

Day one installs skills from two of these, `claude-code-deep-review` and `claude-code-learned-skills`. [GROWTH.md](GROWTH.md) says which of the rest to reach for and when.

- [claude-code-rules](https://github.com/aksheyw/claude-code-rules): the thirteen rules I run myself. The eighteen here were written for this kit
- [claude-code-learned-skills](https://github.com/aksheyw/claude-code-learned-skills): skills pulled out of real sessions. Three are on the day-one list
- [claude-code-deep-review](https://github.com/aksheyw/claude-code-deep-review): review in several passes, a different angle each time. One skill is on the day-one list
- [claude-code-pm-agents](https://github.com/aksheyw/claude-code-pm-agents): product-manager assistants, each with one job, including a council that reviews big decisions
- [context-bridge](https://github.com/aksheyw/context-bridge): the fuller notebook, and a handoff note for the next conversation
- [claude-code-ship-gate](https://github.com/aksheyw/claude-code-ship-gate): checks that must pass before your work goes live
- [claude-code-guardrail-hooks](https://github.com/aksheyw/claude-code-guardrail-hooks): checks that fire the moment a file is written
- [claude-code-harness-backup](https://github.com/aksheyw/claude-code-harness-backup): moving your setup to a new machine intact

</details>

## License

MIT. See [LICENSE](LICENSE).

---

Built by [Akshey Walia](https://github.com/aksheyw). If a step breaks on your machine, open an issue and say exactly what you saw, including the error text. A step that fails silently is a bug in this repo, not in you.
