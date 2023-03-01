# Git commands: What is the difference between push, fetch, and pull?

This page describes the `git push`, `git fetch`, and `git pull` commands. These commands require a [remote tracking branch](https://git-scm.com/book/en/v2/Git-Branching-Remote-Branches) for your repository. If there is no remote tracking branch, you will receive an error.

## Git push

The `git push` command sends changes from your local branch to a remote repository. Repositories are often hosted in a centralized location, like [GitHub](https://github.com/).

To push from a specific branch, run `git push origin <branch-name>`, where `<branch-name>` is the name of the branch you want to push changes from (such as `main`).

Pushing your changes to a remote branch gives you the ability to open a pull request. The remote branch will update with your changes after the pull request is merged.

## Git fetch

## Git pull


- `git fetch` - get changes from a remote repo into your tracking branch
- `git pull` - will get changes from a remote branch into your tracking branch and merge them into a local branch

Often `git push` and `git pull` are described as equivalent. This isn't entirely correct, since under the hood `git pull` does two things. This will fail if the remote branch has diverged from your local branch: if not all the commits in the remote branch are in your local branch. When this happens, your local branch needs to be synchronized with the remote branch with git pull or git fetch and git merge.`git fetch` again takes our current branch, and checks to see if there is a tracking branch. If so, it looks for changes in the remote branch, and pulls them into the tracking branch. It does not change your local branch. To do that, you'll need to do `git merge origin/master` (for the "master" branch) to merge those changes into your branch - probably also called "master".`git pull` simply does a `git fetch` followed immediately by `git merge`. This is often what we desire to do, but some people prefer to use git fetch followed by git merge to make sure they understand the changes they are merging into their branch before the merge happens.