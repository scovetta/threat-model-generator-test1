# threat-model-generator

A [GitHub Copilot CLI](https://docs.github.com/en/copilot/how-tos/copilot-cli)
plugin that generates a STRIDE-based `threat_model.md` for whatever project
you run it in.

## Install

From an interactive Copilot CLI session:

```text
/plugin install scovetta/threat-model-generator-test1
```

Or from your shell:

```sh
copilot plugin install scovetta/threat-model-generator-test1
```

Verify it loaded:

```text
/plugin list
/skills list
```

You should see the `threat-model-generator` plugin and its `threat-model-generator` skill.

## Use

`cd` into any project you want to analyze, start Copilot CLI, and ask:

> Generate a threat model for this project.

The skill will:

1. Inspect the project (README, manifests, source layout, dependencies,
   entry points, data stores, existing security controls).
2. Enumerate threats using the **STRIDE** methodology, scoped to what it
   actually found in your code.
3. Write `threat_model.md` at the project root with sections for System
   Overview, Architecture & Data Flow (with a Mermaid diagram), Assets,
   Trust Boundaries, Threats by STRIDE category, prioritized
   Recommendations, Assumptions / Out-of-Scope, and References.
4. Summarize what it produced and suggest next steps.

## What's in this repo

```
.
├── plugin.json                              # Copilot CLI plugin manifest
└── skills/
    └── threat-model-generator/
        └── SKILL.md                         # Skill instructions
```

See the [Copilot CLI plugin reference](https://docs.github.com/en/copilot/reference/copilot-cli-reference/cli-plugin-reference)
for details on the plugin format.

## Uninstall

```sh
copilot plugin uninstall threat-model-generator
```

## License

MIT
