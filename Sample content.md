# hashicorp_sample
Edit test for tech-writer slot
## What is the difference between push, pull, and fetch?

- `git push` - send changes from a local branch to a remote repo
- `git fetch` - get changes from a remote repo into your tracking branch
- `git pull` - get changes from a remote branch into your tracking branch and merge them into a local branch

Often `git push` and `git pull` are described as equivalent. This isn't entirely correct, since under the hood `git pull` does two things: 
- `git push` takes our current branch and checks to see whether there's a tracking branch for a remote repository connected to it. If there is, our changes are pushed from our branch to the remote branch. This is how code is shared with a remote repository; you can think of it as "make the remote branch resemble my local branch." This process will fail if the remote branch has diverged from your local branch. If it has not diverged, all the commits in the remote branch remain in your local branch. When this happens, your local branch needs to be synchronized with the remote branch by using `git pull` or `git fetch` and `git merge`.
- `git fetch` again takes our current branch, and checks to see if there's a tracking branch. If there is, it looks for changes in the remote branch and pulls them into the tracking branch. `git fetch` does not change your local branch. To do that, you'll need to run `git merge origin/master` (for the "master" branch) to merge those changes into your branch -- probably also called "master." The `git pull` command simply runs a `git fetch` followed immediately by `git merge`. This is often what we want to do, but some people prefer to use `git fetch` followed by `git merge` to make sure they understand the changes they are merging into their branch before the merge happens.