---
layout: post
title: Learn Markdown in 3 Minutes
modified_date: 21 July 2014
category: basic_setup
published: true
---

Markdown syntax is extremely simple and you can learn all you need to know within a few minutes.<!--more-->

## Formatting headings

```
# First level
## Second Level
### Third level
#### Fourth level
##### Fifth level
###### Sixth level
```

## **Bold** and _Italics_

```
Bold: **some text**

Italics:  _some other text_

Also italics: *this is also italics*
```

## Links

```
[link text](link)
example: [click here for a web page](http://google.com)
```
## Figures and Images

Figures are formatted the same as links but just add a `!` before the square bracked.

```
![text description](/path/to/image)
```

You can have a picture with a link:

```
[![text description](/path/to/image)](http://twitter.com)
```

## Horizontal lines

```
***

or

---
```

## Code and verbatim

```
Inline code: `some code`

Code block:

    some code
    and another line of code
    some more code

```

Subscript (Pandoc only)

```
R~0~
```

Superscript (Pandoc only)

```
x^2^
```

That's most of the formatting you'll need to get by. I'll get into citation and table formatting on a separate page.
