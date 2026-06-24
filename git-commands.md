# Git: Complete Reference Guide & Cheat Sheet

This guide provides a comprehensive list of Git commands, ranging from repository setup and local workflow commands to collaboration, remote management, undoing changes, and advanced troubleshooting.

---

## 🚀 Connecting to Your Repository

To initialize Git in this directory and push these system design files to your remote repository (`https://github.com/Thilina-Samarasinghe/system-design.git`), run the following commands in your terminal:

```bash
# 1. Initialize a local Git repository
git init

# 2. Add all files in the directory to the staging area
git add .

# 3. Commit the files with a descriptive message
git commit -m "Initial commit: Added system design guide and documentation"

# 4. Rename the default branch to 'main'
git branch -M main

# 5. Link the local repository to your remote GitHub repository
git remote add origin https://github.com/Thilina-Samarasinghe/system-design.git

# 6. Push the code to GitHub (upstream)
git push -u origin main
```

---

## 📂 Git Commands Quick Reference

### 1. Setup & Configuration
Configure your identity and check system settings.
*   `git config --global user.name "Your Name"`: Set your commit username.
*   `git config --global user.email "your.email@example.com"`: Set your commit email.
*   `git config --global core.editor "code --wait"`: Set the default text editor (e.g., VS Code).
*   `git config --list`: Show all current configurations.
*   `git init`: Initialize a new local Git repository in the current folder.
*   `git clone <repo-url>`: Clone an existing repository from a remote server.

### 2. Snapshotting & Staging
Manage modifications, stage changes, and create commits.
*   `git status`: Show the state of the working directory and staging area (tracked/untracked files).
*   `git add <file>`: Add a specific file to the staging area (stage it for commit).
*   `git add .`: Add all modified and untracked files to the staging area.
*   `git commit -m "commit message"`: Commit staged changes with a one-line message.
*   `git commit -am "commit message"`: Stage all tracked modifications and commit in one command.
*   `git diff`: View changes made in the working directory that are not yet staged.
*   `git diff --staged`: View changes made to staged files relative to the last commit.
*   `git rm <file>`: Remove a file from the working directory and stage the deletion.
*   `git rm --cached <file>`: Remove a file from tracking but keep it locally in the file system.
*   `git mv <old-path> <new-path>`: Move or rename a file/folder and stage the change.

### 3. Branching & Merging
Create, switch, list, and merge isolated lines of development.
*   `git branch`: List all local branches (highlighting the active branch).
*   `git branch -a`: List all local and remote-tracking branches.
*   `git branch <branch-name>`: Create a new branch.
*   `git checkout <branch-name>`: Switch to an existing branch.
*   `git switch <branch-name>`: Modern alternative to checkout for switching branches.
*   `git checkout -b <branch-name>`: Create a new branch and switch to it immediately.
*   `git switch -c <branch-name>`: Modern alternative to create and switch branches.
*   `git merge <branch-name>`: Merge the specified branch's history into the current active branch.
*   `git branch -d <branch-name>`: Delete a local branch (safely checks if changes are merged).
*   `git branch -D <branch-name>`: Force-delete a branch even if it has unmerged changes.

### 4. Sharing & Collaboration (Remotes)
Sync your local history with remote servers like GitHub, GitLab, or Bitbucket.
*   `git remote -v`: List all configured remote repositories and their URLs.
*   `git remote add <name> <url>`: Add a new remote repository (typically named `origin`).
*   `git remote remove <name>`: Remove a configured remote repository.
*   `git fetch <remote>`: Download all branches and updates from the remote without merging them.
*   `git pull <remote> <branch>`: Fetch remote updates and automatically merge them into the active branch.
*   `git push <remote> <branch>`: Upload local commits to the specified remote branch.
*   `git push -u origin <branch>`: Push local commits and set the remote branch as the default upstream target.

### 5. Inspecting History & Commits
Review the commits, history details, and who modified what.
*   `git log`: Show a chronological history of commits.
*   `git log --oneline`: Show commit history in a condensed, one-line format.
*   `git log --graph --oneline --all`: Show a visual ASCII branch diagram of all commits and branches.
*   `git show <commit-hash>`: Show metadata and code diff of a specific commit.
*   `git blame <file>`: Show who wrote/modified each line of a file and when (ideal for debugging).

### 6. Stashing (Temporary Drafts)
Temporarily save uncommitted changes without committing them, leaving a clean workspace.
*   `git stash` or `git stash push`: Stash your current modifications (both staged and unstaged).
*   `git stash -u`: Stash changes including untracked files.
*   `git stash list`: List all stashed changes.
*   `git stash pop`: Apply the most recent stash and remove it from the stash list.
*   `git stash apply`: Apply the most recent stash but keep it in the stash list.
*   `git stash drop`: Delete the most recent stash.
*   `git stash clear`: Delete all stashed items.

### 7. Undoing & Correcting History
Recover from mistakes, rollback changes, and rewrite history.
*   `git checkout -- <file>`: Discard local changes in the working directory (restore file to last commit).
*   `git restore <file>`: Modern alternative to discard local changes in a file.
*   `git restore --staged <file>`: Unstage a file, keeping its local changes.
*   `git commit --amend -m "new message"`: Replace the last commit with a new commit (updates message or adds newly staged files).
*   `git revert <commit-hash>`: Create a new commit that applies the exact opposite changes of a target commit (safest way to undo shared history).
*   `git reset --soft <commit-hash>`: Move the current branch pointer back to a specific commit, keeping all modified files staged in your workspace.
*   `git reset --mixed <commit-hash>` (Default): Move branch pointer back, keep modifications unstaged in the workspace.
*   `git reset --hard <commit-hash>`: **CRITICAL**: Move branch pointer back and discard all changes in both the staging area and working directory.
*   `git clean -fd`: Remove all untracked files and directories from the working directory.

### 8. Advanced Git Operations
Advanced workflows for troubleshooting and picking commits.
*   `git cherry-pick <commit-hash>`: Copy a specific commit from another branch and apply it to the current branch.
*   `git rebase <branch-name>`: Re-apply commits on top of another base branch (keeps a linear history).
*   `git reflog`: View a log of all actions taken in the repository (e.g., switching branches, resetting). Crucial for recovering "lost" commits.
*   `git tag <tag-name>`: Create a lightweight tag/label at the current commit (e.g., `v1.0.0`).
