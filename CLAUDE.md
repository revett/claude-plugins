# CLAUDE.md

This repo is a personal collection of Claude Code plugins as a marketplace.

## Documentation

Refer to the following Claude Code documentation, especially to ensure we follow best practices and
specifications (e.g. for plugins, skills etc):

- [Create Plugins](https://code.claude.com/docs/en/plugins)
- [Plugin Marketplaces](https://code.claude.com/docs/en/plugin-marketplaces)
- [Plugins Reference](https://code.claude.com/docs/en/plugins-reference)
- [Discover & Install Plugins](https://code.claude.com/docs/en/discover-plugins)
- [Skills](https://code.claude.com/docs/en/skills)
- [Hooks](https://code.claude.com/docs/en/hooks)
- [Subagents](https://code.claude.com/docs/en/sub-agents)

## Project Structure

```plaintext
.claude-plugin/
  marketplace.json
plugins/
  foo/
    commands/
      bar.md
    skills/
      baz/
        SKILL.md
    .claude-plugin/
      plugin.json
```
