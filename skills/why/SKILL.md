---
name: why
description: Investigate why code behaves or is structured a certain way. Use when someone asks why a branch, guard, workaround, API, dependency, test, or design choice exists, especially when Git history or project discussions may explain the intent.
---

# Why

Explain the rationale behind a code choice with evidence. Build a short, traceable account from the code that exists now and the history that led to it. Keep observed behavior, documented intent, and inference distinct.

## Workflow

1. **Scope the question.** Identify the symbol, behavior, or design choice and the smallest relevant code path. Ask one concise follow-up only when the target is genuinely ambiguous.
2. **Read the current code.** Inspect the implementation, callers, nearby comments, and relevant tests. Establish what the code does today before explaining why.
3. **Trace the change.** Use repository history to find when and how the choice entered the code. Read the full diff and surrounding commits. Useful commands and search strategies are in [history research](references/history-research.md).
4. **Look for intent.** Follow issue, pull request, design note, or review links from the commit or repository. Prefer the author’s stated rationale and discussion over assumptions based on code shape.
5. **Explain with calibrated claims.** Give the most supported reason, cite file paths and commit/PR/issue identifiers or links, and separate documented rationale from your own inference. If history does not say why, say that plainly.

## Evidence rules

- Treat current code and tests as evidence of current behavior, not automatically as evidence of original intent.
- A commit message is a clue. Read the diff and, if available, the linked discussion before attributing motivation.
- Do not turn temporal correlation into causation. A change that followed a bug report is not necessarily the fix for that report unless the evidence connects them.
- Label conclusions as **Documented**, **Inferred**, or **Unknown**. Use “inferred” only when concrete evidence supports the explanation; do not fill gaps with a plausible story.
- If a link or remote history is unavailable, say what you could inspect and what remains unavailable. Never imply that you read a source you could not access.
- Keep investigation proportional. Stop when the question is answered with adequate evidence, or when the remaining explanation would be speculation.

## Response shape

Use the format in [answer format](references/answer-format.md). For a simple question, answer in a few sentences; expand only when the code path or history needs it.
