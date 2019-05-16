---
title: "Keeping your fork up-to-date"
teaching: 20
exercises: 0
questions:
- "How do I keep my fork up to date with the Carpentries repository?"
- "How do I resolve a merge conflict in my PR?"
objectives:
- "Be able to add an upstream repository, and pull changes from it"
- "Know how to resolve merge conflicts in your PR"
keypoints:
- "A repository can have more than one remote"
- "Adding an upstream remote allows you to keep your fork up to date, ready to make another PR"
- "Merging an upstream branch enables you to resolve merge conflicts"
---
The scenario: You submitted a PR, but there have been new commits since, and your PR can't be merged due to conflicts.
This is because another PR has made changes to one of the lines which you changed, and that PR has been merged.

The lesson maintainer isn't necessarily able to resolve the conflict on your behalf,
and certainly it will be easier for them to review and merge your PR if you resolve the conflicts for them.
So how do you do this?

## Remote repositories
Our repo on our machines has local branches, and remote branches (the ones visible on GitHub).
The GitHub repository is referred to as `origin` by default.
You can check this with:

```
git remote -v
```
{: .language-bash}

```
origin	https://github.com/your-username/swc-pr-tutorial.git (fetch)
origin	https://github.com/your-username/swc-pr-tutorial.git (push)
```
{: .output}

However, a repository can have more than one remote repo.
For a forked repository such as the one we're using, we can add the Carpentries' repo address as a second remote.
This allows us to keep our fork up to date with the Carpentries repo.
When we add the original repo as a remote to our forked copy, it is convention to call this remote `upstream`,
because changes can flow downstream to our forked copy.

Let's add the upstream repo now:

```
git remote add upstream URL    # for this example we can use https://github.com/gcapes/swc-pr-tutorial.git
```
{: .language-bash}

The scenario we're currently in is that we have forked the repo, and cloned it to our machines,
submitting a PR from a feature branch.
The network diagram below shows our branches (origin), and the Carpentries repo branches (upstream).

![Pull request behind upstream repo]({{ page.root }}/fig/pr-behind-upstream.svg)

Let's draw that network diagram for our own repo:

```
git fetch upstream gh-pages    # Update our local repo's knowledge of the upstream commits
git log --graph --all --decorate --oneline
```
{: .language-bash}

Now we can update our local `gh-pages` branch by pulling the upstream changes:

```
git checkout gh-pages
git pull upstream gh-pages
git log --graph --all --decorate --oneline
```
{: .language-bash}

Our local gh-pages branch is now the same as upstream/gh-pages.

![Pull upstream/gh-pages]({{ page.root }}/fig/pull-upstream-gh-pages.svg)


The diagram below summarises the concepts involved in adding an upstream remote:
![]({{ page.root }}/fig/upstream-repo.svg)

## Resolving the merge conflict
Now that our local `gh-pages` branch is the same as `upstream/gh-pages`,
we're in a position to include those commits in our feature branch with a `git merge`.

If we merge the `gh-pages` branch (which we just updated) into the `feature` branch,
we will have to resolve the merge conflict in the process.

```
$ git checkout feature
$ git merge gh-pages
```
{: .language-bash}

We then fix the conflicts by removing the markup and committing the file in question:

```
$ git add fixed-file
$ git commit
```
{: .language-bash}

Our feature branch now contains all the commits in `upstream/gh-pages`, so it will
be a straightforward merge for the maintainer.

![Merge upstream/gh-pages]({{ page.root }}/fig/merge-upstream.svg)

Let's visualise that for our repos:

```
git log --graph --all --decorate --oneline
```
{: .language-bash}

But wait, there's one more thing --- this update to our feature branch only exists locally.
We need our origin/feature to be the same as our local feature branch.
So let's push the feature branch:

```
git push origin feature
```
{: .language-bash}

If we now check GitHub we can see that our PR updates.
We resolved the conflicts, so the maintainer's job is easier ---
and your PR is likely to be merged more quickly.

## Subsequent PRs
We have seen how pulling the upstream branch enables us to resolve a merge conflict,
but you should use this technique to update your gh-pages branch before submitting another PR.
