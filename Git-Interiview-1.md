# Git Interview Q&A - Part 01

## 1. Is Git a Distributed or Centralized Version Control System?
Git is a **Distributed Version Control System (DVCS)**, unlike **Centralized Version Control Systems (CVCS)** like SVN or CVS.

- **CVCS**: Stores all versions on a central server; developers need to be connected.
- **DVCS (Git)**: Every developer has a full copy of the repository, allowing offline work.

## 2. How to Commit Changes to a Remote Repository?
Use the following Git commands:
```sh
# Stage changes
git add .

# Commit changes
git commit -m "Your commit message"

# Push changes to remote repository
git push origin main
```

## 3. Difference Between `git fetch` and `git pull`
- `git fetch`: Retrieves the latest changes from the remote but does **not merge** them.
- `git pull`: Retrieves **and merges** the latest changes from the remote.
```sh
git fetch origin
git pull origin main
```

## 4. Difference Between `git merge` and `git rebase`
- `git merge`: Merges changes from one branch into another while keeping history.
- `git rebase`: Moves changes from one branch to another while keeping a **linear history**.
```sh
git merge feature-branch
git rebase feature-branch
```

## 5. Difference Between `.git` and `.gitignore`
- `.git`: Stores metadata, history, and configuration of the repository.
- `.gitignore`: Specifies files that should be ignored by Git.

## 6. What are Pre-Commit and Post-Commit Hooks?
- **Pre-Commit Hook**: Runs before a commit, e.g., checking for security keys.
- **Post-Commit Hook**: Runs after a commit, e.g., sending notifications.

Hooks are located in `.git/hooks/`.

## 7. What is a Webhook?
A webhook triggers an external action (e.g., CI/CD pipeline) when an event occurs in Git.

## 8. How to Pull and Push Changes?
- Pull: `git pull origin main`
- Push: `git push origin main`

## 9. What is `git stash`?
Temporarily saves uncommitted changes.
```sh
git stash       # Save changes
git stash pop   # Retrieve changes
```

## 10. Difference Between `git clone` and `git fork`
- `git clone`: Copies a remote repository to local.
- `git fork`: Creates a personal copy of a repository on GitHub.
```sh
git clone <repo-url>
```

## 11. How to Amend a Commit?
If you need to change the last commit:
```sh
git commit --amend -m "New commit message"
```

## 12. What is `git cherry-pick`?
Applies a specific commit from one branch to another.
```sh
git cherry-pick <commit-hash>
```

## 13. How to Resolve Merge Conflicts?
1. Identify conflicts using `git status`.
2. Manually edit conflicted files.
3. Mark them as resolved:
```sh
git add .
git commit -m "Resolved merge conflict"
```

---
**Easy to Revise, Keep Practicing! 🚀**

