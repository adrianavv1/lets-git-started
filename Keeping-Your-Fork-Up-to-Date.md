# Keeping Your Fork Up to Date

While this isn't an absolutely necessary step, if you plan on doing anything more than just a tiny quick fix, you'll want to make sure you keep your fork up to date by tracking the original "upstream" repo that you forked. To do this, you'll need to add a remote:

```shell
# Add 'upstream' repo to list of remotes
git remote add upstream https://github.com/UPSTREAM-USER/ORIGINAL-PROJECT.git

# Verify the new remote named 'upstream'
git remote -v
```

Whenever you want to update your fork with the latest upstream changes, you'll need to first fetch the upstream repo's branches and latest commits to bring them into your repository:

```shell
# Fetch from upstream remote
git fetch upstream

# View all branches, including those from upstream
git branch -va
```

Now, checkout your own master branch and merge the upstream repo's master branch:

```shell
# Checkout your main branch and merge upstream
git checkout main
git merge upstream/main
```

If there are no unique commits on the local main branch, git will simply perform a fast-forward. However, if you have been making changes on main (in the vast majority of cases you probably shouldn't be - [see the next section](#doing-your-work)), you may have to deal with conflicts. When doing so, be careful to respect the changes made upstream.

Now, your local main branch is up-to-date with everything modified upstream.

## Doing Your Work

### Create a Branch
Whenever you begin work on a new feature or bugfix, it's important that you create a new branch. Not only is it proper git workflow, but it also keeps your changes organized and separated from the main branch so that you can easily submit and manage multiple pull requests for every task you complete.

To create a new branch and start working on it:

```shell
# Checkout the main branch - you want your new branch to come from main (this can differ from project to project, make sure to look into the projects CONTRIBUTIONS rules)
git checkout main

# Create a new branch named newfeature (give your branch its own simple informative name)
git branch newfeature

# Switch to your new branch
git checkout newfeature
```

To create and checkout your new brach,you can also do this in a 'one-liner' command, like so:

```shell
# Checkout the main branch - you want your new branch to come from main (this can differ from project to project, make sure to look into the projects CONTRIBUTIONS rules)
git checkout main

# Create a new branch named newfeature from the main branch (give your branch its own simple informative name) and checkout to your newly created branch.
git checkout -b newfeature main
```

Now, go to town hacking away and making whatever changes you want to.

---

## Submitting Your Pull-Request

To learn how to submit your pull request, you can read [this document][pr-submit]. Don't worry if you don't completely get it. We will also cover this in the study group.

[pr-submit]: Submitting-Your-Pull-Request.md