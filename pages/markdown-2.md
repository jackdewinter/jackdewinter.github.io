Title: Extended Markdown Examples
Date: 2019-06-28 12:00
Category: blogging
Tags: markdown

This is a continuation of the [previous cheat sheet]({filename}/pages/markdown-1.md) for
my website.  This article specifically addresses any extensions that are not part of the
base Markdown specification.

The authors of the [Python Markdown Package](https://python-markdown.github.io/)
anticipated the addition of extra features.  To ensure people would have choice, the base
package can be [extended using configuration](https://python-markdown.github.io/extensions).

Each section here represents an extension that I have enabled on my website.  The formatting
from the previous page is continued, with one small exception.  The title of each section
specifies the name of the extension instead of the name of the feature being documented (see
[Admonitions](#admonitions)).  If an extension contains more than one feature, such as the
Extra extension, the title specifies the name of the extension, a dash, and the name of the
feature (see [Footnotes](#extra-footnotes)).

---

## Table Of Contents

```text
[TOC]
```

[TOC]

---

## CodeHilite - Code Blocks With Line Numbers

```text
\```
#!python
    # Code goes here ...
\```
```

```
#!python
    # Code goes here ...
```

---

## Extra - Footnotes

```text
Here's a simple footnote,[^1] and here's a longer one.[^bignote]

[^1]: This is the first footnote.

[^bignote]: Here's one with multiple paragraphs and code.
```

Here's a simple footnote,[^1] and here's a longer one.[^bignote]

[^1]: This is the first footnote.

[^bignote]: Here's one with multiple paragraphs and code.

---

## Extra - Abbreviations

The HTML specification
is maintained by the W3C.

*[HTML]: Hyper Text Markup Language
*[W3C]:  World Wide Web Consortium

---

## Extra - Definition Lists

Apple
:   Pomaceous fruit of plants of the genus Malus in
    the family Rosaceae.

Orange
:   The fruit of an evergreen tree of the genus Citrus.

---

## Admonitions

- broken down into section by the way that the Elegant theme colors the admonitions

---

!!! note
    You should note that the title will be automatically capitalized.

!!! important "Replacement Title"
    You should note that the default title will be replaced.

---

!!! hint
    You should note that the title will be automatically capitalized.

!!! tip "Replacement Title"
    You should note that the default title will be replaced.

---

!!! warning
    You should note that the title will be automatically capitalized.

!!! caution "Replacement Title"
    You should note that the default title will be replaced.

!!! attention ""
    You should note that this will have no title due to the empty title.

---

!!! danger
    You should note that the title will be automatically capitalized.

!!! error "Replacement Title"
    You should note that the default title will be replaced.

---

---