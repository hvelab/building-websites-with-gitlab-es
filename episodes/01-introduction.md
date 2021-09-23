---
title: "Introduction"
teaching: 30
exercises: 10
questions:
- "What is static web content?"
- "Why should I use GitHub or GitLab Pages to create my website?"
  objectives:
- "Explain what a static site generator does."
- "Choose the appropriate tool for a website/project."
  keypoints:
- "A static site generator combines page-specific content with layout elements and styling information to construct individual static webpages."
- "GitHub Pages/GitLab Pages is a good choice for people who are already familiar with Git and GitHub/GitLab."
- "This approach can be used to create a relatively small website/blog on a limited budget."
---

## How Websites Work

When we use a web browser to visit a page on the World-Wide Web,
the browser asks for information from a server -
a computer storing the data relevant to the site and configured to receive and respond to requests for that data.
Assuming there were no problems at this stage
(e.g. asking for a page which doesn't exist, or being unable to reach the server),
our browser receives and interprets this information
to render and display the webpage on our screen.

A web developer would probably be horrified to read such a gross oversimplification,
which is just one reason why
web developers are not the target audience of this tutorial.

The page displayed by the web browser is the result of combining
**HTML** - a hierarchical format describing the structural elements of the page and their raw content - with
**CSS** - an ordered set of styling instructions telling the browser how the content should be organised and formatted -
and any **images** that should be embedded in the page.
Other information received from the server,
but not displayed by the browser,
includes **metadata**, **cookies**, and other non-visible elements in the HTML -
information about the site that could be relevant for a computer
but probably isn't interesting to a human -
and scripts that the browser may run to do something
in response to various triggers.

{% include links.md %}
