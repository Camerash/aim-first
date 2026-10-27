# aim-first

A portable agent skill. When you offer a method ("let's do X with Y"), the agent first:

1. restates your aim in its own words,
2. finds the real quality bar (what is good enough for that aim),
3. compares your method with one to three other methods on cost and quality,
4. recommends one, and lets you decide.

The check is small for small choices and larger for big or hard-to-reverse choices. It also starts when the same work needs a third round of rework.

Why: experts often choose the method they know best, not the method that fits the aim. Example: high-detail models for characters that are seen small on a phone.

The skill is `SKILL.md` (the [Agent Skills](https://agentskills.io) format: YAML front matter with `name` and `description`, then the instructions).

## Install

Claude Code, for all your projects:

```bash
git clone https://github.com/Camerash/aim-first ~/.claude/skills/aim-first
```

One project only (Claude Code, Codex and other agents that read `.agents/skills/`):

```bash
git clone https://github.com/Camerash/aim-first .agents/skills/aim-first
ln -s ../../.agents/skills/aim-first .claude/skills/aim-first   # for Claude Code
```

claude.ai: zip this folder (or use a packaged `.skill` file) and add it under Settings → Capabilities → Skills.

To make the agent use it every time, add a line to the project rules (`CLAUDE.md` or `AGENTS.md`), for example:

> When the user offers a solution or a method, apply the `aim-first` skill before the work starts.

## Update

```bash
git -C ~/.claude/skills/aim-first pull
```

## License

MIT. See `LICENSE`.
