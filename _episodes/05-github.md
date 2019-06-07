---
title: "Contributing directly on GitHub"
teaching: 5
exercises: 5
questions:
- "How can I contribute to a lesson using only GitHub?"
- "What are the limitations of using GitHub like this?"
objectives:
- "Submit a PR using just GitHub"
- "Recognise the drawbacks of editing directly on GitHub"
keypoints:
- "Click on *Improve this page* button"
- "Change the default commit message"
- "GitHub creates a new branch for your PR"
- "GitHub preview doesn't render the lesson correctly"
---

Ok, so what if you're using a machine that doesn't have Git installed?
Or maybe you've spotted a typo and want to fix it without first
updating your fork.

An alternative to editing your local copy of the repo is to edit
the files directly on GitHub.
Go to the rendered webpage for the lesson, and click on the button
labelled *Improve this page* on the navigation bar at the top of the page.
This will take you into an editor window, where you can make your edits:

![]({{ page.root }}/fig/edit-on-github.png)

After you have made your edits, scroll down to find the *Propose file change*
dialog, and be sure to edit the default commit message to something descriptive!

![]({{ page.root }}/fig/propose-file-change.png)

The next screen is where you'll actually submit the PR.

![]({{ page.root }}/fig/create-pr-github.png)

GitHub creates a new branch called *patch-1* which puts your changes
on top of the most recent commit in the Carpentries' repo.

An advantage is that your PR will be up-to-date with the official lesson.
A disadvantage is that you don't get to name the new branch anything descriptive.
Also, the preview of your changes on GitHub doesn't render the page correctly,
so you won't necessarily be able to tell if your PR contains any formatting errors.

> ## Submit a PR using the GitHub interface
> Submit a PR to this repo using the GitHub interface.
> Choose any page, and propose a change to it by clicking on *Improve this page*
> and following the instructions.
{: .challenge}

See also [these materials](https://github.com/dmgt/swc_github_flow/blob/master/for_novice_contributors.md)
on contributing to Carpentries lessons.
