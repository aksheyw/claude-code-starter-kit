# Ask for code that stays easy to change

*Trigger: an app you keep coming back to.*

Ask for small files that each do one job, one agreed shape for what recurs, and a note on every shortcut.

**Why this exists.** Long files are where bugs hide and where I make my worst edits, because I have to read the whole file to change one part of it. Without an agreed shape, every new part invents its own variant.

**How to apply it.**

- One job per file, grouped by feature. When changing one thing means reading the whole file, that is the moment to split it. And no values typed mid-code: name them once, in one place.
- Pick one shape for anything that recurs and write it into your project instructions, the CLAUDE.md from rule 03. Same shape and same field names for every answer your server sends back, so new work becomes assembly rather than invention.
- Every failure produces two messages: a calm one telling the person what to do, and a detailed one recorded for you. Never show the second, never throw it away, and never let either carry a key or private data.
- Mark every shortcut with the point where it stops working: "SHORTCUT: fine to about 500 records, needs to fetch in batches past that." A note without that trigger rots.
