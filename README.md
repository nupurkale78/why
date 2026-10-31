# why

`/why` is a Cursor skill for answering the question behind unfamiliar code: why is it written this way?

It reads the relevant implementation and tests, then traces Git history and linked discussions when useful. It separates direct evidence from plausible explanations and calls out what the available history cannot establish.

## Try it

In Cursor, ask:

```text
/why does this retry loop stop after three attempts?
/why is this state updated in a layout effect?
/why was this validation added?
```

The skill narrows the question, follows the code path, and uses commit history, pull requests, issues, or design notes to look for intent. It reports sources and uncertainty instead of treating a commit title or a guess as proof.

## Install

Install this repository as a Cursor plugin, or copy [`skills/why`](skills/why) into your agent's skills directory. The skill uses the Agent Skills `SKILL.md` format.

## Project structure

```text
.cursor-plugin/   Cursor plugin and marketplace manifests
skills/why/       Skill instructions and focused reference guides
```

## License

MIT. See [LICENSE](LICENSE).
