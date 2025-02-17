# Git Partial Commit Guide Using `git add -p`

When working on a project, you might find yourself making changes that belong to different logical units or tasks. Instead of committing all changes at once, you can use `git add -p` to stage only specific parts of your changes. This allows for cleaner, more focused commits.

## 1. Check Your Current Status

Before starting, check the status of your working directory to see what changes have been made:

```bash
git status
```

This will show you which files have been modified, added, or deleted.

## 2. Start Interactive Staging

To begin interactively staging changes, use:

```bash
git add -p
```

Git will present you with each change in your working directory, one at a time, and prompt you for an action.

## 3. Understand the Prompt Options

For each change, you'll see a diff and a prompt with several options:

- `y` – stage this hunk
- `n` – do not stage this hunk
- `q` – quit; do not stage this hunk nor any of the remaining ones
- `a` – stage this hunk and all the remaining ones
- `d` – do not stage this hunk nor any of the remaining ones
- `g` – select a hunk to go to
- `/` – search for a hunk matching the given regex
- `j` – leave this hunk undecided, see the next undecided hunk
- `J` – leave this hunk undecided, see the next hunk
- `k` – leave this hunk undecided, see the previous undecided hunk
- `K` – leave this hunk undecided, see the previous hunk
- `s` – split the current hunk into smaller hunks
- `e` – manually edit the current hunk
- `?` – print help

## 4. Stage Changes

Go through each hunk and decide whether to stage it. Use `s` to split hunks if you want to stage only part of a change. This is useful for large changes where only a portion is relevant to the current commit.

## 5. Review Staged Changes

After staging the desired changes, you can review them with:

```bash
git diff --cached
```

This shows the changes that are staged for the next commit.

## 6. Commit Staged Changes

Once you're satisfied with the staged changes, commit them:

```bash
git commit -m "Your descriptive commit message"
```

## 7. Continue with Remaining Changes

Repeat the process for any remaining changes that need to be committed separately.

## Conclusion

Using `git add -p` allows you to create more meaningful and organized commits by staging only the changes relevant to a specific task or feature. This practice leads to a cleaner project history and makes collaboration easier.