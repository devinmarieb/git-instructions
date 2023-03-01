# Git commands: What is the difference between push, fetch, and pull?

This page describes the `git push`, `git fetch`, and `git pull` commands. These commands require a [remote tracking branch](https://git-scm.com/book/en/v2/Git-Branching-Remote-Branches) for your repository. If there is no remote tracking branch, you will receive an error.

## Git push

The `git push` command sends changes from your local branch to a remote repository. Repositories are often hosted in a centralized location, like [GitHub](https://github.com/).

To push from a specific branch, run `git push origin <branch-name>`, where `<branch-name>` is the name of the branch you want to push changes from (such as `main`).

Pushing your changes to a remote branch gives you the ability to open a pull request. The remote branch will update with your changes after the pull request is merged.

It is possible a remote branch exists, but has diverged from your local branch. If this is the case, you will receive an error like the example below:

<!-- Find example of git error -->

This error indicates that the commits in the remote branch are not found in your local branch. When this happens, your local branch needs to sync with the remote branch. You can do this by running `git fetch` and `git merge`, or `git pull`.

## Git fetch

The `git fetch` command fetches changes from a remote repository into your tracking branch, but it does _not_ merge the changes. This command is helpful if you would like to view the changes you are pulling down to your local branch before you merge them into your work.

To fetch from a specific branch, run `git fetch origin <branch-name>`, where `<branch-name>` is the name of the branch you want to fetch changes from (such as `main`).

## Git pull


- `git pull` - will get changes from a remote branch into your tracking branch and merge them into a local branch

Often `git push` and `git pull` are described as equivalent. This isn't entirely correct, since under the hood `git pull` does two things. To do that, you'll need to do `git merge origin/master` (for the "master" branch) to merge those changes into your branch - probably also called "master".`git pull` simply does a `git fetch` followed immediately by `git merge`. This is often what we desire to do, but some people prefer to use git fetch followed by git merge to make sure they understand the changes they are merging into their branch before the merge happens.