# Renda Manual

This repository contains the content of the Renda manual available at
[rendajs.org/manual](https://rendajs.org/manual).

## Contributing

If you want to preview the changes you have made, you can run the code for the
rendajs.org site locally. To do so, check the documentation in the
[rendajs.org repository](https://github.com/rendajs/rendajs.org).

### Style Guide

All headings are written in Title Case, you can use
[capitalizemytitle.com](https://capitalizemytitle.com/) to quickly convert your
titles.

In instructions, the contents of buttons and the names of content windows should
be **bold**.

### Markdown Files

All pages are written in Markdown files. You can find a quick
[overview of the syntax here](https://www.markdownguide.org/basic-syntax/). But
[GitHub flavored Markdown](https://github.github.com/gfm/) is also supported. On
top of that there are a few more additions:

#### Notes

You can prepend a paragraph with `NOTE:` and `WARNING:` to render a paragraph as
a note or warning.

```
NOTE: This is a note.

This is a regular paragraph.

WARNING: This is a warning.
```

If you want to wrap multiple paragraphs in a single note that is possible too.

```
NOTE:

This is a note.

And this is still part of the same note.

END NOTE
```

### Index Files

Every folder contains an `index.yml` file which configures the order of the
pages and which file represents the main page.

```yml
title: My Topic
mainPage: main.md
pages:
  - first-page.md
  - second-page.md
```

If a main page is configured, it can be viewed by clicking the name of the
directory on rendajs.org. It also appears in the regular pagination flow using
the 'Previous' and 'Next' buttons on rendajs.org.

Main pages are not required and are discouraged when there is nothing meaningful
to say. It is better to have no main page at all than to have a shallow main
page with only a simple table of contents.

The table of contents on rendajs.org is generated from the first title in each
Markdown file. Directory names are taken from the title of the main page. If no
main page exists, a `title:` needs to be provided in its index file.
