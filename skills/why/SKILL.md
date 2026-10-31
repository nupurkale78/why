---
name: why
description: Explain why a code path behaves as it does or why a design choice exists. Use when someone asks why a branch, guard, workaround, API, dependency, test, or implementation decision was made, particularly when the answer may be in Git history or project discussions.
---

# Why

Explain why a code path behaves as it does or why a design choice was made. Build a concise, traceable explanation from the current implementation and the history that led to it. Keep observed behavior, documented intent, inference, and missing evidence distinct.

## Workflow

1. **Scope the question.** Identify the symbol, behavior, or design choice and the smallest relevant code path. Ask one concise follow-up only if the target is genuinely ambiguous.
2. **Establish current behavior.** Read the implementation, relevant callers, comments, and tests. If the question is about runtime behavior, trace control flow and important values far enough to explain the observed result. Do not mistake a plausible reading of one line for a complete explanation.
3. **Choose the right history path.** If the question asks why a decision was made, find when it entered the code and inspect the full diff and surrounding commits. For both kinds of question, check history when it may clarify behavior or motivation. See [history research](references/history-research.md).
4. **Find decision evidence.** Follow references to pull requests, issues, reviews, design notes, or release notes. Read the relevant discussion where access permits. Prefer an explicit rationale over assumptions based on code shape.
5. **Write a traceable answer.** State the explanation, cite relevant paths and history links or identifiers, and label the claim as documented, inferred, or unknown. If available evidence does not establish intent, say so directly.

## Evidence rules

- Treat current code and tests as evidence of current behavior, not automatically as evidence of original intent.
- A commit subject or PR title is a search clue, not proof of motivation. Read the diff and linked discussion before attributing a reason.
- Do not turn temporal correlation into causation. A change that followed a bug report is not necessarily the fix for that report unless the evidence connects them.
- Label rationale as **Documented**, **Inferred**, or **Unknown**. Use **Inferred** only when concrete evidence supports the explanation; do not fill gaps with a plausible story.
- Distinguish observable behavior from rationale. Tests may encode expected behavior without explaining why that expectation exists.
- If history is shallow, files moved, or a link is unavailable, say what you inspected and what remains unavailable. Never imply that you read a source you could not access.
- Cite exact repository paths and, when available, line ranges or stable commit/PR/issue links. Keep references close to the claims they support.
- Do not modify code unless the user separately asks for a change. Answer the why question first.
- Keep research proportional. Stop when the explanation is adequately supported, or when further claims would be speculation.

## Response shape

Use [answer format](references/answer-format.md) as a guide, not a rigid template. For a simple question, answer in a few sentences; expand only when the behavior or evidence chain needs it.
