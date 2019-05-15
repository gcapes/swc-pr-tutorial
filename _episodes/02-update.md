---
title: "Adding to a Pull Request"
teaching: 0
exercises: 0
questions:
- "How do I make changes to an existing PR?"
objectives:
- "Know how to make changes to an existing PR"
keypoints:
- "Any changes to your feature branch in `origin` will be reflected in your PR automatically"
---
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

## Adding to your PR
So you've made your PR, but changes have been requested. How do you make them?

Let's take a look at the recent history of your git repository.
You have a feature branch which is ahead of `gh-pages`, which is the default branch
in the Carpentries' lesson repos, and is also the branch used to build the website.

All we need to do is to modify that feature branch, and the PR will update.

The simplest (if not the most elegant solution) is to add more commits to the feature branch.
Then push your local branch to `origin` (your forked copy of the repo),
and your PR updates.
Your new (or amended) commits show up in the PR on GitHub.

> ## Add to your pull request
> Suppose the reviewer has asked for changes to your PR.
> Make those changes by adding another commit to the feature branch
> you used to submit the PR.
> Then view your PR on GitHub and check that the extra commit shows.
> You might need to refresh the GitHub page in your browser.
{: .challenge}
