<!-- copybreak off # to proof -->

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

<!-- copybreak off # to light -->

Background
----------

The questions in this discussion document pertain to three types of disclosure facilitated by a specific
manuscript writing approach. This approach involves writing a manuscript

* with source text files, such as LaTeX or Markdown,
* saving them using source version control, such as [Git](https://en.wikipedia.org/wiki/Git), and
* improving the text with LLM copyediting software,
  such as Manubot AI Editor [@Pividori2023.01.21.525030],
  and spin-off <https://CopyAid.it>.

LLM copyediting software processes chunks of text from an existing manuscript
along with predefined instructions like "Revise the text received" and submits them
to an LLM. The LLM's response is then a new, revised chunk of text
suggested for the manuscript.


<!-- copybreak off # to light -->

First Type of Disclosure
------------------------

The first type of disclosure aligns with
[the current requirements from GSA journals for authors](https://academic.oup.com/genetics/pages/general-instructions):
"full technical specifications of the LLM used (name, version, model, source) and method
of application (query structure, syntax)" [4].

CopyAid produces files that could be termed "method specification files", following the
language of the GSA requirement.
Here is an example of such a file produced by CopyAid when an author chooses the "proofread"
instruction:

[proofread.toml](https://gitlab.com/castedo/copyaid/-/raw/68647e9c9439159259e6a282ccd0de5c15aea944/copyaid/config/proofread.toml)

Authors can choose other CopyAid instructions such as "heavy" which produces a slightly
different "method specification file":

[heavy.toml](https://gitlab.com/castedo/copyaid/-/raw/68647e9c9439159259e6a282ccd0de5c15aea944/copyaid/config/heavy.toml)


<!-- copybreak on -->

Second Type of Disclosure
-------------------------

The second type of disclosure is the complete history of all edits made by the human authors,
saved as "commits" in Git terminology. An example is the history of hundreds of
commits for the publication doi:10.1098/rsif.2017.0387 [@doi:10.1098/rsif.2017.0387]:

<https://github.com/greenelab/deep-review/commits/master/>

An example of an individual commit (saved edit) is:

<https://github.com/greenelab/deep-review/commit/081fb466dd13c2813b3ae14bb916173f5d0442c5?diff=split>

This type of disclosure provides transparency on the history of what text revisions
a human choose to include in the manuscript.
These revisions are typically large chunks of draft text early in the history of a
manuscript and then later the revisions are smaller.

These histories can be easily and automatically archived in the Software Heritage
Archive with archival timestamps beyond the authors' control:

<https://archive.softwareheritage.org/browse/origin/visits/?origin_url=https://github.com/greenelab/deep-review>


<!-- copybreak off # to light -->

Third Type of Disclosure
------------------------

The third type of disclosure is similar to the second type but for LLM-suggested edits,
not changes saved by a human. 
This functionality is showcased by Manubot AI Editor.
Example edits are illustrated in these four
diagrams from the paper about Manubot AI Editor:

* <https://greenelab.github.io/manubot-gpt-manuscript/#fig:intro:ccc>

* <https://greenelab.github.io/manubot-gpt-manuscript/#fig:discussion:ccc>

* <https://greenelab.github.io/manubot-gpt-manuscript/#fig:methods:phenoplier>

* <https://greenelab.github.io/manubot-gpt-manuscript/#fig:methods:manubotai>

Similar to human edits recorded as Git commits, LLM-suggested revisions can also be recorded
as Git commits.


<!-- copybreak on # heavy yet to merge -->

Main Questions
--------------

Given that the GSA already requests the information in a "method specification file", we
assume journal editors would like LLM copyediting software to facilitate authors
submitting them.

Popular Git services, like GitHub, and the Software Heritage Archive already provide
pages which list and link to the human edits.

For a given "method specification file", the third type of disclosure can be actual edits suggested by the LLM on actual
past drafts of the manuscript or they can be edits suggested on a canonical frequently
used example, such as a classic genetics paper of the past.

Q1) What would be of greater utility to journal editors, seeing the kind of edits
suggested on a canonical classic example for the "method specification files used,
or the actual edits suggested on past drafts?

Q2) If you think actual suggested edits on past drafts is more useful than suggested
edits on a canonical classic example,
this third type of disclosure can be a short list or an exhaustive list of LLM
suggested edits. Human authors do not choose to incorporate all edits suggested by an
LLM. A short list would consist of tens of selected paragraph revisions,
whereas an exhaustive list would consist of almost all LLM suggested edits, which would
be hundreds of revised paragraphs, even if a human author does not use them.
Would you find a short list or an exhaustive list more useful?

Q3) How much utility do journal editors find in also having the third type of
disclosure, given the first and second types of disclosures are already available?


Terminology Questions
---------------------

Q4) The GSA journals use the term "language editing" as a suggested pre-submission
activity. Do you think "LLM language editing" is a better description rather than "LLM
copyediting" for the function performed by the software referenced by these questions?

Q5) Is there an alternative term than "method specification file" that you think
is a more understandable name for the file described in the first type of disclosure?

Q6) Are the any names you can suggest for a file that 
ists and links to the edits of the SECOND type of disclosure (saved edits by a human)?

Q7) Are the any names you can suggest for a file that lists and links to the THIRD type
of disclosure (suggested edits by an LLM copyediting software)?
