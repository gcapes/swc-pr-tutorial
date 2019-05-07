---
title: "What makes a good Pull Request"
teaching: 0
exercises: 0
questions:
- "When should I create an issue?"
- "What makes a good PR?"
- "How can I make my PR easy to review?"
- "What makes my PR more likely to be merged quickly?"
objectives:
- "Know how to clearly communicate the purpose of your PR"
- "Know how to make reviewing your PR easier"
keypoints:
- "Aim to fix only one thing per PR"
- "Reference any relevant issues"
- "Give a short but descriptive title"
- "The easier you make things for the reviewer, the more likely your PR is to be merged"
---

## Issues
Issues are like a to-do function. Feel free to report a problem you notice without feeling that you also have to fix it with a PR.

Sometimes it can be useful to create an issue first to discuss the intended change.
This enables you to get input from others and get approval of the change before commiting your time.
Search the issues first so that you're not duplicating anything.

> ## Issue exercise
> FIXME: Show one good and one bad example
> Exercise: list details that make a good/bad issue
>
> > ## Solution
> > - Link to the relevant episode, exercise etc.
> > - Quote any relevant text being discussed.
> > - Give others chance to comment before submitting a PR.
> > If you plan to submit the PR anyway, it's probably easier to have any discussion on the PR rather than an issue.
> > Sometimes it's easier to comment on changes than a description of them in an issue.
> {: .solution}
{: .challenge}

## Pull requests
When you create a PR, there is a title box, and a description box.
It's great when the title gives a brief but descriptive overview of the PR,
and when the description describes the what improvements are made by the PR.
Both boxes will usually have some default text in them --- please take the time to
tailor them to your PR.

> ## Pull Request exercise
> FIXME give a good example and a bad example
>
> > ## Solution
> > In the description of the PR, describe in more detail if required.
> > - Reference any related issues using #issuenumber.
> > - If your commit fixes an issue, you can also reference this in the commit message:
> > 'fix #issue-number'.
> >
> > A PR that is easy to merge usually does one thing, and one thing only --- keep it simple.
> > If a PR fixes several unrelated issues, it is harder to review.
> > A PR can only be merged, or not merged --- it isn't easy to merge part of a PR.
> > So if one part of your PR is ready to merge, but another part needs more work,
> > the unfinished part will delay the merging of the finished part.
> > Creating a new feature branch for each PR enables you to work on multiple PRs at the same time.
> {: .solution}
{: .challenge}

