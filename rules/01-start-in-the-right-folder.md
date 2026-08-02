# Start in the right folder

Claude Code works in the folder you started it in, and everything inside that folder is within reach.

**Why this exists.** How far a mistake can spread is decided before you type anything, by where the session was started. Start it in the folder that holds all your work and a request meant for one app has every other file you own in scope.

**How to apply it.**

- You start a session by moving into a folder and typing `claude`. Moving into it is one Terminal line, `cd ~/Documents/my-project`, using your own folder name. That folder is the project for the whole session. Typing `claude` without moving first starts it in your home folder, which is the case this rule exists to prevent.
- Give each project its own folder and start the session inside it. Not the folder that holds all your projects, not Documents, not your home folder.
- Keep out of it anything you would not hand to a stranger: personal documents, downloads, another project's files.
- If you are not sure where a session is standing, ask before anything runs: "which folder are you working in, and what is in it?"
- A broad instruction in a broad folder is the combination that hurts. "Tidy up the old files" means one thing in a project folder and something much worse one level up.
