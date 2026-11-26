# Errilo skills

Agent Skills that teach an AI coding agent to work with [Errilo](https://errilo.com), the European error tracker compatible with the Sentry SDKs, through the Errilo MCP server. This repository is also a Claude Code plugin marketplace.

| Skill                                                  | What it does                                                                                                                           |
| ------------------------------------------------------ | -------------------------------------------------------------------------------------------------------------------------------------- |
| [`errilo-fix-issue`](skills/errilo-fix-issue/SKILL.md) | Fixes a production error from its stack trace to a pull request, then comments on the issue and marks it resolved in the next release. |
| [`errilo-setup`](skills/errilo-setup/SKILL.md)         | Installs Errilo in a repository with the Sentry SDK and checks that a first test error arrives.                                        |
| [`errilo-triage`](skills/errilo-triage/SKILL.md)       | Ranks the open issues by impact and proposes what to fix first. Read-only unless you ask for a change.                                 |
| [`errilo-overview`](skills/errilo-overview/SKILL.md)   | Explains what Errilo is, its MCP tools and prompts, and how to treat production data.                                                  |

## Claude Code (plugin)

```
/plugin marketplace add geterrilo/skills
/plugin install errilo@errilo
```

The plugin installs the Errilo MCP server (`https://app.errilo.com/mcp`) and the four skills. On first use, run `/mcp` to sign in to Errilo (OAuth).

To update: `/plugin marketplace update errilo` refreshes the catalog, then update the plugin itself from `/plugin` (Installed tab) or with `claude plugin update errilo@errilo`, then restart Claude Code. Auto-update can be enabled for the `errilo` marketplace in `/plugin` (Marketplaces tab).

If you added an `errilo` MCP server by hand before (`claude mcp add … errilo …`), remove it with `claude mcp remove errilo` (with the same `--scope` you used): Claude Code keeps only one server per URL and prefers the one you added, so the plugin's configuration would not apply.

## Other agents

Connect your agent to the MCP server `https://app.errilo.com/mcp`. The [agents guide](https://errilo.com/en/agents/) covers each client.

Clients that support the Skills over MCP extension get the skills from the server and follow its updates. Otherwise, copy the folder of a skill from [`skills/`](skills) to where your agent loads its skills. For an agent without skills, paste the body of `SKILL.md` into its `AGENTS.md`.

## Contributing

This repository is generated automatically from the Errilo code at each production release. Any change made here is overwritten by the next publication. To report a problem or suggest an improvement, open an issue in this repository.

## License

MIT, see [LICENSE](LICENSE).
