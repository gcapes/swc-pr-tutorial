---
title: "Making a Pull Request (PR)"
teaching: 0
exercises: 0
questions:
- "What is a PR?"
- "What does it mean to fork a repository?"
- "Which branch should I use to make changes to the lesson files?"
- "What happens after I make a PR?"
objectives:
- "Understand the difference between a fork and a clone"
- "Know why to create a new feature branch for your PR"
- "Be able to submit a PR"
keypoints:
- "A PR is asking the maintainer of a repo to merge your feature branch"
- "A fork is making a copy of a repo into your GitHub account; it's a `git clone` on the GitHub servers"
- "Creating a new feature branch for each PR means you can work on more than one PR at a time"
---

The maintainers for a Carpentries lesson have push/write access to the repository,
but most contributors don't have permission to push to the lesson repo.
So how do you contribute your changes?

The first step towards making a PR, is to make a copy of the lesson repository into your GitHub account.
This is called **forking** the repository. You can then use this forked copy like any other git repo that you own.

Next, you `git clone` your newly forked repository (i.e. the copy in your GitHub account).
Checkout a new feature branch for your changes, and make your commits.
Push these changes back to `origin`, which is your forked copy of the repo.

Now you can request that the maintainer of the lesson merge your feature branch into the main lesson's branch.
This is done using GitHub --- look for the green button.
If you don't see this on your GitHub repo's page, go to the Carpentries' lesson repo and go to the *Pull Requests* tab.
Select your feature branch, and follow the instructions!

![]({{ page.root }}/fig/pull-request-diagram.png)

> ## Exercise
> - Fork a repo
> - Clone repo to your own machine
> - Create a new feature branch
> - Make changes to files
> - Preview changes locally using `jekyll serve`
> - Commit changes to the new feature branch
> - Push feature branch to origin
> - Go to <github.com> and submit a PR from your new feature branch
{: .challenge}

## What happens next?
After you have made your PR, the maintainers will receive an email notification,
and will review your PR.

For small PRs (e.g. fixing typos) your PR may be merged without any discussion.

Sometimes a PR is out of the scope of the lesson, or inappropriate for inclusion,
and the PR will be closed with an explanation from a maintainer.

However, for more complicated PRs, there will likely be a review stage and/or general discussion about
your proposal.
This all happens on GitHub, and is typically between the maintainers and the submitter of the PR,
but anyone is welcome to join the conversation.
Often changes will be requested, and you will need to update or add to your PR.
This topic forms the basis of the next episode.
