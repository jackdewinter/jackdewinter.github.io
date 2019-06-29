Title: Standard Markdown Examples
Date: 2019-06-28 12:00
Category: blogging
Tags: markdown

As I started writing my articles for my blog, I realized I needed something.  To help me
write articles using this flavor of Markdown, I wanted my own cheat sheet.

---

- [Introduction](#introduction)
- [Horizontal Break](#horizontal-break)
- [Headings](#headings)
- [Text Emphasis](#text-emphasis)
- [Numbered lists](#numbered-lists)
- [Bulleted List](#bulleted-list)
- [Block quote](#block-quote)
- [Code Block](#code-block)
- [Tables](#tables)
- [Links](#links)
    - [Local Links](#local-links)
    - [Remote Links](#remote-links)
    - [Download Links](#download-links))
- [Images](#images)

---

## Introduction

I am writing articles and pages on Pelican 4.0.1 using the Elegant theme, therefore I want to
make sure I have a cheat sheet that is specific to this dialect of Markdown. The base Markdown
used for Pelican uses the [Python Markdown Package](https://python-markdown.github.io/) which
(with 3 exceptions) follows
[John Gruber's Markdown definition](https://daringfireball.net/projects/markdown/syntax)
very literally.  Pelican configuration also supports providing Markdown with additional
configuration that enables other features.  Those features are documented separately in
[the next page]({filename}/pages/markdown-2.md).

The format of this cheat sheet is simple.  Each section is separated from the next with a
horizontal break and the name of the section.  Any notes regarding that section are placed
at the top of the section in point form, to ensure they are brief.  Then a
[Code Block](#code-block) section is used to show the literal code used to produce the effects
that are presented right after the code block.

---

## Horizontal Break

```text
A horizontal break occurs after 3 or more hyphens.

---
```

A horizontal break occurs after 3 or more hyphens.

---

## Headings

```text
# Heading Level 1

## Heading Level 2

### Heading Level 3
```

# Heading Level 1

## Heading Level 2

### Heading Level 3

---

## Text Emphasis

- two spaces at the end of a line will be equivalent to ``<br/>``

```text
This text is **bold** and this text is also __bold__.  
This text is *italic* and this text is also _italic_.  
This text is **_italic and bold_**, but no two spaces at end.
Single ```line``` block.  
Inline `code` has ```back-ticks like this ` around``` it.  
```

This text is **bold** and this text is also __bold__.  
This text is *italic* and this text is also _italic_.  
This text is **_italic and bold_**, but no two spaces at end.
Single ```line``` block.  
Inline `code` has ```back-ticks like this ` around``` it.  

---

## Numbered lists

- to maintain the indentation, place 4 spaces at the start of the line

```text
1. One  

    New para.  

    Blah

2. Two
    - unordered
    - list
3. Three
    1. ordered
    2. list
        - unordered
        - list
    3. items
```

1. One  

    New para.  

    Blah

2. Two
    - unordered
    - list
3. Three
    1. ordered
    2. list
        - unordered
        - list
    3. items

---

## Bulleted List

- to maintain the indentation, place 4 spaces at the start of the line

```text
- This is a list item with two paragraphs.

    This is the second paragraph in the list item. You're
only required to indent the first line. Lorem ipsum dolor
sit amet, consectetuer adipiscing elit.

- Another item in the same list.
    - Bulleted item
    - Bulleted item
```

- This is a list item with two paragraphs.

    This is the second paragraph in the list item. You're
only required to indent the first line. Lorem ipsum dolor
sit amet, consectetuer adipiscing elit.

- Another item in the same list.
    - Bulleted item
    - Bulleted item

---

## Block quote

```text
> This is the first paragraph of a blockquote with two paragraphs.
> Lorem ipsum dolor sit amet,
> consectetuer adipiscing elit. Aliquam hendrerit mi posuere lectus.
> Vestibulum enim wisi, viverra nec, fringilla in, laoreet vitae, risus.
>
> This is a blockquote with two paragraphs. Lorem ipsum dolor sit amet, consectetuer adipiscing elit. Aliquam hendrerit mi posuere lectus. Vestibulum enim wisi, viverra nec, fringilla in, laoreet vitae, risus.
>
> This is the first level of quoting.
>
> > This is nested blockquote.
>
> Back to the first level.
```

> This is the first paragraph of a blockquote with two paragraphs.
> Lorem ipsum dolor sit amet,
> consectetuer adipiscing elit. Aliquam hendrerit mi posuere lectus.
> Vestibulum enim wisi, viverra nec, fringilla in, laoreet vitae, risus.
>
> This is a blockquote with two paragraphs. Lorem ipsum dolor sit amet, consectetuer adipiscing elit. Aliquam hendrerit mi posuere lectus. Vestibulum enim wisi, viverra nec, fringilla in, laoreet vitae, risus.
>
> This is the first level of quoting.
>
> > This is nested blockquote.
>
> Back to the first level.

---

## Code Block

- line numbers can be added
[via extensions]({static}/pages/markdown-1.md#codehilite-code-blocks-with-line-numbers)

```text
```text
Make things only as complex as they need to be.
``\`

```Python
# Blogroll
LINKS = (
            ('Pelican', 'Pelican', 'http://getpelican.com/'),
         )
```

```text
Make things only as complex as they need to be.
```

```Python
# Blogroll
LINKS = (
            ('Pelican', 'Pelican', 'http://getpelican.com/'),
         )
```

---

## Tables

- colons can be used to align columns.

```text
| Column1 | Column 2 | Column 3
|---|---|---|
| Value 1 | Value 2 | Value 3 |
| Value 4 | Value 5 | Value 6 |
| Value 7 | Value 8 | Value 9 |

| Tables        | Are           | Cool  |
| ------------- |:-------------:| -----:|
| col 3 is      | right-aligned | $1600 |
| col 2 is      | centered      |   $12 |
| zebra stripes | are neat      |    $1 |
```

| Column1 | Column 2 | Column 3
|---|---|---|
| Value 1 | Value 2 | Value 3 |
| Value 4 | Value 5 | Value 6 |
| Value 7 | Value 8 | Value 9 |

| Tables        | Are           | Cool  |
| ------------- |:-------------:| -----:|
| col 3 is      | right-aligned | $1600 |
| col 2 is      | centered      |   $12 |
| zebra stripes | are neat      |    $1 |

---

## Links

### Local Links

- `{static}` tag indicates location in the content folder.

```text
[About Page]({filename}/pages/about.md)
```

[About Page]({filename}/pages/about.md)

### Remote Links

- proper URL indicates a remote website

```text
[Python Package Index](https://pypi.org)
```

[Python Package Index](https://pypi.org)

### Download Links

- download links are not natively supported in Markdown
- must explicitly create HTML text inline to achieve that
Creating a link to a file to download, not display, is not natively supported in markdown.

```text
[Pelican Brag Document (display)]({static}/images/pelican.txt)  
<a href="{static}/images/pelican.txt" download>Pelican Brag Document (download)</a>
```

[Pelican Brag Document (display)]({static}/images/pelican.txt)  
<a href="{static}/images/pelican.txt" download>Pelican Brag Document (download)</a>

---

## Images

- `{static}` tag indicates location in the content folder.

```text
![python logo]({static}/images/python_icon.png)
```

![python logo]({static}/images/python_icon.png)
