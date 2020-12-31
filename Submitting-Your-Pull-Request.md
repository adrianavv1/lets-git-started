# Submitting a Pull Request

## Cleaning Up Your Work

Prior to submitting your pull request, you might want to do a few things to clean up your branch and make it as simple as possible for the original repo's maintainer to test, accept, and merge your work.

If any commits have been made to the upstream main branch, you should rebase your development branch so that merging it will be a simple fast-forward that won't require any conflict resolution work.

```shell
# Fetch upstream main and merge with your repo's main branch
git fetch upstream
git checkout main
git merge upstream/main

# If there were any new commits, rebase your development branch
git checkout newfeature
git rebase main
```

Now, it may be desirable to squash some of your smaller commits down into a small number of larger more cohesive commits. You can do this with an interactive rebase:

```shell
# Rebase all commits on your development branch
git checkout 
git rebase -i main
```

This will open up a text editor where you can specify which commits to squash.

## Submitting

Once you've committed and pushed all of your changes to GitHub, go to the page for your fork on GitHub, select your development branch, and click the pull request button. If you need to make any adjustments to your pull request, just push the updates to GitHub. Your pull request will automatically track the changes on your development branch and update.

---

## Accepting and Merging a Pull Request

We will go over this in the study group, but you can read [this document][pr-merging] to get a head start.

[pr-merging]:  Accepting-and-Merging-Pull-Requests.md