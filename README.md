# Trimtab Claude plugin

Connect Claude to Trimtab with its bundled MCP connector, operating skills, and feedback commands.
The connection defaults to `https://bridge.trimtab.cc/api/mcp`.
`ATLAS_MCP_URL` overrides the address in Claude Code.

## Install in Claude Code

Run these commands in a Claude Code session, then review the plugin and choose an installation scope.

```text
/plugin marketplace add archipelagoaec/trimtab
/plugin install trimtab@trimtab
```

For automatic updates, open `/plugin`, select the trimtab marketplace under Marketplaces,
and select Enable auto-update.
[Claude Code installation and updates](https://code.claude.com/docs/en/discover-plugins), checked 2026-10-25.

## Install in claude.ai

1. Open **Customize > Plugins**.
2. Choose **Add > Add marketplace** and enter `https://github.com/archipelagoaec/trimtab`.
3. Select Trimtab and choose **Add**.
4. Open Trimtab's **Connectors** tab. Add the connector if it shows **Not added**, then connect it if it shows **Not connected**.

On Team and Enterprise plans, an Owner adds the connector for the organization.
Each person then connects with their own account.
For updates from this GitHub marketplace, enable **Sync automatically**, or select **Check for updates**.
[Anthropic plugin installation, connectors, and updates](https://claude.com/docs/plugins/overview), checked 2026-10-25.

## Use Trimtab

Describe your task to load a matching skill, or use `/trimtab:feedback`,
`/trimtab:bug-report`, or `/trimtab:feature-request`.
The connector requires access to a Trimtab organization.

## License

See [LICENSE](LICENSE) for the GNU Affero General Public License, version 3.
