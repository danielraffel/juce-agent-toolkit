# JUCE Agent Toolkit

Portable JUCE development skills for coding agents outside Claude Code.

JUCE Agent Toolkit gives agents like Codex, Cursor, OpenCode, Gemini CLI, GitHub Copilot, and other supported hosts practical JUCE knowledge without requiring the `juce-dev` Claude Code plugin.

## Installing JUCE Agent Toolkit

Install the whole toolkit:

```bash
npx skills add https://github.com/danielraffel/juce-agent-toolkit --skill '*'
```

Install one skill:

```bash
npx skills add https://github.com/danielraffel/juce-agent-toolkit --skill juce-project-starter
```

If you get the error `npx: command not found`, you need to [install Node first](https://nodejs.org/en/download). On macOS, the quickest route is:

```bash
brew install node
```

When using `npx`, the installer will guide you through which agents to install into and whether the skills should be installed for just the current project or for all your projects.

If you prefer, you can also clone this repository and install it however you want.

## What You Get

- `juce-project-starter`: JUCE-Plugin-Starter setup, `.env` configuration, build targets, placeholder replacement, and VST3 MIDI generator patterns.
- `juce-visage-ui`: JUCE + Visage UI integration for macOS and iOS, including embedding, focus, keyboard handling, popups, and troubleshooting.

## JUCE Agent Toolkit vs `juce-dev`

| Capability | JUCE Agent Toolkit | `juce-dev` Claude Code plugin |
|---|---|---|
| Understand JUCE-Plugin-Starter conventions | Yes | Yes |
| Understand JUCE + Visage UI patterns | Yes | Yes |
| Works in Codex, Cursor, OpenCode, Gemini CLI, and similar hosts | Yes | No |
| Guided new-project creation flow | No | Yes |
| Named build/test/sign/publish commands | No | Yes |
| Automated setup for Visage, iOS, and auto-updates | No | Yes |
| CI, logs, secrets, status, VM, website, and port workflows | No | Yes |
| Best fit | Portable JUCE knowledge across agents | Full Claude Code automation |

The easiest way to think about it is:

- JUCE Agent Toolkit is the portable knowledge layer
- `juce-dev` is the Claude Code automation layer on top

If you want the full guided workflow in Claude Code, use the plugin:

- https://www.generouscorp.com/generous-corp-marketplace/plugins/juce-dev/

If you already use `juce-dev`, do not install overlapping toolkit skills into Claude Code. Use this toolkit for your other agents instead.

## Using JUCE Agent Toolkit

These are skills, not slash commands.

In hosts that support explicit skill invocation, use the host's normal skill shortcut with one of these names:

- `juce-project-starter`
- `juce-visage-ui`

You can also trigger the skills using natural language. For example:

```text
Use the juce-project-starter skill to explain which .env values I need for code signing.
Use the juce-project-starter skill to help configure a VST3 MIDI generator for Ableton and Logic.
Use the juce-visage-ui skill to debug keyboard focus in my JUCE + Visage plugin UI.
Use the juce-visage-ui skill to show the right way to embed Visage inside a JUCE editor.
```

## Planned v2

This release focuses on the portable foundation.

The next release should expand parity with `juce-dev` by adding more portable skills and shared scripts for:

- build and release workflows
- setup flows for Visage, iOS, and auto-updates
- more of the plugin's day-to-day operational surface

As that work lands, the matrix above should be updated to reflect the new capability split.

## Related Projects

- `juce-dev` Claude Code plugin: https://www.generouscorp.com/generous-corp-marketplace/plugins/juce-dev/
- `JUCE-Plugin-Starter`: https://github.com/danielraffel/JUCE-Plugin-Starter
- `skills` installer: https://www.npmjs.com/package/skills
