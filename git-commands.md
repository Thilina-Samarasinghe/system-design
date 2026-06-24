# Git: Complete Reference Guide & Cheat Sheet

This guide provides a comprehensive list of Git commands, ranging from repository setup and local workflow commands to collaboration, remote management, undoing changes, and advanced troubleshooting.


## 📂 Git Commands Quick Reference

### 1. Setup & Configuration
Configure your identity, command line settings, and check configurations.
*   `git config --global user.name "Your Name"`: Sets your commit username.
*   `git config --global user.email "your.email@example.com"`: Sets your commit email.
*   `git config --global core.editor "code --wait"`: Sets the default text editor (e.g., VS Code).
*   `git config --global alias.<shortcut> <command>`: Creates a custom alias (e.g., `git config --global alias.co checkout` lets you run `git co`).
*   `git config --list`: Shows all current Git configurations active on your machine.
*   `git config --show-origin --list`: Shows where each configuration setting was loaded from.
*   `git init`: Initializes a new local Git repository in the current folder.
*   `git clone <repo-url>`: Clones an existing repository from a remote server to your local machine.

### 2. Snapshotting & Staging (Local Workflow)
Manage modifications, stage changes, and create commits.
*   `git status`: Shows the state of the working directory and staging area (staged, unstaged, and untracked files).
*   `git add <file>`: Adds a specific file's changes to the staging area.
*   `git add .` or `git add -A`: Adds all modified, deleted, and untracked files to the staging area.
*   `git add -p`: Interactive staging. Allows you to review and select parts of files to stage (hunks).
*   `git commit -m "message"`: Commits staged changes with a descriptive message.
*   `git commit -am "message"`: Stages all tracked modifications and commits them in one go (skips `git add` for modified files, doesn't add new files).
*   `git diff`: Views changes made in the working directory that are not yet staged.
*   `git diff --staged` or `git diff --cached`: Views changes made to staged files relative to the last commit.
*   `git diff HEAD`: Views all changes since the last commit (staged and unstaged combined).
*   `git rm <file>`: Deletes the file from the working directory and stages the deletion.
*   `git rm --cached <file>`: Removes a file from tracking but keeps it locally on your hard drive.
*   `git mv <old-path> <new-path>`: Moves or renames a file/folder and stages the change.

### 3. Branching & Merging
Create, switch, list, and merge isolated lines of development.
*   `git branch`: Lists all local branches (highlights the active one with `*`).
*   `git branch -r`: Lists all remote tracking branches.
*   `git branch -a`: Lists all local and remote branches.
*   `git branch <branch-name>`: Creates a new branch at the current commit without switching to it.
*   `git checkout <branch-name>`: Switches to the specified branch.
*   `git switch <branch-name>`: Modern, safer alternative to `checkout` for switching branches.
*   `git checkout -b <branch-name>`: Creates a new branch and switches to it immediately.
*   `git switch -c <branch-name>`: Modern alternative to create and switch branches.
*   `git branch -d <branch-name>`: Deletes a local branch safely (will warn you if it has unmerged changes).
*   `git branch -D <branch-name>`: Forces the deletion of a branch even if its changes are unmerged.
*   `git merge <branch-name>`: Merges the history of the specified branch into your current active branch.
*   `git merge --abort`: Aborts a merge process if there are conflicts you do not want to resolve right now.
*   `git branch -m <new-name>`: Renames the current branch.

### 4. Sharing & Collaboration (Remotes)
Synchronize your local history with remote servers like GitHub.
*   `git remote -v`: Lists all configured remote repositories and their fetch/push URLs.
*   `git remote add <name> <url>`: Adds a new remote repository connection (typically named `origin`).
*   `git remote rename <old-name> <new-name>`: Renames a remote server handle.
*   `git remote remove <name>`: Removes a remote repository link.
*   `git fetch <remote>`: Downloads all branches and updates from the remote without merging them into your working files.
*   `git pull <remote> <branch>`: Fetches remote updates and automatically merges them into the active branch.
*   `git pull --rebase`: Fetches remote updates and applies your local commits on top of the remote changes (rebase instead of merge).
*   `git push <remote> <branch>`: Uploads local commits to the remote repository.
*   `git push -u origin <branch>`: Pushes changes and sets the remote branch as the default upstream target for subsequent pulls/pushes.
*   `git push origin --delete <branch-name>`: Deletes a branch from the remote repository.
*   `git remote prune <remote>` or `git fetch -p`: Deletes local references to remote branches that have been deleted on the server.

### 5. Inspecting History & Logs
Review the commit timeline, locate specific updates, and identify authors.
*   `git log`: Shows a chronological history of commits.
*   `git log --oneline`: Shows commit history in a highly condensed, one-line format.
*   `git log -n <number>`: Limits the log output to a specific number of recent commits.
*   `git log --grep="search pattern"`: Searches commit messages for matching text.
*   `git log -S "code snippet"`: Searches for commits that added or removed a specific string of code.
*   `git log --author="Developer Name"`: Filters commits by a specific author.
*   `git log --graph --oneline --all`: Displays an ASCII branch graph of all commits and branches.
*   `git show <commit-hash>`: Displays the details and code diff of a specific commit.
*   `git blame <file>`: Shows who wrote/modified each line of a file, when, and in which commit.

### 6. Stashing (Temporary Drafts)
Temporarily save uncommitted changes without committing them, leaving a clean workspace.
*   `git stash` or `git stash push`: Stashes your current dirty working changes (both staged and unstaged).
*   `git stash -u` or `git stash --include-untracked`: Stashes untracked files along with modified files.
*   `git stash list`: Lists all stashed changes in chronological order.
*   `git stash pop`: Applies the most recent stash and deletes it from the stash list.
*   `git stash apply`: Applies the most recent stash but keeps it in the stash list for reuse.
*   `git stash apply stash@{2}`: Applies a specific stash from the list.
*   `git stash drop`: Deletes the most recent stash.
*   `git stash clear`: Deletes all stashed items.

### 7. Undoing & Correcting Mistakes
Recover from mistakes, rollback changes, and rewrite commit history safely.
*   `git checkout -- <file>`: Discards local unstaged modifications in the working directory (restores to last commit).
*   `git restore <file>`: Modern, clean alternative to discard local modifications.
*   `git restore --staged <file>`: Unstages a file, keeping the local edits in your workspace.
*   `git commit --amend -m "new message"`: Replaces the last commit with a new commit (used to change commit messages or add new files to the last commit).
*   `git revert <commit-hash>`: Generates a new commit that applies the exact opposite changes of a target commit. Safest way to undo shared remote history.
*   `git reset --soft <commit-hash>`: Moves the current branch head back to a specific commit, keeping all modified changes staged in your workspace.
*   `git reset --mixed <commit-hash>` (Default): Moves branch head back, keeps changes in your workspace but unstages them.
*   `git reset --hard <commit-hash>`: **CRITICAL**: Resets branch head back to a specific commit and discards all local modifications (staged and unstaged). Destructive action.
*   `git clean -fd`: Removes all untracked files (`-f` for force) and directories (`-d`) from the working directory.

### 8. Advanced Git Operations
Advanced workflows for troubleshooting, tagging, and linear history.
*   `git cherry-pick <commit-hash>`: Copies a specific commit from another branch and applies it onto the current branch.
*   `git rebase <branch-name>`: Re-applies your current branch commits on top of another base branch. Useful for maintaining a linear, clean history.
*   `git rebase --continue` / `git rebase --abort`: Coordinates the rebase process if you encounter conflicts.
*   `git reflog`: Shows a history of all local repository updates (branch switches, commits, resets). Crucial for finding "lost" commits.
*   `git tag <tag-name>`: Creates a lightweight tag at the current commit (e.g., `v1.0.0`).
*   `git tag -a <tag-name> -m "tag message"`: Creates an annotated tag with metadata (author, date, message).
*   `git push origin <tag-name>`: Pushes a specific tag to the remote repository.
*   `git push origin --tags`: Pushes all local tags to the remote repository.

### 9. Submodules & External Projects
Manage nested repositories inside your main repository.
*   `git submodule add <repo-url> <path>`: Adds an external Git repository as a submodule inside a specific path.
*   `git submodule init`: Initializes submodules listed in the `.gitmodules` configuration file.
*   `git submodule update` or `git submodule update --init --recursive`: Downloads and updates nested submodules to the commit specified by the parent repository.

### 10. Large File Storage (LFS)
Manage large assets (videos, database dumps, design files) efficiently.
*   `git lfs install`: Initializes the Git LFS extension in your local environment.
*   `git lfs track "*.mp4"`: Configures Git LFS to track large MP4 files (creates/updates `.gitattributes`).
*   `git lfs ls-files`: Lists files currently tracked by Git LFS.

### 11. Git Worktrees (Advanced Workspace Management)
Work on multiple branches of the same repository simultaneously in different folders without switching back and forth.
*   `git worktree add <path> <branch-name>`: Checks out a branch in a separate directory (`<path>`), allowing you to run code or make changes in parallel.
*   `git worktree list`: Lists all active worktrees linked to the repository.
*   `git worktree prune`: Cleans up links to worktree directories that have been manually deleted from disk.

---

## 💡 Important Git Conceptual Differences

### Merge vs. Rebase
*   **Merge**: Combines two branches with a dedicated "merge commit" that joins histories. It preserves the exact chronological order of events but can result in a messy branch graph.
*   **Rebase**: Moves your local commits to sit on top of the latest changes from the base branch. It rewrites history to create a clean, linear commit graph but shouldn't be used on public, shared branches.

### Soft vs. Mixed vs. Hard Reset
*   `--soft`: Undo commit $\rightarrow$ Keep changes in **Staging Area**.
*   `--mixed`: Undo commit $\rightarrow$ Keep changes in **Working Directory** (unstaged).
*   `--hard`: Undo commit $\rightarrow$ **Discard** all changes (both staged and unstaged).
