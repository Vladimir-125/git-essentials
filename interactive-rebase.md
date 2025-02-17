# Git Rebase Interactive Guide

## 1. Check Your Current Branch and Status

Before starting a rebase, verify your current branch and check the status of your working directory:

```bash
git status
```

This will show the current branch and whether there are any uncommitted changes.

## 2. View Commit History

To determine which commits need modification and how many commits to include in the rebase, use:

```bash
git log --oneline
```

This command displays a condensed commit history with commit hashes and messages:

```
abc1234 Fix bug in authentication
def5678 Add new logging feature
ghi9101 Update documentation
jkl1121 Initial commit
```

Count the number of commits you want to modify, then proceed to rebase.

## 3. Start Interactive Rebase

To edit the last N commits (e.g., 5 commits), run:

```bash
git rebase -i HEAD~5
```

## 4. Choose Actions for Each Commit

An editor will open with a list of commits:

```
pick abc1234 Fix bug in authentication
pick def5678 Add new logging feature
pick ghi9101 Update documentation
pick jkl1121 Initial commit
```

Replace `pick` with one of the following actions:
- `reword` – change the commit message
- `edit` – modify files in the commit
- `squash` – merge commit with the previous one
- `fixup` – similar to squash but discards the commit message
- `drop` – remove the commit
- Rearrange commits by changing the order of lines

Example:

```
pick abc1234 Fix bug in authentication
reword def5678 Add new logging feature (change commit message)
edit ghi9101 Update documentation (modify files)
squash jkl1121 Initial commit (merge with previous commit)
```

## 5. Editing a Commit (if edit is chosen)

If you selected `edit`, Git will stop at that commit, allowing you to:
- Modify files (`git add .`)
- Amend the commit (`git commit --amend`)
- Continue rebase (`git rebase --continue`)

To cancel the rebase at any point:

```bash
git rebase --abort
```

## 6. Finish and Force Push

After completing the rebase, if you’ve already pushed the branch before, force push it:

```bash
git push -f origin my_branch
```


**Warning!** Use `push -f` with caution, as it rewrites history and can disrupt others working on the same branch, so it is not recommended for shared or main branches.

## 7. Rebase Current Branch on Top of Another Branch

To rebase your current branch on top of another branch, use:

```bash
git rebase -i other_branch
```

This command will apply the commits from your current branch on top of `other_branch`. You can then resolve any conflicts and continue the rebase process as described in the previous steps.

**Note:** Before rebasing to keep your branch up-to-date with the target branch, ensure that the target branch is updated locally. You can do this by checking out the target branch and pulling the latest changes:

```bash
git checkout other_branch
git pull origin other_branch
```

Alternatively, you can rebase directly onto the remote branch to ensure you have the latest updates:

```bash
git rebase -i origin/other_branch
```

Rebasing onto another branch can be useful for keeping your branch up-to-date with the latest changes from the target branch. However, be cautious as it rewrites history, which can disrupt others working on the same branch.

## Conclusion
## Conclusion

Interactive rebasing is a powerful tool in Git that allows you to clean up your commit history, modify commit messages, and reorder or combine commits. By understanding how to use interactive rebase effectively, you can maintain a more organized and meaningful project history.

Remember to always be cautious when rewriting history, especially on shared branches, as it can affect others working on the same project. Use `git rebase` to keep your branches up-to-date and to integrate changes smoothly, but always communicate with your team to avoid conflicts.

With these practices, you can leverage the full potential of Git's interactive rebase to enhance your workflow and collaboration.
