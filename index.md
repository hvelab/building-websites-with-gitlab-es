---
layout: lesson
root: .  # Is the only page that doesn't follow the pattern /:path/index.html
permalink: index.html  # Is the only page that doesn't follow the pattern /:path/index.html
---

> ## Prerequisites
> Before following this lesson, learners should be able to:
>
> 1. create a project on [GitLab][gitlab] / [EMBL GitLab][embl-gitlab].
> 1. clone a local copy of a project with Git, add and commit modified files, and push/pull changes between local and remote repositories.
> 1. execute commands in the shell.
>
> If you'd like to learn any of the skills listed above,
> the [Software Carpentry][swc] lessons on
> [the Shell][swc-shell]
> and [Git][swc-git] are a good place to start.
{: .prereq }

For those already familiar with the ways that Git
and an online platform like GitLab or GitHub
can help them track and compare changes to flat text files
and collaborate with others on projects,
__GitLab__ (and GitHub) __Pages__ provide a cost-free way to
build and host webpages.
This approach is commonly used to provide documentation
on software projects,
and to create blogs and websites for
individuals and organisations already used to working with
the Git toolset for their other projects.
However, for those taking their first steps towards building sites like this,
the process can be confusing and intimidating.
This tutorial aims to address this,
by
1. providing a step-by-step guide to creating a collection of pages,
1. showing multiple examples of how to structure them into a coherent site,
1. demostrating how to use multiple frameworks for web pages development, from plain _HTML_ to _Jekyll_ and _Sphinx_.

The difference between GitLab and GitHub pages development will also be briefly discussed.

> ## Outdated Screenshots
>
> Throughout this lesson we will make use and show content and screenshots from [git.embl.de](https://git.embl.de/).
> As an ever evolving platform, GitLab is always adding new features
> and new visual elements to its website.
> **Screenshots** in the lesson may then become out-of-sync, refer or show content that no longer exists.
>
> If during the lesson you find **screenshots** that no longer match what you see in your browser,
> please [open an issue](https://git.embl.de/grp-bio-it-workshops/building-websites-with-gitlab/-/issues)
> describing what you see and how it differs from the lesson content.
> Feel free to add as many screenshots as necessary to clarify the discrepancy.
{: .callout }

> ## Learning Objectives
>
> After following this lesson,
> learners will be able to:
>
> - __create__ formatted page content with _HTML_ or _Markdown_
> - __configure__ their project to build and serve pages on GitLab
> - __build__ a simple site to host content in plain _HTML_
> - __build__ a coherent site with multiple pages using the _Jekyll_ or the _Sphinx_ framework
> - __customise__ the layout and style of the pages on their site
>
{: .objectives }

[gitlab]: https://gitlab.com/
[embl-gitlab]: https://git.embl.de/

{% include links.md %}
