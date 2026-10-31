# why

<p align="center">
  <img src="assets/why.svg" alt="why: a magnifying glass around a question mark" width="96" />
</p>

**Ask why a code path exists—not only what it does.**

`/why` is a Cursor skill for investigating the reasoning behind unfamiliar code. It connects the code that runs today to its tests and, when available, the commit, pull request, issue, or design note that explains how it got there. It clearly separates documented intent from evidence-based inference and unknowns.

## Ask questions like

- `/why does this retry loop stop after five attempts?`
- `/why was this compatibility branch added?`
- `/why does this state update use a layout effect?`

The skill first establishes current behavior. For a runtime question, it follows the relevant code path. For a design question, it traces the change and looks for the original discussion. Its answer is concise and points back to the sources it used.

## How it works

1. **Read the code that exists now.** Follow the smallest relevant path through implementation, callers, and tests.
2. **Find when the choice entered the code.** Inspect the relevant diff and surrounding history, including renames when needed.
3. **Look for the decision behind the change.** Follow links to pull requests, issues, reviews, and design notes when available.
4. **Report the evidence honestly.** Identify what is documented, what is inferred, and what the repository cannot establish.

| Evidence label | Meaning |
| --- | --- |
| **Documented** | A source explicitly states the reason or constraint. |
| **Inferred** | Specific code or history supports the explanation, but no source states it directly. |
| **Unknown** | Available evidence does not establish the reason. |

A commit title is a lead, not proof of motivation. Current tests establish behavior; they do not automatically establish why that behavior was chosen.

## Install

### Add it as a Cursor skill

Copy the skill folder into your project’s Cursor skills directory:

```sh
mkdir -p .cursor/skills
cp -R skills/why .cursor/skills/
```

Or install it for your user by copying `skills/why` into `~/.cursor/skills/why`. In Cursor Agent, type `/why` and choose the skill, or ask a matching question in natural language. Cursor discovers skills from project and user skill directories; see the [Cursor skills guide](https://cursor.com/docs/skills).

### Load it as a local Cursor plugin

This repository also includes a Cursor plugin manifest. To try the plugin locally, copy `.cursor-plugin` and `skills` into `~/.cursor/plugins/local/why`, restart Cursor (or reload the window), then confirm the skill appears in Customize. See [Cursor’s local plugin instructions](https://cursor.com/docs/plugins#test-plugins-locally).

```sh
mkdir -p ~/.cursor/plugins/local/why
cp -R .cursor-plugin skills assets ~/.cursor/plugins/local/why/
```

The plugin has **not** been submitted to the Cursor Marketplace. The skill itself is plain Markdown in the Agent Skills `SKILL.md` format; the manifests package it for Cursor.

## Scope and limits

`/why` investigates rationale; it does not prove intent that was never recorded or change code on its own. Results depend on the history available in the checkout and on access to remote discussions. A shallow clone, missing PR links, or unavailable network may leave the answer **Unknown**.

## Repository layout

```text
.cursor-plugin/                 Cursor plugin and marketplace manifests
skills/why/SKILL.md              Main workflow and evidence rules
skills/why/references/           History research and answer guidance
assets/why.svg                   Plugin icon
```

## Contributing

Issues and focused pull requests are welcome. Please include a concrete question or example that shows how a change improves evidence quality, clarity, or portability. Keep the skill concise and avoid adding claims that the workflow cannot support.

## License

MIT. See [LICENSE](LICENSE).
