# JUCE Agent Toolkit

Installable JUCE workflow skills for coding agents that support the `skills` ecosystem.

This repo is a standalone skills package. It is not the `juce-dev` Claude Code plugin, and it does not depend on that plugin. The point is to make the JUCE workflow available to agents like Codex, Cursor, OpenCode, and others through a standard installer flow.

## Included Skills

- `juce-project-starter`: JUCE-Plugin-Starter setup, `.env` configuration, build targets, placeholder replacement, and VST3 MIDI generator patterns.
- `juce-visage-ui`: JUCE + Visage UI integration patterns for macOS and iOS, including embedding, focus, keyboard handling, popups, and troubleshooting.

## Install

List available skills:

```bash
npx skills add danielraffel/juce-agent-toolkit --list
```

Install a specific skill globally for Codex:

```bash
npx skills add danielraffel/juce-agent-toolkit \
  --skill juce-project-starter \
  --agent codex \
  --global
```

Install both skills for Codex and Cursor:

```bash
npx skills add danielraffel/juce-agent-toolkit \
  --skill '*' \
  --agent codex \
  --agent cursor \
  --global
```

Install for Claude Code only if you are not already using the `juce-dev` plugin:

```bash
npx skills add danielraffel/juce-agent-toolkit \
  --skill '*' \
  --agent claude-code \
  --global
```

## Claude Code Note

If you already use the `juce-dev` Claude Code plugin, prefer the plugin for Claude Code and use this repo for your other agents.

The plugin already bundles overlapping JUCE workflow guidance, so installing the same guidance again into `claude-code` is unnecessary. A clean pattern is:

- use `juce-dev` in Claude Code
- use `juce-project-starter` and `juce-visage-ui` in Codex, Cursor, OpenCode, or other agents

Plugin link:

- https://www.generouscorp.com/generous-corp-marketplace/plugins/juce-dev/

## How It Works

This repo uses the standard agent-skills layout:

```text
skills/
  juce-project-starter/
    SKILL.md
    references/
    agents/openai.yaml
  juce-visage-ui/
    SKILL.md
    references/
    agents/openai.yaml
```

The `skills` CLI installs these skill folders into the target agent's skill directory by symlink or copy. After that, the target agent can discover and trigger them like any other installed skill.

## Related Projects

- `juce-dev` Claude Code plugin: https://www.generouscorp.com/generous-corp-marketplace/plugins/juce-dev/
- `JUCE-Plugin-Starter`: https://github.com/danielraffel/JUCE-Plugin-Starter
- `skills` installer: https://www.npmjs.com/package/skills

