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

> ## What makes a good issue?
> Consider the two issues below, then list the positive and negative aspects of each.
>
> 1. **Ep6: Exercise 'List Unique Species' has high cognitive load**
>
>    https://swcarpentry.github.io/shell-novice/06-script/index.html#list-unique-species
>
>    This exercise relies on the `cut` command which was introduced only in exercises two episodes ago,
>    and the long pipeline introduces extraneous cognitive load.
>
>    This exercise would better meet the learning objectives of the episode if it were scaffolded
>    by providing the piped commands, leaving learners the task of writing a script to loop over input files.
>
>
> 2. **suggested improvements (and fixed a typo) - Instructor checkout**
>
>    - Possible confusion with 'ls' command
>
>         The first few unix shell lesson subsections switch between `ls` and `ls -F` without ever really explaining why. Furthermore, the longer command ls -F is never fully explained (and the man page for ls doesn't provide helpful information on what this flag is doing in case users are trying to figure it out on their own). Issue #846 has raised this same point.
>
>
>     - In the "Finding things" subsection, there could be a quick reminder to `cd data-shell/writing` before running the `find` commands. After the `grep` exercises, users are likely to be in another directory or subdirectory.
>
>
>     - There's a minor typo in the first line of the usage data for the `goostats` program,
>     in that it calls the script *goodstats* instead of *goostats*.
>     The following line uses the correct name, and the goodiiff script gets things right as well.
>
>     -
>
>     Please delete the text below before submitting your contribution.
>
>     Thanks for contributing! If this contribution is for instructor training, please send an email to checkout@carpentries.org with a link to this contribution so we can record your progress. You’ve completed your contribution step for instructor checkout just by submitting this contribution.
>
>    Please keep in mind that lesson maintainers are volunteers and it may be some time before they can respond to your contribution. Although not all contributions can be incorporated into the lesson materials, we appreciate your time and effort to improve the curriculum. If you have any questions about the lesson maintenance process or would like to volunteer your time as a contribution reviewer, please contact Kate Hertweck (k8hertweck@gmail.com).
>
> > ## Solution
> > In an issue, you should aim to:
> > - Address only one thing (if possible).
> > - Link to the relevant episode, exercise etc.
> > - Quote any relevant text being discussed.
> > - Give others chance to comment before submitting a PR.
> > If you plan to submit the PR anyway, it's probably easier to have any discussion on the PR rather than an issue.
> > Sometimes it's easier to comment on changes than a description of them in an issue.
> {: .solution}
{: .challenge}

## Pull Requests
When you create a PR, there is a title box, and a description box.
It's great when the title gives a brief but descriptive overview of the PR,
and when the description describes the what improvements are made by the PR.
Both boxes will usually have some default text in them --- please take the time to
tailor them to your PR.

> ## What Makes a Good Pull Request?
> Consider the PR titles and descriptions below, then list the positive and negative aspects of each.
>
> 1. **Move callout for non-responsive commands**
>
>     Move callout from episode 6 to where this problem may first be encountered in episode 4.
>
>     Fix #836
>
> 2. **Update index.md**
>
>    FIXME: add some uninformative text, maybe just the boilerplate text.
>
> 3. FIXME: example of PR which addresses several issues, making it cumbersome to discuss each point.
>
> > ## Solution
> > In the description of the PR, describe in more detail if required.
> > - Reference any related issues using #issuenumber.
> > - If your commit fixes an issue, you can also reference this in the commit message:
> > 'fix #issue-number'.
> > - A PR that is easy to merge usually does one thing, and one thing only --- keep it simple.
> > - If a PR fixes several unrelated issues, it is harder to review.
> > - A PR can only be merged, or not merged --- it isn't easy to merge part of a PR.
> > - So if one part of your PR is ready to merge, but another part needs more work,
> >   the unfinished part will delay the merging of the finished part.
> > - Creating a new feature branch for each PR enables you to work on multiple PRs at the same time.
> {: .solution}
{: .challenge}

