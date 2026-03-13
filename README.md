# JUCE Agent Toolkit

Installable JUCE workflow skills for coding agents that support the `skills` ecosystem.

This repo is a standalone skills package. It is not the `juce-dev` Claude Code plugin, and it does not depend on that plugin. The point is to make the JUCE workflow available to agents like Codex, Cursor, OpenCode, and others through a standard installer flow.

## Included Skills

- `juce-project-starter`: JUCE-Plugin-Starter setup, `.env` configuration, build targets, placeholder replacement, and VST3 MIDI generator patterns.
- `juce-visage-ui`: JUCE + Visage UI integration patterns for macOS and iOS, including embedding, focus, keyboard handling, popups, and troubleshooting.

## Installing JUCE Agent Toolkit

Install one skill:

```bash
npx skills add https://github.com/danielraffel/juce-agent-toolkit --skill juce-project-starter
```

Install both skills:

```bash
npx skills add https://github.com/danielraffel/juce-agent-toolkit --skill '*'
```

List available skills first if you want to browse:

```bash
npx skills add https://github.com/danielraffel/juce-agent-toolkit --list
```

The installer will guide you through:

- which agents you want to install into
- whether the skills should be installed for just one project or all your projects
- whether to symlink or copy the installed skills

If you get the error `npx: command not found`, install Node first:

```bash
brew install node
```

If that fails, you likely need to install Homebrew first.

Alternatively, you can clone this repository and install it however you want.

## Claude Code Note

If you already use the `juce-dev` Claude Code plugin, prefer the plugin for Claude Code and use this repo for your other agents.

The plugin already bundles overlapping JUCE workflow guidance, so installing the same guidance again into `claude-code` is unnecessary. A clean pattern is:

- use `juce-dev` in Claude Code
- use `juce-project-starter` and `juce-visage-ui` in Codex, Cursor, OpenCode, or other agents

Plugin link:

- https://www.generouscorp.com/generous-corp-marketplace/plugins/juce-dev/

## Using The Skills

These are skills, not slash commands.

That means there is no `/juce-dev:create`-style command table here. Instead, your agent will either:

- detect the skill automatically from your request
- let you invoke the skill by name, depending on the agent

The exact invocation style varies by agent, but these are the kinds of requests each skill is for:

### `juce-project-starter`

- "Help me set up a new JUCE-Plugin-Starter project."
- "Explain which `.env` values I need for code signing and GitHub releases."
- "How does JUCE-Plugin-Starter generate plugin codes and bundle IDs?"
- "Help me configure a VST3 MIDI generator that still works as an AU MIDI effect in Logic."

### `juce-visage-ui`

- "Help me debug keyboard focus in my JUCE + Visage plugin UI."
- "Show me the right way to embed Visage inside a JUCE editor."
- "Help me build a popup or modal system in a Visage-based plugin."
- "Why is my Visage-based plugin failing keyboard shortcuts in a DAW host?"

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
