# The rules

Working habits, written as instructions to Claude Code. Each file is one rule: what it is, why it exists, and how it gets applied. Nothing about the interface changes when you add them.

**They load into every session.** Once installed they are read at the start of every conversation, in every project, whether or not you mention them. That is the point, and it is also why this set is deliberately small. A rule you skip protects nothing.

## Installing them

Copy the numbered files you have accepted into `~/.claude/rules/`, creating that folder if it does not exist. The setup in [START-HERE.md](../START-HERE.md) asks you which you want before it copies anything, so this is a description of what it does rather than an instruction to copy all eighteen. `~` is your home folder and `.claude` is a hidden folder inside it. Claude Code does this for you as a step in [START-HERE.md](../START-HERE.md).

**They install with `starter-kit-` on the front of each filename**, so `03-write-the-project-instructions.md` lands as `starter-kit-03-write-the-project-instructions.md`. That is deliberate. The rules folder is shared with anything else you have put there, and the prefix means one of these can never land on top of a rule of your own, and can never be mistaken for one when you come to remove them.

This README is not a rule. Leave it out of that folder. [`reference/undo.md`](../reference/undo.md) covers taking them out again. Nothing else depends on any single one.

## What the numbers mean

The blocks say when a rule starts to matter, not how important it is. The gaps let a block grow without renumbering the rest.

| | |
|---|---|
| **01 to 09** | Day one. Every one of these applies from your first hour. |
| **20 to 23** | When something you make goes to someone else. |
| **30 to 34** | When you are building software rather than documents. |

Every rule outside the day-one block opens with the moment that triggers it, so you can leave a block alone until then.

## Which to read first

If you read only three: **01** (where a session stands and how far it can reach), **03** (the one file it reads every time), **05** (how to stop it and how to get back). Those are what make everything else safe to try.

Otherwise read 01 to 09 straight through, once. That is the whole day-one set.
