---
title: "Rebasing a Pull Request"
teaching: 0
exercises: 0
questions:
- "How do I keep my fork up to date with the original repository?"
- "How do I 'replay' my pull request on top of the newest commit in the repository?"
- "How do I resolve a merge conflict?"
objectives:
- "Be able to add an upstream repository, and pull changes from it"
- "Know how to rebase a pull request to resolve merge conflicts"
keypoints:
- "A repository can have more than one remote"
- "Adding an upstream remote allows you to keep your fork up to date"
- "Rebasing a pull request enables you to resolve merge conflicts"
---
The scenario: You submitted a PR, but there have been new commits since, and your PR can't be merged due to conflicts.
This is because another pull request which has been merged, has made changes to one of the lines which you changed.

The lesson maintainer isn't necessarily able to resolve the conflict on your behalf,
and certainly it will be easier for them to review and merge your PR if you resolve the conflicts for them.
So how do you do this?

The scenario we're currently in is that we have forked the repo, and cloned it to our machines,
submitting a PR from a feature branch.
The network diagram below shows our branches (origin), and the original repo branches (upstream).

![Pull request behind upstream repo]({{ page.root }}/fig/pr-behind-upstream.svg)

Our gh-pages branch is behind the official repo's gh-pages branch.
The easiest merge to make is a fast forward merge, which happens when the feature branch is ahead of gh-pages.
There is no merge commit required, and no possibility of a merge conflict. This is what we are aiming for.

![Pull request ahead of upstream repo]({{ page.root }}/fig/pr-ahead-of-upstream.svg)

## Remote repositories
Our repo on our machines has local branches, and remote branches (the ones visible on GitHub).
The GitHub repository is referred to as `origin` by default.
You can check this with

```
git remote -v
```
{: .language-bash}

```
origin	https://github.com/gcapes/swc-pr-tutorial.git (fetch)
origin	https://github.com/gcapes/swc-pr-tutorial.git (push)
```
{: .output}

However, a repository can have more than one remote repo.
For a forked repository such as the one we're using, we can add the original repo's address as a second remote.
This allows us to keep our fork up to date with the original repo.
When we add the original repo as a remote to our forked copy, it is convention to call this remote `upstream`,
because changes can flow downstream to our forked copy.

Let's add the upstream repo now:

```
git remote add upstream URL
```
{: .language-bash}

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


## Rebasing your feature branch onto the latest commit
Now we can 'replay' the feature branch on top of the `gh-pages` branch.
This will put it ahead of `gh-pages` which will enable a fast-forward merge for the maintainer.
`git rebase` is the command which 'replays' commits onto a new base commit:
it moves the whole feature branch onto a new starting point i.e. a new *base* commit.

```
git checkout feature-branch
git rebase gh-pages
```
{: .language-bash}

We will have to fix any merge conflicts by editing the conflicted file and removing the merge conflict mark up.
We then mark the file as resolved and continue the rebase:

```
git add conflicted-file
git rebase --continue
```
{: .language-bash}

After the rebase, the feature branch will be ahead of gh-pages and the maintainer can make a fast-forward merge.

![Network diagram after rebase]({{ page.root }}/fig/after-rebase.svg)

Let's visualise that for our repos:

```
git log --graph --all --decorate --oneline
```
{: .language-bash}

But wait, there's one more thing --- this rebased branch only exists locally.
We need our origin/feature to be the same as our local feature branch.
So let's push the feature branch:

```
git push origin feature
```
{: .language-bash}

It doesn't work! In using rebase, we have rewritten the history of the branch,
and so we now have commits locally that doesn't exist in `origin` and vice-versa.
Git is trying to prevent us from accidentally overwriting any commits, and so the push fails.

In order to get origin/feature to match feature, we must *force push*.
```
git push -f origin feature
```
{: .language-bash}

Now the push works, and our pull request updates.
We resolved the conflicts, so the maintainer's job is easier ---
and your PR is likely to be merged more quickly.
