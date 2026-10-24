# What this kit adds, and where each piece comes from

This is the catalogue the setup reads in Step 2. It exists so you can see the whole offer in one place before any of it lands on your machine, and so Claude can compare it against what you already have.

**Nothing here replaces anything of yours.** Where a piece of this overlaps with something you already run, the setup shows you both and asks you to choose. Where you have nothing, it is a straight addition.

**Everything here is either written by the author of this kit or downloaded from the repository that maintains it.** Nothing that belongs to somebody else is copied into this repo. That means you can update those pieces later from their source, the same way the author does. The credits are at the bottom of the [README](../README.md).

---

## 1. Rules

**What a rule is.** A short instruction file that Claude reads at the start of every conversation, in every project, whether or not you mention it. Eighteen of them.

**Where they come from.** Written for this kit. They install into `~/.claude/rules/` with `starter-kit-` on the front of each filename, so they cannot land on top of a rule you already have and so they are unambiguous to remove later.

| Block | What it covers | When it starts mattering |
|---|---|---|
| 01 to 09 | Where a session stands, plain words, the project instructions file, stopping before anything expensive or hard to undo, stopping and getting back, asking for proof, not guessing, getting things out of the chat, banking corrections | Your first hour |
| 20 to 23 | Agreeing shape before drafting, writing so it lands, saving is not publishing, checking before someone else uses it | The first time something you made goes to somebody else |
| 30 to 34 | Agreeing the approach before code, asking for a failing test first, code that stays easy to change, delegating reading, pressure-testing expensive decisions | The first time you are building software rather than documents |

**What it overlaps with.** If you already keep rules in `~/.claude/rules/`, expect real overlap in the 01 to 09 block, because that block is about working habits everybody eventually writes down. Judge by what each file says, not by its name.

---

## 2. The project instructions file, and the notebook

**What they are.** `CLAUDE.md` is the one page Claude reads at the start of every conversation about a project. The notebook is two files, `_hot.md` for where things stand right now and `_log.md` for one entry per working session, plus a short block added to `CLAUDE.md` that makes them actually get read.

**Also installed, and easy to miss because they are small:**

| What | Where it goes | Why |
|---|---|---|
| `learn.md`, the `/learn` command | `~/.claude/commands/learn.md` | Turns a correction into a rule you never have to give twice. It keeps its exact filename, because Claude Code takes a command's name from the file, and a prefix would make it `/starter-kit-learn`. If you already have a `learn.md`, the setup stops and asks rather than touching it. |
| The four wiki commands, `/wiki-init`, `/wiki-ingest`, `/wiki-query` and `/wiki-lint` | `~/.claude/commands/` | Only if you take the `llm-wiki` skill, and from the same repository. They set up, add to, search and check the fuller project wiki. They keep their exact filenames for the same reason as `learn.md`, and if you already have one with the same name the setup stops and asks rather than touching it. |
| The list of what was installed | `~/.claude/starter-kit-manifest.md` | A dated record of every file added and where it came from, so removing things later is exact rather than guesswork. If it is already there from an earlier run, a new dated section is added and nothing existing is replaced. |
| An untouched copy of everything installed | `~/.claude/starter-kit-baseline/` | The rules, the commands, each skill folder, and the exact text of anything added to your `CLAUDE.md` or to a notebook you already kept, all exactly as they arrived and filed under the project it happened in. A copy already in there is never overwritten. Months later it is the only way to tell a change you made from a change the authors made, which is what stops you deleting your own improvements by mistake. |

**Where they come from.** Templates in this kit. They are skeletons, and the setup fills them in with your real answers rather than leaving you the placeholders.

**What it overlaps with.** If you already have a `CLAUDE.md`, the setup never replaces or rewrites it. It offers you the sections the template has that yours does not, one at a time, and adds only the ones you accept. If you already keep a notebook, it never rewrites it either. It shows you the lines it would add, as a diff, and adds them only if you say yes, and it writes down what it added so you can find it again later.

---

## 3. Skills bundled in this kit

**What a skill is.** A set of instructions Claude loads when a particular kind of job comes up, so it follows a worked method instead of improvising.

These two are the author's own writing, so they are in this repo rather than downloaded. They install from `starter-kit/skills/`, and both are MIT licensed under this repository's own [LICENSE](../LICENSE).

| Skill | What it does | Source | Licence |
|---|---|---|---|
| `sounding-board` | A thinking partner for the decisions that are really a test of judgement. It agrees what the problem is before proposing anything, does the reading itself instead of interviewing you, comes back with a view rather than a menu, argues against that view before committing to it, and tells you when you are wrong. | Bundled in this kit | MIT |
| `handoff-audit` | Reads what a previous conversation left behind as a list of claims rather than a briefing, and re-checks the ones today's work depends on. Also the discipline for writing a handoff the next conversation can audit. This is the one that stops a confident wrong note surviving for weeks. | Bundled in this kit | MIT |

**What it overlaps with.** If you already have a thinking-partner or review skill of your own, `sounding-board` is the one most likely to duplicate it. Read both and keep one.

---

## 4. Skills from the author's own public repositories

**What a skill is.** A set of instructions Claude loads when a particular kind of job comes up, so it follows a worked method instead of improvising.

These are downloaded rather than copied into this kit, so you can pull a newer version whenever you want one. All are MIT licensed.

| Skill | What it does | Repository |
|---|---|---|
| `deep-review` | Reviews something in several passes, a different angle each time, instead of one pass that sees what it saw the first time | [claude-code-deep-review](https://github.com/aksheyw/claude-code-deep-review) |
| `llm-wiki` | The fuller version of the notebook: a project wiki that compounds across sessions, with a check for contradictions. Comes with the four wiki commands listed above. The two-file notebook from Step 9 grows into this fuller wiki when you run `/wiki-init`, which adds the files it needs and leaves `_hot.md` and `_log.md` as they are | [claude-code-learned-skills](https://github.com/aksheyw/claude-code-learned-skills) |
| `doc-confluence` | Organises a project's documents so anything can be found in one or two hops, and scans for rot | [claude-code-learned-skills](https://github.com/aksheyw/claude-code-learned-skills) |
| `audit` | A pre-release sweep for the bug classes that repeat, before something goes in front of somebody who is not you | [claude-code-learned-skills](https://github.com/aksheyw/claude-code-learned-skills) |

**Not on the day-one list, and why:** `council-full`, from [claude-code-pm-agents](https://github.com/aksheyw/claude-code-pm-agents), puts several Claudes in different roles to argue a decision out. One run costs many times a normal request, which matters on a plan with usage limits, so it sits in [GROWTH.md](../GROWTH.md) instead. `context-bridge` overlaps with the notebook you set up in Step 9, and running two notebooks means neither gets trusted. `claude-code-ship-gate` and `claude-code-guardrail-hooks` are not plain skills, they install differently, and they are in [GROWTH.md](../GROWTH.md) behind the moment that earns them. `claude-code-rules` holds the author's own thirteen rules. The eighteen here were written for this kit.

---

## 5. Skills from other people's public repositories

Downloaded from the repository that maintains them. Not copied into this kit, because they are not this kit's to redistribute.

| Skill | What it does | Repository | Author | Licence |
|---|---|---|---|---|
| `brainstorming` | Forces the shape of a thing to be agreed before anyone starts building it | [obra/superpowers](https://github.com/obra/superpowers) | Jesse Vincent | MIT |
| `writing-plans` | Turns an agreed design into a step-by-step plan before any work starts; brainstorming hands off to it | [obra/superpowers](https://github.com/obra/superpowers) | Jesse Vincent | MIT |
| `test-driven-development` | Write the failing check first, then the code that makes it pass | [obra/superpowers](https://github.com/obra/superpowers) | Jesse Vincent | MIT |
| `systematic-debugging` | A method for finding out why something broke, instead of guessing at fixes | [obra/superpowers](https://github.com/obra/superpowers) | Jesse Vincent | MIT |
| `requesting-code-review` | How to ask for a review that finds things, rather than one that agrees with you. It works from version control, so it earns its place once you have turned that on in week two ([GROWTH.md](../GROWTH.md)) | [obra/superpowers](https://github.com/obra/superpowers) | Jesse Vincent | MIT |
| `verification-before-completion` | Run the check and read the output before saying something is done | [obra/superpowers](https://github.com/obra/superpowers) | Jesse Vincent | MIT |

The `obra/superpowers` repository holds fifteen skills, checked 2026-10-24. The six above are the ones this kit installs, because they are the ones with real use behind them. You can install the rest yourself from the same repository whenever you want them.

**A note on where these live.** There is also an `obra/superpowers-marketplace` repository. That one is an index that points at this one; the skills themselves are in `obra/superpowers`. If you go looking, go to the second.

---

## 6. Plugins

**What a plugin is.** A bundle that adds skills and tool connections together. Anthropic ships a catalogue of them, called the Knowledge Work marketplace, which is added to your app by default.

The setup has you look at that catalogue and install two or three, starting with **Product Management**, which Step 8 reaches for first when it fits the job you bring it. Nothing is installed from anywhere except Anthropic's own catalogue on day one.

**What it overlaps with.** If you already have plugins installed, the setup asks you to read out what your screen says rather than assuming. Installing something twice is the failure here, and it is avoidable by looking first.

---

## How to judge an overlap

The setup will bring you choices. These are the questions worth asking about each one.

**Does the new one actually do something different, or does it just say it differently?** Two files can cover the same ground in different words. If they do, keep yours. You wrote it for a reason and it fits you.

**Is one a superset of the other?** If the kit's version says everything yours says and more, taking it costs you nothing. If yours says something the kit's does not, that sentence is the part worth keeping, and combining is usually better than choosing.

**Would having both be worse than having either?** Two notebooks means neither is trusted. Two rules that disagree means Claude follows whichever it read last. When two things genuinely conflict rather than merely overlap, pick one.

**When in doubt, keep yours and skip the kit's.** You can always add it later. Nothing else in this kit depends on any single rule being present.
