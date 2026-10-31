# why

**Ask why a code path exists—not only what it does.**

`why` is a portable agent skill for investigating unfamiliar code. It connects current behavior to the implementation, tests, and—when available—the commit, pull request, issue, or design note that explains how a decision came about.

It keeps three things distinct: what the code does now, what a source says about the original intent, and what can only be inferred from the evidence.

## Use it

Ask questions such as:

- `Why does this retry loop stop after five attempts?`
- `Why was this compatibility branch added?`
- `Why does this state update use a layout effect?`

The skill follows the relevant code path, checks history when it may clarify the answer, and returns a concise explanation with sources and meaningful uncertainty.

## Install

Copy `skills/why/` into the skills directory supported by your agent, keeping the folder name `why` and its `references/` directory together.

The skill uses the `SKILL.md` format with its reference files kept alongside it. After installing, invoke `/why` if your agent supports slash commands, or ask a matching question naturally.

There is no plugin, build step, dependency, or setup script.

## Evidence labels

| Label | Meaning |
| --- | --- |
| **Documented** | A source explicitly states the reason or constraint. |
| **Inferred** | Specific code or history supports the explanation, but no source states it directly. |
| **Unknown** | Available evidence does not establish the reason. |

A commit or pull request title is a search clue, not proof of motivation. Tests establish expected behavior, but they do not automatically explain why that behavior was chosen.

## Limits

The skill cannot recover intent that was never recorded. Answers depend on the history in the checkout and access to linked discussions; a shallow clone or unavailable source may leave the reason unknown. The skill investigates and explains; it does not modify code.

## Contents

```text
skills/why/
├── SKILL.md
└── references/
    ├── history-research.md
    └── answer-format.md
```

## Contributing

Focused issues and pull requests are welcome. Include a concrete question or example showing how a change improves evidence quality, clarity, or portability. Keep the skill concise and avoid claims its workflow cannot support.

## License

MIT. See [LICENSE](LICENSE).
