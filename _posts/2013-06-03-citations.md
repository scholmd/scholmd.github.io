---
layout: post
title: Citations
modified_date: 21 July 2014
category: markdown_elements
published: true
---

### Citations breakout group at Markdown for Science workshop

Citations should be specified as citation keys (e.g. [@smith2010]. Pandoc and Multimarkdown both support human-readable formatting for this, but use different formatting.<!--more-->

#### We identified two use cases:
* fragment of a scientific document
* complete document, e.g. manuscript for paper

Reference information should be stored in an external bibtex file, which could be referenced by a link or be in the same folder as the markdown file, specified in the metadata.

Citation styles should be processed using Citeproc and the Citation Style Language. Citation style can optionally be specified in the metadata.

#### Questions from the audience :)
Stian: Is there any good online collaborative citation manager that supports citekeys (defining/seeing)?

### Citation discussion at Gobbledygook Blog
A [blog post](http://blog.martinfenner.org/2013/06/19/citations-in-scholarly-markdown/), and a very good discussion clarified many issues around citations.

#### Rethink current practices
Most of the things we currently with citations come from a time when journal articles were printed on paper. Examples include citation styles and reference lists. Moving forward we should rethink these practices:

* Citation styles should not be the concern of the author. There is no place for citation styles, or citation formatted with a particular citation style in a markdown document.
* Reference lists often don't make sense for digital documents. What we rather need are good inline links, plus references in a computer-readable format (e.g. bibtex). One challenge with reference lists is the synchronization between inline citations and the reference list.
* Separate files for references create unnecessary overhead and can lead to vendor lock-in. Ideally all the required information should be stored in the markdown document. We should rather export the references from the markdown file to bibtex when transforming to HTML or other output formats (see above).

#### Suggested approach
* Citations are links. Thinking of citations as links makes the workflow much easier.
* Use reference-style links for documents with many citations. This makes it easier to manage the citations, e.g. when the same paper is cited more than once.
* You can use citation keys with reference-style links, and this makes it easy to integrate with reference managers (Papers for example supports `[#key][]`).
* Use the "title" attribute with reference-style links, using the citation title. DOIs (and often also weblinks) are not human-readable. Using the title makes citations easier to remember and prevents transcription errors (i.e. typos in DOIs or URLs):

```
[#Beyer2013]: http://dx.doi.org/ 10.1093/annonc/mds579 "Maintaining success, reducing treatment burden,
focusing on survivorship: highlights from the third European consensus conference on diagnosis and
treatment of germ-cell cancer."
```
* The transformation from markdown into a presentation format (e.g. HTML or PDF) should include link checking (see proof of concept tools below).
* We should support internal links to tables and figures, using anchors.

#### Questions
* How do we handle citations that can't be linked to digital resources? Two ideas are footnotes and placeholder hyperlinks (and <a> tag without href, new in HTML5).

#### Todo
* Proof of concept tool that transform links in markdown documents into references, e.g. by pulling information from CrossRef or DataCite.
* Proof of concept tool to display reference information on hover in HTML documents created from markdown.
* Proof of concept tool that extracts all links from a markdown document and generates both a bibliography and bibtex file.
* Best practices how citation information can be stored in HTML link. Probably involves data- attributes.

### Citation Styles

#### Reference Manager support for workflow above

* Papers. Allows copy/paste of citekey in different formats (including MMD, Pandoc)
* Mendeley. Copy/paste of citekey in LaTeX format. Allows custom citekeys. Can automatically sync with bibtex file.
* Zotero. ?
* Endnote. ?

#### Downloading styles
This repo contains citation styles for most journals. Download a copy of the repo somewhere locally by running:

```
git clone git://github.com/citation-style-language/styles.git
```
