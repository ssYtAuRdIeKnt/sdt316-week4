## Task 1 - Merge

The merge commit has two parents. In the graph, the history splits into separate main and feature-merge paths and then joins again at the merge commit. This shows that the history forked and later rejoined.

## Task 2 - Rebase

### Why did the SHA change?

The SHA changed because rebase created a new commit with a different parent. A commit hash depends on the commit contents, metadata, and parent commit.

### Why was the normal push rejected?

The normal push was rejected because rebase rewrote the branch history. The remote branch still contained the old commit, so the new history was not a fast-forward update.

### How does this graph differ from Task 1?

Task 1 contains a visible fork and a merge commit with two parents. Task 2 has linear history because the feature commit was rebased on top of main and then merged using a fast-forward.

### Why is rebasing a branch already pulled by a teammate risky?

Rebase changes commit SHAs and rewrites history, so teammates with the old history can end up with diverging branches and conflicts.

## Task 3 - Curated History and Pull Request

### Merge strategies

**Create a merge commit:** preserves the branch commits and creates a new merge commit with two parents. Task 1 produced this shape.

**Squash and merge:** combines all pull request commits into one new commit on main.

**Rebase and merge:** reapplies the branch commits on top of main and produces linear history without a merge commit. Task 2 produced this shape.

Squash and merge would destroy the three curated commits because it would replace them with one combined commit.

### Why were two commits removed with fixup?

The two fixup commits were only corrections to the changes directly before them, so they had no useful independent meaning. The remaining three commits represent separate coherent changes: project notes, configuration, and usage documentation.
