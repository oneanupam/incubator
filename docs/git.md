# 📘 Git Commands Reference
This file contains a curated list of essential `git` commands for versioning the code repos efficiently. Useful for daily reference and quick lookups.

## 🔍 Installation
Use the below option to install the git to local system (check the git version using: `git version`).

-   [Git](https://git-scm.com/install/) >= 2.52.0

> [!NOTE]
> See [Installation Steps](https://git-scm.com/install) on how to install Git.

## 🧱 Useful Commands

```bash
# 1. Commands for config management
# Please note, git global configurations are managed in "~/.gitconfig" present in home directory.
git config --global --list # to list the global configurations
git config --global user.name "Your Name" # to add the username for global config
git config --global user.email "your_email@example.com" # to add the user email for global config
git config --global alias.st status # to set the alias for a command in global config

# 2. Commands for repo management
git init # to initialize a repo for using git vcs
git clone <repo-url> # to clone the repository to local

# 1. Commands for branch management
git branch # to list all the local branches
git branch -a # to list all the local and remote branches

git branch <branch-name> # create a new branch from the branch you are currently on
git checkout <branch-name> # switch to a branch
git checkout -b <branch-name> # create anew branch from the branch you are currently on and switch to it

git branch -d <branch_name> # to delete the branch from local
git branch -d <branch_name> -f # to delete the branch forcefully from local
git push <remote> -d <branch_name> # to delete the branch from remote

# 2. Commands for local work
git checkout -- . # to remove the changes from tracked files. if the file is not known, git wont do anything.
git add . # add all the files to staging area. use filename to add specific files.
git reset -- . # remove the changes from staging area and put them back to working directory
git commit -m "commit_message" # to commit the changes locally
git commit --amend -m "updated-message" # to update the last commit message

git log # to see the commit history in detail
git log --oneline -n 5 # to show the top 5 logs in oneline

# 2.1 git revert
# to reverse a commit changes by creating a new revert commit. if the commit is not the HEAD, then there are high chances of merge conflict.
# Safe for shared branches like main, develop, etc. because it doesn't rewrite history.
git revert <commit-id>
# to resolve the merge conflict, use the editor and accept/reject the changes.
# after resolving the conflicts, mark them with "git add/rm <pathspec>", then run "git revert --continue".
# You can instead skip this commit with "git revert --skip".
# To abort and get back to the state before "git revert", run "git revert --abort"

# 2.2 git reset
# all the commit are orphned, hence history is re-written. not safe to use for shared branches like main, dev etc.
# Mixed reset (default, keeps changes unstaged, means changes will be there in working directory)
# Soft reset (keeps changes staged, means u just need to commit, if you want them again)
# Hard reset (deletes changes and local files!)
git reset <commit-id> # to reset till the given commit id. all commits after given commit are removed from branch history.

# Note:
# It's important to understand that "git revert" undoes a single commit whereas "git reset" takes back you to the previous state of a project by removing all subsequent commits after that state.

# One more important thing is that "git reset" will never delete a commit/s, however, commits can become 'orphaned' which means there is no direct path from a ref to access them. These orphaned commits can usually be found and restored using git reflog. Git will permanently delete any orphaned commits after it runs the internal garbage collector. By default, Git is configured to run the garbage collector every 30 days.

# 2.3 git merge
# Git merge and rebase have the same purpose – to converge multiple branches of development. Different branches can be merged into any one branch as long as they belong to the same repository.
git checkout <branch-name> # switch to branch where the commit of ur working branch needs to be merged, say main.

# fast-forward merge: to merge the working branch changes to current branch. if there are no development in base branch (where you are merging the commits), then it would be fast-forward merge.
git merge <working-branch>

# Three-way merge: when both the branches has diverson, in that case, git merge will use an extra commit to tie together the two branches.
# In this case, there are high chances of merge-conflict. merge conflict occurs when two branches you're trying to merge both changed the same part of the same file.
# When such a situation occurs, it stops right before the merge commit so that you can resolve the conflicts manually.
git merge <working-branch>

# 2.4 git rebase
# git rebase rewrites the commits of the branch you are currently on. its not safe to use for shared branches, as it re-writes the histroy.
# please note, if there are no diversion or no unique commits in your branch. rebase would not re-write the history.
# As usual, there could be chance of merge-conflict. hence resolve it first.

# Types of rebase
# 1. Rebase onto another branch
git checkout feature
git rebase main # in this case, all the commits of feature branch will be re-written. assuming that, main has a diversion from feature.

# 2. Rebase interactively (edit, squash, reorder)
# It is a special mode of rebase that lets you edit, reorder, squash, combine, delete, or modify commits before rewriting them.
# This can be used to permanently clean up the commit from a branch
git rebase -i HEAD~5 # this will open the last 5 commits of a branch in an editor and you choose the action (eg: pick, drop, squash) for these commits.

# 2.5 git fetch
# Git fetch and Git pull commands are used to update the local code base.
# The git fetch command imports commits from a remote repository into your local repo. But remember that, the resulting commits are stored as remote tracking branches instead of the normal local branches that we’ve been working with.
git fetch # to only fetch all the new commits of existing branches and new branches from default remote to local repo, that's origin.
git fetch origin master # to only fetch all commits of specified branch i.e. master of remote, origin.
git merge origin/master # to merge the remote changes of master branch to current branch.

# 2.6 git pull (fetch + merge)
git pull # This pulls from the default remote and default branch that your current branch is tracking. Please note, as git pull merges the remote chanegs automatically, there could be a chance of merge-conflict.
git pull origin master # This is explicit. Pull from the origin remote and merge the master branch into your current branch. So if you are on feature branch, it does:

git fetch origin master
git merge origin/master into feature

# 3. Commands for remote work
git push <remote> <branch> # to push the changes of a branch to remote

# 4. Commands for remote management
git remote # to list all the remotes with their short names
git remote -v # to list all the remotes URLs in verbose form
git remote add <short-name> <url> # to add a remote to a repo
git remote remove <short-name> # to remove the remote from a repo
```

## 📌 How to Contribute
Feel free to fork this repo and add your favorite git commands!

## 🔗 References
- https://git-scm.com/cheat-sheet
- https://git-scm.com/docs
