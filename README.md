# Errilo skills

Agent Skills that teach an AI coding agent to work with [Errilo](https://errilo.com), the European error tracker compatible with the Sentry SDKs, through the Errilo MCP server.

| Skill                                           | What it does                                                                                                                           |
| ----------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------- |
| [`errilo-fix-issue`](errilo-fix-issue/SKILL.md) | Fixes a production error from its stack trace to a pull request, then comments on the issue and marks it resolved in the next release. |
| [`errilo-setup`](errilo-setup/SKILL.md)         | Installs Errilo in a repository with the Sentry SDK and checks that a first test error arrives.                                        |
| [`errilo-triage`](errilo-triage/SKILL.md)       | Ranks the open issues by impact and proposes what to fix first. Read-only unless you ask for a change.                                 |
| [`errilo-overview`](errilo-overview/SKILL.md)   | Explains what Errilo is, its MCP tools and prompts, and how to treat production data.                                                  |

## Requirements

The skills call the tools of the Errilo MCP server, `https://app.errilo.com/mcp`. Connect your agent to it first.

In Claude Code:

```sh
claude mcp add --transport http errilo https://app.errilo.com/mcp
```

Then run `/mcp` in Claude Code to sign in to Errilo (OAuth). The [agents guide](https://errilo.com/en/agents/) covers the other clients.

## Install

Clients that support the Skills over MCP extension need nothing: the skills come with the server and follow its updates.

Otherwise, copy the folder of a skill to where your agent loads its skills, for example `.claude/skills/` (project) or `~/.claude/skills/` (user) for Claude Code. For an agent without skills, paste the body of `SKILL.md` into its `AGENTS.md`.

## Contributing

This repository is generated automatically from the Errilo code at each production release. Any change made here is overwritten by the next publication. To report a problem or suggest an improvement, open an issue in this repository.

## License

MIT, see [LICENSE](LICENSE).
