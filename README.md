# sstack

A small collection of agent skills for Claude Code, Codex, and other
agents that support the `SKILL.md` format.

## Skills

| Skill | What it does |
| --- | --- |
| [`decision-helper`](skills/decision-helper/SKILL.md) | Gets independent opinions on a decision from a panel of models, then decides with you. Say "decision helper" (add "light" for the lighter panel). |

## Install

With the [`skills`](https://github.com/vercel-labs/skills) CLI:

```sh
npx skills add solo-stack-dev/sstack
```

Or copy a skill folder by hand:

```sh
git clone https://github.com/solo-stack-dev/sstack
cp -r sstack/skills/decision-helper ~/.claude/skills/
```

## Layout

```
skills/
  <skill-name>/
    SKILL.md   # frontmatter (name, description) + instructions
```

## Notes

`decision-helper` uses T3 Code's orchestration tools
(`orchestrator_capabilities`, `delegate_task`) to run its panel across
providers.

## License

[MIT](LICENSE)
