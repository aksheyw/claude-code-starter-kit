# [Project name]

<!--
This file is your project's instructions. Claude Code reads it at the start of every
conversation about this project, so it is the highest-leverage page you own.

Two rules for keeping it useful:

1. Keep it under a page. It is read every single time, so length is a real cost.
   When a section grows, move the detail into its own file and leave a pointer here.
2. Keep it TRUE. A stale instruction is worse than a missing one, because Claude
   believes it. Fix it the moment something changes.

Delete these comments and the bracketed prompts as you fill it in.
-->

## What this is

[One or two sentences. What the project is and what it is for.]

## Who it is for

[Who uses this, and what they are trying to get done. If you know who it is NOT for, say that too, because it prevents more wrong turns than the positive version.]

## How I want you to work with me

- Explain things in plain words. Assume I am smart and not an engineer.
- Tell me what something means for me before you tell me what you did.
- One thing at a time. If there are five threads, name the one that matters now.
- Show me evidence, not confidence. If you say it works, show me what you ran.
- Ask me when you are unsure. A question costs me ten seconds. A wrong guess costs me an afternoon.

## What it is built with

[Delete this section if there is no code. Otherwise: the language, the framework, where it runs, where the data lives. Keep it to a list.]

## How to run and check it

[Delete if there is no code. Otherwise the exact commands: how to start it, how to test it. Being exact here saves you re-explaining it every session.]

## Decisions already made

[Things settled, so they do not get re-argued every conversation. One line each, with the reason.

Example:
- Payments go through Stripe, not PayPal. Already have an account and the fees are lower at our volume.]

## Things that are not obvious

[The traps. Anything that surprised you once and would surprise you again.

Example:
- The date field is stored in UTC but displayed in local time. Anything comparing dates has to convert first.]

## Where things live

- Current state and what is in progress: `.claude/wiki/_hot.md`
- Session by session record: `.claude/wiki/_log.md`
- Corrections I have already given you, so I never give them twice: `lessons/index.md`
- [Add your own pointers here as the project grows.]

## Read at the start of every conversation

Read `lessons/index.md` if it exists, before doing any work. It is the list of things I have already
corrected you on. This line is what makes that happen: nothing loads a lessons file automatically, so
if this line is deleted, every lesson in that folder stops being read.
