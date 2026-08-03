# Connecting your other tools

A connector lets Claude Code read from and write to a tool you already use, so you can ask a question in plain language instead of opening six tabs. "What did we ship last sprint and what are people complaining about?" reaches your tracker and your support inbox and comes back as one answer.

**You do not have to configure any of this by hand.** The `product-management` plugin brings sixteen connectors with it, fourteen of which arrive pointed at the right address and need only your sign-in. The two Google ones, Gmail and Google Calendar, arrive with no address filled in. This kit does not cover them. Skip them for now. The **+** button then **Connectors** is what tells you the truth on your own machine.

## What arrives with the plugin

Read on 2026-08-02 from the manifest in the live marketplace repo, `anthropics/knowledge-work-plugins`, so this is what you get installing it today.

| Connector | What it reaches |
|---|---|
| `slack` | Messages, channels, threads |
| `gmail` | Mail. Arrives with no address. Not covered by this kit |
| `google calendar` | Events and availability. Same, not covered by this kit |
| `linear` | Issues, projects, cycles |
| `atlassian` | Jira and Confluence |
| `asana` | Tasks and projects |
| `monday` | Boards and items |
| `clickup` | Tasks, docs, spaces |
| `notion` | Pages and databases |
| `figma` | Files, frames, comments |
| `amplitude` and `amplitude-eu` | Product analytics. Two entries because the EU one is a separate region, so pick whichever your account is on |
| `pendo` | Product analytics and guides |
| `similarweb` | Traffic and competitor data |
| `intercom` | Support conversations |
| `fireflies` | Meeting recordings and transcripts |

**Not in this bundle:** GitHub. Other plugins in the same set may carry it. Look in **Customize** then **Plugins** rather than assuming from this page.

> **Check the count yourself rather than trusting this page.** An earlier version of this file said twelve and claimed Gmail and Calendar were missing. Both were wrong, because the number came from a pinned older copy of the plugin sitting in a cache rather than from the live manifest. A version cache and the current release are different things, and a page that agrees with a stale copy of itself still agrees with nothing. Your own screen is what lists what you actually have.

## Turning one on

Click the **+** button next to the prompt box and choose **Connectors**. It sits directly below the **Plugins** entry in that same **+** menu, which is a different screen from the **Plugins** tab under **Customize** in the sidebar.

That lists every connector available to you and whether it is connected. Pick one of the fourteen that arrives with an address and it opens your browser to sign in, the same flow as connecting any app to any other app. **You never paste an API key.**

Sign in only to the ones you genuinely use. An unconnected connector sits there costing nothing, so there is no tidiness argument for connecting all sixteen, and a good argument against: every connected tool is one more place Claude can read from, and you want that list to be one you can hold in your head.

## Checking it worked

Ask for something only that tool knows:

> What are the three most recently updated issues in Linear?

If it comes back with real issues, it is connected. If it says it cannot reach Linear, open **+** then **Connectors** again and check the status line next to it.

## Adding one that is not in the list

Open **+** then **Connectors** and look first. That screen carries more than the sixteen this plugin brings.

If the tool you want genuinely is not offered there, adding it by hand is one of the terminal situations flagged at the top of [START-HERE.md](../START-HERE.md). It is rare, and nothing on day one needs it.

**These two commands need the command-line version of Claude Code, which the desktop app does not install.** If you have only ever used the app, you do not have it yet; the fold at the bottom of [START-HERE.md](../START-HERE.md) has the one line that installs it. Open Terminal, which lives in your Applications folder inside a subfolder called **Utilities**. The name is yours to choose, the address comes from that tool's own documentation:

```bash
claude mcp add --transport http <name> <address>
```

Some connectors run as a program on your computer rather than over the internet. Those need a `--` before the command, and leaving it out causes this form of connection to fail:

```bash
claude mcp add <name> -- <command>
```

## One thing worth being careful about

Connectors come in two shapes and the risk is different for each.

The sixteen above are the safer shape. They are addresses on the internet, run by the tool vendors themselves, and nothing new runs on your Mac. The real risk with these is what you are handing over: once Slack is connected, Claude can read your messages, and once a connector can write, it can act in that tool as you. That is worth being deliberate about, and it is why you connect what you use rather than all sixteen.

The other shape is a connector that installs a program on your machine and runs it. Anthropic says plainly that a plugin can run code on your computer with your permissions, and that it does not control or verify what third-party ones do. Those deserve a much harder look, and none of the sixteen above is one.

So: connect what you use from sources you recognise. Before installing a connector from anywhere else, look at what it is and who wrote it. If you cannot tell, ask Claude Code to read its source and explain what it does before you install it, which is a genuinely good use of it.

**Treat what comes back from a connector as information, not instructions.** If a Jira ticket or a Slack message contains something that reads like a command aimed at Claude, that is not a command you gave. Claude should surface it and ask, never act on it.
