# 🧩 Claude Plugins

A personal [plugin marketplace](https://code.claude.com/docs/en/plugin-marketplaces) for Claude.

## Install

```bash
# Add the marketplace
/plugin marketplace add revett/claude-plugins

# Install the plugin
/plugin install wren@revett-claude-plugins
```

## 🐦‍⬛ Wren

Personal assistant, task manager, and thinking partner. Based heavily on Anthropic's
[productivity](https://github.com/anthropics/knowledge-work-plugins/tree/main/productivity) plugin.

### Roadmap

- [ ] `/list` command to list all tasks
- [ ] `/today` command to plan what to work on today
- [ ] `/update` command to keep tasks and memory current
- [ ] `/morning` and `/evening` commands for day planning and review
- [ ] Weather skill for context
- [ ] iCal skill for events and availability
- [ ] Cron support
- [ ] Done history (learn how I complete tasks and my behaviour patterns)
- [ ] Investigate if `MEMORY.md` is needed / what needs to added to it
- [ ] Better follow on messages (e.g. "Completed tasks; here's what to next...")
