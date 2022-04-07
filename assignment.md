## Version Control Commands in Git

### What is the difference between push, pull, and fetch?

- `git push` - Send changes from a local branch to a remote repo
- `git pull` - Get changes from a remote branch into a tracking branch and merge them into a local branch
- `git fetch` - Get changes from a remote repo into a tracking branch

Often `git push` and `git pull` are described as equivalent. This isn't entirely correct, since `git push` does one action and `git pull` does two actions. `git push` takes the current branch, and checks to see whether or not there is a tracking branch for a remote repository connected to it. If so, your changes are taken from the branch and pushed to the remote branch. This is how code is shared with a remote repository. You can think of it as "make the remote branch resemble my local branch". This will fail if the remote branch has diverged from your local branch: if not all the commits in the remote branch are in your local branch. When this happens, you need to synchronize your local branch with the remote branch using `git pull` or `git fetch` and `git merge`. Just like with `git push`, `git fetch` takes your current branch and checks to see if there is a tracking branch. If so, it looks for changes in the remote branch, and pulls them into the tracking branch. It does not change your local branch. To do that, you'll need to do `git merge origin/master` (for the "master" branch) to merge those changes into your branch - probably also called "master".`git pull` does a `git fetch` followed immediately by a `git merge`. This is often what we desire to do, but some people prefer to use git fetch followed by git merge to make sure they understand the changes they are merging into their branch before the merge happens.
