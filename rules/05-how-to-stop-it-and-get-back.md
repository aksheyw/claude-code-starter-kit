# How to stop it and how to get back

Learn the stop key and the way back to a working version before you need them, not while you need them.

**Why this exists.** Being careful about what cannot be undone only helps if you know how to undo things. Without that, the safe move is to stop trying things, and then nothing gets built.

**How to apply it.**

- To stop it mid-run, press Escape. It stops there and keeps whatever it had already finished. You do not have to wait for it to end, or close anything.
- To go back, type `/rewind`, or press Escape twice with nothing typed in the box. It lists the prompts you sent this session and offers to put the code back, the conversation back, or both.
- Rewind has holes, and they are the dangerous ones. It restores files it edited itself. It does not restore files changed by commands it ran, so deleting, moving and copying sit outside it, and nor does it cover work done by a second session it started on its own (rule 33).
- Rewind is undo for this session only. The first time you have work you would hate to lose, that is the moment to add real save points, which means a commit: a checkpoint of the whole project you can return to any time (rule 22).
- When something goes wrong, ask for the way back before you approve a fix on top of it. A fix on top of a mess is a bigger mess.
- If the tool itself is misbehaving rather than the work, quit it and open it again. In the desktop app that is `Cmd` `Q` and relaunch. If you use the terminal version and that does not help, `claude doctor` in a terminal checks the installation rather than the conversation.
