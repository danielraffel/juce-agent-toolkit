# JUCE Agent Toolkit

Portable JUCE workflow skills for coding agents outside Claude Code.

JUCE Agent Toolkit gives agents like Codex, Cursor, OpenCode, Gemini CLI, GitHub Copilot, and other supported hosts practical help with the custom workflow around your JUCE ecosystem:

- `JUCE-Plugin-Starter` project setup and conventions
- `.env`, build, signing, and release flows
- Visage GPU UI setup and debugging
- cross-DAW plugin behavior that is easy to get wrong without project context

This is not a general JUCE API docs package, and it is not a clone of the `juce-dev` Claude Code plugin.

## Installing JUCE Agent Toolkit

You can install these skills into Codex, Gemini CLI, Cursor, GitHub Copilot, OpenCode, and other supported hosts by using `npx`:

```bash
npx skills add https://github.com/danielraffel/juce-agent-toolkit --skill '*'
```

If you get the error `npx: command not found`, you need to [install Node first](https://nodejs.org/en/download). On macOS, the quickest route is:

```bash
brew install node
```

When using `npx`, the installer will guide you through which agents to install into and whether the toolkit should be installed for just the current project or for all your projects.

If you prefer, you can also clone this repository and install it however you want.

## What You Get

- `juce-project-starter`: starter template structure, `.env` setup, formats, placeholder replacement, and MIDI generator patterns
- `juce-visage-ui`: JUCE + Visage UI integration and debugging on macOS and iOS
- `juce-build-release`: build, test, sign, package, and publish workflows based on starter scripts
- `juce-setup-visage`: portable setup flow for adding Visage to an existing starter project
- `shared/scripts/inspect_juce_project.py`: reusable project inspector used by the workflow skills

In plain English:

- this helps an agent understand your starter-based project faster
- this helps an agent run more of the build and setup workflow without guessing
- this helps an agent debug Visage-based plugin UIs without guessing
- this still does not recreate Claude Code slash commands or menu-driven prompts

## Parity Matrix

Matrix key:

- `Yes`: strong toolkit support today
- `Partial`: meaningful skill or script support, but not full plugin automation
- `No`: plugin-only today

| Capability | JUCE Agent Toolkit v2.0 | `juce-dev` Claude Code plugin |
|---|---|---|
| Understand JUCE-Plugin-Starter conventions | Yes | Yes |
| Understand JUCE + Visage UI patterns | Yes | Yes |
| Build, test, sign, package, and publish from starter scripts | Partial | Yes |
| Add Visage to an existing starter project | Partial | Yes |
| Create a new project from the starter | No | Yes |
| Add an iOS app target | No | Yes |
| Add auto-update support | No | Yes |
| Inspect project status and enabled features | Partial | Yes |
| Trigger CI, view logs, and manage release secrets | No | Yes |
| Create or refresh a GitHub Pages download site | No | Yes |
| Manage cross-platform VMs | No | Yes |
| Audit and port a project across macOS, Windows, and Linux | No | Yes |
| Works in Codex, Cursor, OpenCode, Gemini CLI, and similar hosts | Yes | No |

The easiest way to think about it is:

- JUCE Agent Toolkit is the portable skills-and-scripts layer
- `juce-dev` is the best Claude Code automation layer on top

If you want the full guided workflow in Claude Code, use the plugin:

- https://www.generouscorp.com/generous-corp-marketplace/plugins/juce-dev/

If you already use `juce-dev`, do not install overlapping toolkit skills into Claude Code. Use this toolkit for your other agents instead.

If you want official JUCE class and method documentation inside your agent, use the JUCE docs MCP server alongside this toolkit:

- https://github.com/danielraffel/juce-docs-mcp-server

## Using JUCE Agent Toolkit

These are skills, not slash commands.

In hosts that support explicit skill invocation, use the host's normal skill shortcut with one of these names:

- `juce-project-starter`
- `juce-visage-ui`
- `juce-build-release`
- `juce-setup-visage`

You can also trigger the skills using natural language. For example:

```text
Use the juce-build-release skill to help me run a signed VST3 build from this starter project.
Use the juce-setup-visage skill to add Visage to this existing JUCE-Plugin-Starter repo.
Use the juce-project-starter skill to explain which .env values I need for code signing.
Use the juce-visage-ui skill to debug keyboard focus in my JUCE + Visage plugin UI.
```

## Related Projects

- `juce-dev` Claude Code plugin: https://www.generouscorp.com/generous-corp-marketplace/plugins/juce-dev/
- `JUCE-Plugin-Starter`: https://github.com/danielraffel/JUCE-Plugin-Starter
- `skills` installer: https://www.npmjs.com/package/skills
