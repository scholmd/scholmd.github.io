---
layout: post
title: Extending Markdown
modified_date: 22 July 2014
category: advanced_formatting
published: true
---

Markdown is a lightweight format that does not offer built-in facilities for extension. Instead it is recommended to combine external templating tools to adapt the syntax to particular use cases, where necessary. To avoid an unnecessary inflation in the number of markdown flavors out there, it is recommended that language extensions are used sparingly.<!--more-->

## Templating

Generally, a good strategy for extending markdown is to place custom markup inside easy to recognize delimiters. When processing the document, *first* run external filters/templating tools on the source document to convert custom markup to HTML (provided HTML is the intended output format) and *then* apply the markdown processor.

Some templating tools available for this purpose are:

* [Dexy](http://www.dexy.it/) filters
* [Jinja](http://jinja.pocoo.org/)
* [OMeta](http://tinlizzie.org/ometa/)
* regular expressions
* others...

Some good choices for delimiters are:
* Double braces `{{ content }}`.
* Backticks, with a prefix inside the backticks. For example, `` `r content` ``.
* others... ?

Of course this is just a beginning. It would be helpful to have more detailed guidelines for templating and extensions. In particular:

* Templating needs are different in static (dexy, jinja) vs. dynamic (IPython notebook, rNotebook) use cases.
* Is there a standard way to protect the output of a templating engine from being garbled by the markdown processor? According to Daring Fireball, markdown processors are supposed to ignore the content of block level HTML tags. Is this the common practice of most markdown processors today? Does this mean that only known HTML tags are ignored or any XML-style tag? Is the content of these tags expected to be well-formed XML to parse correctly? ...

## Further Notes

* IPython notebook: no way to reference variables from code in the text (i.e. embed their actual values)
  * dexy does something like this
  * `knitr` (for `R`) does this
  * probably can't extend to get this to work in a generic setting, but could define a generic syntax?

* Issues regarding templating, delimeters and parsing
  * where is the information coming from?
  * where does the processing happen?
  * What information can you put in a single file format?
  * Tradeoff between flexibility/ease of use and ability to be precise
  * Don't want to get too complicated

* Composable tools/plugins
  * Python Markdown has extension guidelines

* Want online resources for collaborating about Markdown
  * documentation regarding different flavors of Markdown (where are they the same, how do they differ)
  * Ana: can set something like this up in dexy
