# Researching code history

Start with the smallest useful scope: the affected symbol, file, or behavior. Read the current implementation before using history to explain it.

## Trace a change

```sh
git log --oneline -- path/to/file
git log -S'interestingExpression' -- path/to/file
git log -G'pattern' -- path/to/file
git blame -L 40,70 -- path/to/file
git show --stat <commit>
git show <commit> -- path/to/file
```

- `git log -S` finds commits that change the number of occurrences of a string.
- `git log -G` finds commits whose diff matches a regular expression.
- `git blame` identifies the commit that last changed each line; it does not explain why the line changed.
- Read the complete patch and its parent context. If code moved or the file was renamed, try `git log --follow -- path/to/file` and inspect the earlier path.

## Follow the evidence

Search commit bodies, merge messages, nearby comments, release notes, and repository documentation for issue or pull request references. When a linked discussion is accessible, read the original report and the parts of the review that explain the decision or constraints. A title alone is not enough to establish intent.

Use sources for the claims they can support:

| Source | Supports |
| --- | --- |
| Current implementation and tests | Behavior and constraints represented in the checkout |
| Commit diff and message | What changed and the author’s stated summary |
| Issue, pull request, review, or design note | Motivation and tradeoffs when they are stated explicitly |
| Inference | A reason suggested by concrete evidence but not stated directly |

## Report limits

History may be shallow, a reference may be missing, or a remote discussion may be inaccessible. State the specific limit and what you could inspect. Do not present an inference as a documented reason, or fill a gap with a plausible story. If more than one explanation fits the evidence, say so.
