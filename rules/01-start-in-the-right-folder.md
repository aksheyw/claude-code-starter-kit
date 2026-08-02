# Start in the right folder

Claude Code works in the folder the session was pointed at, and everything inside that folder is within reach.

**Why this exists.** How far a mistake can spread is decided before you type anything, by which folder the session was pointed at. Point it at the folder that holds all your work and a request meant for one app has every other file you own in scope.

**How to apply it.**

- In the desktop app you pick the folder when the session starts: choose **Local**, then **Select folder**. That folder is the project for the whole session. In the terminal you move into the folder first, `cd ~/Documents/my-project`, and then type `claude`. Typing `claude` without moving first starts it in your home folder, which is the case this rule exists to prevent.
- Give each project its own folder and start the session inside it. Not the folder that holds all your projects, not Documents, not your home folder.
- Keep out of it anything you would not hand to a stranger: personal documents, downloads, another project's files.
- If you are not sure where a session is standing, ask before anything runs: "which folder are you working in, and what is in it?"
- A broad instruction in a broad folder is the combination that hurts. "Tidy up the old files" means one thing in a project folder and something much worse one level up.
