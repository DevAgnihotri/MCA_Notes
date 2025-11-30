# Git Notes — Interview-Ready, Simple English

Purpose: A single file to learn Git for interviews. Clear definitions, command examples, short explanations (8th-grade level), and interview tips.

## Table of Contents

1. [Introduction to Version Control](#1-introduction-to-version-control)
2. [Git Basics](#2-git-basics)
3. [Creating and Initializing Repositories](#3-creating-and-initializing-repositories)
4. [Basic Git Commands](#4-basic-git-commands)
5. [Branching and Merging](#5-branching-and-merging)
6. [Remote Repositories (GitHub / GitLab)](#6-remote-repositories-github--gitlab)
7. [Working with Changes](#7-working-with-changes)
8. [Undoing and Reverting Changes](#8-undoing-and-reverting-changes)
9. [Stashing](#9-stashing)
10. [Tagging and Versioning](#10-tagging-and-versioning)
11. [Git Ignore](#11-git-ignore)
12. [Collaboration in GitHub](#12-collaboration-in-github)

---

## 1. Introduction to Version Control

What is a Version Control System (VCS)?

- A VCS records changes to files over time so you can recall specific versions later.
- Think of it like a time machine for your project: you can go back, compare, or restore.

Importance of Version Control

- Saves history so mistakes can be undone.
- Lets teams work together without overwriting each other's work.
- Enables experimentation with branches.

Types of VCS

- Local: keeps history on your computer (simple, old-school).
- Centralized (CVCS): one central server (e.g., SVN). Everyone pulls and pushes to that server.
- Distributed (DVCS): every developer has a full copy of the repository (history + code) — Git is DVCS.

Difference between Git and other VCS (like SVN)

- Git is distributed: every clone has full history; SVN is centralized: history lives on server.
- Git is generally faster for branching and merging.
- SVN handles some permissions and central workflows more directly.

Difference between Git and GitHub

- Git is a tool on your computer to manage history.
- GitHub is a web service to host Git repositories, show code, make PRs, and collaborate.

Interview tip: say "Git = tool; GitHub = hosting/service" and give a one-line example.

---

## 2. Git Basics

What is Git and how it works (simple)

- Git tracks snapshots (commits) of your project. Each commit points to a tree of files and a parent commit(s).
- Basic flow: change files → stage them → commit → push to remote.

Installing Git

- Windows: download from `https://git-scm.com` or use package manager.
- macOS: `brew install git` or installer.
- Linux: `sudo apt install git` or distro package.

Git Configuration (important commands)

- Set name: `git config --global user.name "Your Name"`
- Set email: `git config --global user.email "you@example.com"`
- See settings: `git config --list`

Explain what these do: Git stores who made a commit; name + email appear in history.

Understanding areas in Git

- Working Directory: your actual project files you edit.
- Staging Area (index): files you marked to go into the next commit (`git add`).
- Local Repository: commits stored on your machine (`.git` folder).

Git workflow overview

- Working Directory → (git add) → Staging Area → (git commit) → Local Repository → (git push) → Remote

Quick example (create a commit):

```powershell
git add README.md
git commit -m "Add README"
git push origin main
```

---

## 3. Creating and Initializing Repositories

`git init`

- Creates a new Git repository in the current folder by creating a `.git` folder.
- Example:

```powershell
mkdir myproj; cd myproj
git init
```

- After `git init`, the folder is now under version control.

`git clone`

- Copies a remote repository (full history) to your machine.
- Example:

```powershell
git clone https://github.com/owner/repo.git
```

The `.git` folder and its role

- `.git` stores all commits, branches, tags, config — the entire history. Don't delete it unless you want to remove Git from the folder.

Repository states

- Untracked: file Git does not know about yet.
- Modified: tracked file changed since last commit.
- Staged: file added to the staging area by `git add`.
- Committed: snapshot saved in local history.

Check states with:

```powershell
git status
```

---

## 4. Basic Git Commands

`git status` — shows modified, staged, and untracked files.

`git add` — stage files for commit.

- `git add file.txt` stages a single file.
- `git add .` stages all changed files.

`git commit` — save staged files to the local repo.

- `git commit -m "message"`
- Use `-a` to auto stage tracked files: `git commit -am "update"` (does not add new untracked files).

`git log` and `git log --oneline`

- Shows commit history.
- `--oneline` shows short ids + message for quick view.

`git diff` — shows what changed

- `git diff` (working vs staged), `git diff --staged` (staged vs last commit).
- Compare commits: `git diff commit1 commit2`

`git show` — show a commit details

- `git show <commit-id>` shows diff and metadata for that commit.

`git rm`, `git mv`

- `git rm file` removes a file and stages removal.
- `git mv old new` renames and stages the change.

`git help` — get help: `git help <command>` or `git <command> --help`.

Examples:

```powershell
git add index.html
git commit -m "Add index page"
git log --oneline
git diff HEAD~1 HEAD
```

---

## 5. Branching and Merging

What is a branch?

- A branch is a pointer to a commit. It lets you work on isolated changes without affecting `main`.
- Default branch is often `main` or `master`.

Why use branches?

- Keep features separate, work on bugs safely, review changes before merging.
- Use short-lived branches per feature or bug.

Common commands

- `git branch` — list branches.
- `git branch <branch_name>` — create a branch.
- `git checkout <branch_name>` — switch to a branch.
- `git checkout -b <branch_name>` — create and switch.
- `git merge <branch_name>` — merge changes from that branch into current branch.
- `git branch -d <branch_name>` — delete a branch.

Example workflow:

```powershell
git checkout -b feature/login
# edit files
git add .
git commit -m "add login"
git checkout main
git merge feature/login
git branch -d feature/login
```

Merge Conflicts

- Causes: same lines changed in both branches or file deletions vs edits.
- How to resolve manually:
  1. Open the conflicting file; Git marks conflict areas with `<<<<<<<`, `=======`, `>>>>>>>`.
  2. Edit to pick or combine changes.
  3. `git add` the resolved file and `git commit`.

Fast-forward vs Non-fast-forward merges

- Fast-forward: the target branch had no new commits, so branch pointer moves forward (no merge commit).
- Non-fast-forward: both branches have new commits — Git creates a merge commit (or you rebase).

Interview tip: explain both and when they occur; mention `git merge --no-ff` to always create merge commits.

---

## 6. Remote Repositories (GitHub / GitLab)

Adding remote

- `git remote add origin <url>` — link local repo to remote named `origin`.
- View remotes: `git remote -v`.

Pushing code

- `git push -u origin main` — push local `main` and set upstream.
- After upstream set: `git push` pushes current branch.

Pulling code

- `git pull origin main` — fetch + merge remote changes into current branch.

Fetching

- `git fetch` downloads commits from remote but does not merge them. Use to inspect remote changes safely.

Difference between `git fetch` and `git pull`

- `git fetch`: get remote updates to refs (safe, no merge).
- `git pull`: fetch + merge (or rebase) — changes your working tree.

Cloning from remote

- `git clone <repo-url>` copies the remote repo to local with remote `origin` set.

Examples:

```powershell
git clone https://github.com/owner/repo.git
git remote -v
git fetch origin
git pull origin main
git push origin feature/xyz
```

---

## 7. Working with Changes

Comparing commits

- `git diff <commit1> <commit2>` — shows changes between commits.
- Compare branches: `git diff main feature/xyz`.

Viewing file history

- `git log -- <file>` shows commits that changed a specific file.

Viewing specific commit details

- `git show <commit-id>` for the diff and commit message.

Example:

```powershell
git diff HEAD~2 HEAD
git log --oneline -- path/to/file
```

---

## 8. Undoing and Reverting Changes

`git checkout -- <filename>` — discard local changes in working directory (reverts to last commit for tracked files).

`git reset <file>` — unstage a staged file (keeps changes in working directory).

Reset types (important!)

- `git reset --soft HEAD~1` — move HEAD back one commit but keep changes staged (index intact).
- `git reset --mixed HEAD~1` — default: move HEAD back and unstage changes (changes remain in working dir).
- `git reset --hard HEAD~1` — move HEAD back and discard all changes (dangerous — deletes work).

`git revert <commit_id>` — create a new commit that undoes the changes from the specified commit (safe for shared history).

Difference between `reset` and `revert`

- `reset` rewrites history (moves branch pointer). Avoid on public branches.
- `revert` preserves history and adds a new commit that undoes changes — safe for shared branches.

Examples:

```powershell
git reset --soft HEAD~1
git revert ab12cd34
```

---

## 9. Stashing

`git stash` — save current working directory and index changes to a stack and revert working dir to HEAD.

Commands

- `git stash` — stash changes.
- `git stash list` — list saved stashes.
- `git stash apply` — apply stash to working dir (keeps stash entry).
- `git stash pop` — apply stash and remove it from list.
- `git stash drop` — remove a stash.

When to use stashing

- When you need to switch branches quickly but have unfinished changes.

Example:

```powershell
git stash
git checkout main
git stash pop
```

---

## 10. Tagging and Versioning

Creating tags

- Lightweight: `git tag v1.0`
- Annotated: `git tag -a v1.0 -m "Release 1.0"` (stores message and author info)

Listing tags

- `git tag`

Pushing tags

- `git push origin v1.0` or `git push --tags` to push all tags.

Deleting tags

- Locally: `git tag -d v1.0`
- Remotely: `git push origin :refs/tags/v1.0`

Example:

```powershell
git tag -a v1.0 -m "First release"
git push origin v1.0
```

---

## 11. Git Ignore

Purpose of `.gitignore`

- Tell Git which files or patterns to ignore (e.g., build files, secrets, env files).

How to create `.gitignore`

- Create file named `.gitignore` in repository root and add patterns.

Common patterns:

```
*.log
__pycache__/
.env
node_modules/
```

Global `.gitignore` configuration

- `git config --global core.excludesfile ~/.gitignore_global`
- Add patterns to that file for all your repos.

Tip: if a file is already tracked, adding to `.gitignore` won't remove it. You must `git rm --cached <file>` first.

---

## 12. Collaboration in GitHub

Forking a repository

- Fork = copy someone else's repo to your GitHub account so you can work on it.

Cloning a forked repo

- Clone your fork locally: `git clone https://github.com/you/repo.git`
- Add upstream remote to track original:

```powershell
git remote add upstream https://github.com/original/repo.git
git fetch upstream
git merge upstream/main
```

Creating branches for features

- Create a branch for each feature or bug fix: `git checkout -b feature/xyz`

Committing and pushing changes

- Commit locally, push to your fork: `git push origin feature/xyz`

Creating Pull Requests (PRs)

- On GitHub open a PR from your fork/branch into the original repo's branch.
- PR description: short summary, what changed, screenshots if UI, tests run.

Code Review and Merge process

- Reviewers comment; you update the branch and push again.
- Once approved, the PR is merged (Squash, Merge commit, or Rebase depending on project rules).

Resolving conflicts in PRs

- If PR cannot be merged automatically, fetch upstream and rebase or merge locally, resolve conflicts, and push.

GitHub Issues and Wiki

- Issues: track bugs, tasks, feature requests.
- Wiki: project documentation.

---

## Final interview tips — Git

- Explain areas (working directory, staging area, repository) clearly.
- When discussing `reset` vs `revert`, mention safety for shared branches.
- For branching, show a simple example and explain merge conflict resolution steps.
- Practice common commands until they are second nature.

---

If you want, I can now:

- Create a short `git_cheatsheet.md` one-page file with the most used commands only.
- Add exercises with step-by-step expected outputs for hands-on practice.
- Create PowerShell scripts to automate repo initialization and sample workflow.

Tell me which of these you'd like next and I'll continue.
