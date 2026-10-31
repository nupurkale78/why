# Researching code history

Use the repository’s own history first. Keep searches scoped to the affected file or symbol, then widen only if needed.

## Find the change

```sh
git log --oneline -- path/to/file
git log -S'interestingExpression' -- path/to/file
git blame -L 40,70 -- path/to/file
git show --stat <commit>
git show <commit> -- path/to/file
```

Read the full patch, not just its subject. Check the parent commit and nearby changes if the patch depends on context. Renames or moved code may require `git log --follow -- path/to/file`.

## Follow references

Look for issue or pull request identifiers in commit messages, merge commits, source comments, and release notes. If project tooling or network access can retrieve the linked discussion, inspect the original report and relevant review comments. Search repository docs and tests for the same behavior or terminology.

Treat each source according to what it can establish:

- **Code and tests:** current behavior and constraints encoded in the repository.
- **Diff and commit:** what changed and the commit author’s stated summary.
- **Issue, pull request, review, design note:** motivation, alternatives, and tradeoffs, when explicitly discussed.
- **Inference:** a reason suggested by evidence but not stated directly. Label it as such.

If remote sources cannot be reached, finish with local evidence and say the discussion was unavailable. Do not manufacture a rationale from a commit title, naming, or surrounding code alone.
