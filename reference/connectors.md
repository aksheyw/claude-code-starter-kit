# Connecting your other tools

A connector lets Claude Code read from and write to a tool you already use, so you can ask a question in plain language instead of opening six tabs. "What did we ship last sprint and what are people complaining about?" reaches your tracker and your support inbox and comes back as one answer.

**You do not have to configure any of this by hand.** Installing the `product-management` plugin on day one brings twelve connectors with it, already pointed at the right place. All that is left is signing in to the ones you actually use.

## What arrives with the plugin

Read from the plugin's own manifest on 2026-08-01, so this is what it ships rather than what it advertises.

| Connector | What it reaches |
|---|---|
| `slack` | Messages, channels, threads |
| `linear` | Issues, projects, cycles |
| `atlassian` | Jira and Confluence |
| `asana` | Tasks and projects |
| `monday` | Boards and items |
| `clickup` | Tasks, docs, spaces |
| `notion` | Pages and databases |
| `figma` | Files, frames, comments |
| `amplitude` | Product analytics |
| `pendo` | Product analytics and guides |
| `intercom` | Support conversations |
| `fireflies` | Meeting recordings and transcripts |

**Not in this bundle:** Google Workspace, Gmail, Calendar, and GitHub. Other bundles in the same marketplace may carry them. Run `claude plugin marketplace list` and look, rather than assuming from this page.

## Turning one on

Inside Claude Code:

```
/mcp
```

That lists every connector available to you and whether it is connected. Pick one and it opens your browser to sign in, the same flow as connecting any app to any other app. **You never paste an API key.**

Sign in only to the ones you genuinely use. An unconnected connector sits there costing nothing, so there is no tidiness argument for connecting all twelve, and a good argument against: every connected tool is one more place Claude can read from, and you want that list to be one you can hold in your head.

## Checking it worked

Ask for something only that tool knows:

> What are the three most recently updated issues in Linear?

If it comes back with real issues, it is connected. If it says it cannot reach Linear, run `/mcp` again and check the status line next to it.

## Adding one that is not in the list

If a tool you use publishes its own connector, add it directly. The name is yours to choose, the address comes from that tool's own documentation:

```bash
claude mcp add --transport http <name> <address>
```

Some connectors run as a program on your computer rather than over the internet. Those need a `--` before the command, and leaving it out is the usual cause of a connection failure:

```bash
claude mcp add <name> -- <command>
```

## One thing worth being careful about

Anthropic says this plainly, and it is worth repeating rather than burying: a connector runs code on your machine with your permissions, and Anthropic does not control or verify what third-party ones do.

The twelve above come from Anthropic's own marketplace and point at the tool vendors themselves. That is a different risk level from something you found in a list of two thousand community plugins.

So: connect what you use from sources you recognise. Before installing a connector from anywhere else, look at what it is and who wrote it. If you cannot tell, ask Claude Code to read its source and explain what it does before you install it, which is a genuinely good use of it.

**Treat what comes back from a connector as information, not instructions.** If a Jira ticket or a Slack message contains something that reads like a command aimed at Claude, that is not a command you gave. Claude should surface it and ask, never act on it.
