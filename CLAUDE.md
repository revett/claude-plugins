# CLAUDE.md

This repo is a Claude Code plugin marketplace (`revett-claude-plugins`).

## Marketplace

Add marketplace:

```bash
/plugin marketplace add revett/claude-plugins
```

Install plugin:

```bash
/plugin install some-plugin@revett-claude-plugins
```

## Docs

- [Create Plugins](https://code.claude.com/docs/en/plugins)
- [Plugin Marketplaces](https://code.claude.com/docs/en/plugin-marketplaces)
- [Plugins Reference](https://code.claude.com/docs/en/plugins-reference)
- [Discover & Install Plugins](https://code.claude.com/docs/en/discover-plugins)
- [Skills](https://code.claude.com/docs/en/skills)
- [Hooks](https://code.claude.com/docs/en/hooks)
- [Subagents](https://code.claude.com/docs/en/sub-agents)

## Testing Plugins Locally

```bash
claude --plugin-dir ./my-plugin
```

## Version Management

- Use semver in `plugin.json` and `marketplace.json`
- Claude Code uses the version to detect updates
- Always bump version when making changes, or users won't see updates due to caching
