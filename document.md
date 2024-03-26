<!-- copybreak on -->

---
title: Questions for Journal Editors on LLM Copyediting Software
date: 2024-03-24
abstract: |
  **STAGE**: Draft

  **DOCUMENT TYPE**: Discussion Document

  LLM copyediting software can incorporate features that assist authors
  in being more transparent with
  journals regarding their use of an LLM in manuscript preparation.
  The development and documentation of these features can be more beneficial if guided
  by the questions posed to journal editors in this discussion document.
---

<!-- copybreak on -->

Background
----------

The questions in this discussion document pertain to three types of disclosure facilitated by a specific
manuscript writing approach. This approach involves writing a manuscript:

* with source text files, such as LaTeX or Markdown,
* saving them using source version control, such as [Git](https://en.wikipedia.org/wiki/Git), and
* improving the text with LLM copyediting software,
  such as Manubot AI Editor [@Pividori2023.01.21.525030],
  and a spin-off <https://CopyAid.it>.

LLM copyediting software processes chunks of text from an existing manuscript
along with predefined instructions like "Revise the text received" and submits them
to an LLM. The LLM's response is then a new, revised chunk of text
suggested for the manuscript.


<!-- copybreak on -->

First Type of Disclosure
------------------------

The first type of disclosure aligns with
[the current requirements from GSA journals for authors](https://academic.oup.com/genetics/pages/general-instructions),
which include "full technical specifications of the LLM used (name, version, model, source) and method
of application (query structure, syntax)" [4].

CopyAid produces files that could be termed "method specification files", following the
language of the GSA requirement.
Here is an example of such a file produced by CopyAid when an author chooses the "proofread"
instruction:

[proofread.toml](https://gitlab.com/castedo/copyaid/-/raw/68647e9c9439159259e6a282ccd0de5c15aea944/copyaid/config/proofread.toml)
([`swh:1:cnt:3abfe022b8737201b0703e3a60713e2f0f1d369f`](https://archive.softwareheritage.org/swh:1:cnt:3abfe022b8737201b0703e3a60713e2f0f1d369f))

Authors can choose other CopyAid instructions, such as "heavy", which produces a slightly
different "method specification file":

[heavy.toml](https://gitlab.com/castedo/copyaid/-/raw/68647e9c9439159259e6a282ccd0de5c15aea944/copyaid/config/heavy.toml)
([`swh:1:cnt:2e7f1e0152133fbc843d91c523e85f290373690a`](https://archive.softwareheritage.org/swh:1:cnt:2e7f1e0152133fbc843d91c523e85f290373690a))


<!-- copybreak on -->

Second Type of Disclosure
-------------------------

The second type of disclosure is the complete history of all edits made by the human authors,
saved as "commits" in Git terminology. An example is the history of hundreds of
commits for the publication doi:10.1098/rsif.2017.0387 [@doi:10.1098/rsif.2017.0387]:

<https://github.com/greenelab/deep-review/commits/master/>

An example of an individual commit (saved edit) is:

<https://github.com/greenelab/deep-review/commit/081fb466dd13c2813b3ae14bb916173f5d0442c5?diff=split>

This type of disclosure provides transparency on the history of text revisions that
an author chose to include in the manuscript.
These revisions typically consist of large chunks of draft text early in
the manuscript's history, with later revisions being smaller.

These histories can be easily and automatically archived in the Software Heritage
Archive, with archival timestamps beyond the authors' control:

<https://archive.softwareheritage.org/browse/origin/visits/?origin_url=https://github.com/greenelab/deep-review>


<!-- copybreak on -->

Third Type of Disclosure
------------------------

The third type of disclosure is similar to the second type but pertains to LLM-suggested edits rather than
changes saved by a human. 
This functionality is showcased by Manubot AI Editor.
Example edits are illustrated in
the following four diagrams from the paper about Manubot AI Editor:

* <https://greenelab.github.io/manubot-gpt-manuscript/#fig:intro:ccc>

* <https://greenelab.github.io/manubot-gpt-manuscript/#fig:discussion:ccc>

* <https://greenelab.github.io/manubot-gpt-manuscript/#fig:methods:phenoplier>

* <https://greenelab.github.io/manubot-gpt-manuscript/#fig:methods:manubotai>

Similar to how human edits are recorded as Git commits, LLM-suggested revisions can also be recorded
as Git commits.


<!-- copybreak on -->

Main Questions
--------------

GSA already requires information of the first type of disclosure, while Git services such as
GitHub and the Software Heritage Archive provide the second type.
Therefore, let's assume that LLM copyediting software and/or documentation aids in submitting
this information.
The primary focus for these questions is on the third type of disclosure.

### Question 1

Regarding the "method specification files" used by an author,
the third type of disclosure could be for LLM-suggested edits on either:

* actual past drafts of the author's manuscript

or

* a frequently reused example, such as a classic genetics paper.

Journal editors might be specifically interested in the
actual LLM-suggested edits on past drafts.
Alternatively, editors might be more interested in just getting a general sense of what kinds of
edits an LLM generates for a given method specification file.

What would be more useful to journal editors, seeing

* the actual LLM-suggested edits on past drafts (which an author might or might not have
  chosen to incorporate, and may have been re-edited or deleted by a human in the
  submitted version)

or

* the kinds of edits suggested by an LLM on a frequently reused, classic example?


### Question 2

If for question 1 you prefer LLM-suggested edits on actual past drafts,
what would be more useful:

* a short list (just edits on tens of selected paragraphs)

or

* an exhaustive list (maybe hundreds of revised paragraphs, many of which the human
  author may have re-edited or deleted in the submitted version)?


### Question 3

How valuable do journal editors find the third type of disclosure when the first and
second types are already available?


Terminology Questions
---------------------

### Question 4

Which term do you think best describes the function performed by the software
discussed in this document:

* "LLM language editing",

* "LLM copyediting",

* or something else, if so, what?


### Question 5

Can you think of a better term than "method specification file" for the file providing
the first type of disclosure?

