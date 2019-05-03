---
title: "Lesson files"
teaching: 0
exercises: 0
questions:
- "Which files should I edit?"
- "How can I preview my changes before making a commit?"
objectives:
- "Know which files to edit to implement your changes"
- "Be able to build the website locally"
keypoints:
- "Edit markdown files in the root directory, `_episodes`(`_episodes_rmd` for R lessons), or `_extras`"
- "Edit figures in the `fig` directory"
- "Jekyll is used to build the site (locally and on GitHub)"
---
## File structure used for lessons
The Carpentries lessons all use the same [structure](http://carpentries.github.io/lesson-example/03-organization/index.html).

Markdown files are combined with images and css to create the webpage served on GitHub.

The home page is created from `index.md` in the root directory, and `setup.md` creates the setup page.
Episode content is stored in `_episodes` and is what you would typically edit in a pull request.
Note that for lessons which use R, you should edit the files in `_episodes_rmd` instead of those in `_episodes`.

Markdown files make use of [special blockquotes](http://carpentries.github.io/lesson-example/04-formatting/index.html)
to create the coloured boxes used for exercises, callouts, keypoints etc.

[Syntax highlighting](http://carpentries.github.io/lesson-example/04-formatting/index.html#formatting-code)
of code blocks is available and should be used whenever possible.

## Local preview using Jekyll
While not always necessary, it's a good idea to preview your changes locally before committing
and making a pull request. This way you can be sure that your intended changes render correctly.

The lesson web sites are build using Jekyll, so you'll need to
[install Jekyll](http://carpentries.github.io/lesson-example/setup.html#optional-jekyll-setup-for-lesson-development)
to build the site locally.

Once you have made your changes, run `make serve` from the root directory of the lesson repository.
The site will be build locally and can be viewed at <http://127.0.0.1:4000>
