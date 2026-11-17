# Discy Second Brain

Discy Second Brain lets Claude use your [Discy](https://discyhabit.com) workspace as a second brain.
Before you start a piece of work, Claude looks up related notes, tasks, habits, projects and goals you
already wrote in Discy. After the work, it drafts a note you can save. Once a week, it runs a structured
review of what moved and what to do next.

The plugin contains five skills and one remote MCP server reference. It runs no local code, installs no
packages and has no hooks.

## Skills

| Skill | What it does |
| --- | --- |
| `brain-recall` | Before non-trivial work, searches your Discy workspace for related context and cites what it used. |
| `brain-capture` | After work, distils decisions and lessons into a note draft. Nothing is saved to Discy automatically. |
| `brain-weekly-review` | Produces Outcome / Output / Actions / Lessons / One Thing Tomorrow from your tasks, goals, projects and notes. |
| `brain-reflections` | Reads your Kaizen / Reflect entries, only after you grant the separate optional permission. |
| `brain-appointments` | Views, reschedules or deletes an existing appointment, only with the optional permission and your explicit confirmation each time. |

## Install

From the Claude plugin directory, or in Claude Code:

```
/plugin install discy-second-brain --marketplace canhanmvp/discy-claude-plugin
```

## Requirements

- A Discy account (sign up at [app.discyhabit.com](https://app.discyhabit.com)). MCP access follows your Discy plan.
- Sign-in through OAuth the first time Claude uses a Discy tool. In Claude Code, run `/mcp` and choose
  **Authenticate** for `discy`.

## What it connects to

The plugin declares one remote MCP server: `https://mcp.discyhabit.com/agent`, operated by the Discy
developer. It uses OAuth 2.0 with PKCE. You see Discy's own consent screen, which lists the permissions
requested:

- `workspace.read` (default): search and read titles and supported fields of your Tasks, Projects, Goals,
  Habits, ordinary Notes and Board metadata.
- `kaizen.read` (optional): read Kaizen / Reflect entries. Diary and mood logs are never included.
- `appointments.write` (optional, Claude Code client only): read, edit or delete existing appointments after
  you confirm the exact change.

Password Vault entries are never returned. The plugin cannot create or edit notes, tasks, projects, goals or
Boards. Search is bounded and may be incomplete.

## Data and privacy

When a skill runs, Claude sends your search query or the item ID to the Discy MCP server and receives the
matching items from your own account. Discy does not receive your Claude conversation beyond those tool
arguments. Access tokens expire, and you can disconnect at any time from Discy settings or by removing the
connector in Claude.

Privacy policy: <https://discyhabit.com/privacy>. Terms: <https://discyhabit.com/terms>.

## Support

Email support@discyhabit.com or visit <https://discyhabit.com/support>.

## License

MIT, see [LICENSE](LICENSE).
