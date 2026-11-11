# alen-androsevic skills

A Claude Code plugin marketplace. This repository holds only the index, `.claude-plugin/marketplace.json`; each plugin lives in its own repository.

```bash
claude plugin marketplace add alen-androsevic/skills
claude plugin install <plugin>@alen-androsevic
```

| Plugin | What it does |
|---|---|
| [break-stuff](https://github.com/alen-androsevic/break-stuff) | Drives a running web page or mobile app as a hostile user, tries to break it, and reports every break with repro steps and evidence |
| [skat](https://github.com/alen-androsevic/skat) | Creates a new Claude Code skill through a few multiple-choice questions, grills the draft with grillmeister, and writes it as parts that skat builds into `skills/<name>/` |
| [grillmeister](https://github.com/alen-androsevic/grillmeister) | Grills a Claude Code skill draft: finds every gap a cold run would trip over and asks you about each one, one multiple-choice question at a time, then fixes the draft |

## Adding a plugin

1. Give it its own repository with `.claude-plugin/plugin.json` and `skills/<name>/SKILL.md`. Skills that are used together go in one plugin, which namespaces them as `<plugin>:<skill>`.
2. Add an entry to `plugins` in `.claude-plugin/marketplace.json` with `"source": { "source": "github", "repo": "alen-androsevic/<repo>" }`, using the same `name` as the plugin's `plugin.json`.
3. Run `claude plugin validate .` and add a row to the table above.
