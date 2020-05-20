
struct:ed Tutorial
==================

This document demonstrates the features of *struct:ed* and reStructuredText_,
the markup language upon which *struct:ed* builds.


What is struct:ed?
------------------

*struct:ed* is a WYSIWYM_ editor. This means that documents are represented in
a structured way, and not formatted as they will eventually be consumed (HTML
or PDF, for example).

Semantics: emphasis instead of italic. Separation of content and presentation.

reStructuredText = open, text-based format, extensible, tools to convert to
multitude of formats including HTML, EPub and PDF.

Can be difficult to edit, requiring to remember syntax. struct:ed provides an
environment that solves this problem. Additionally, struct:ed styles the
various document elements to help navigate the document. For example, headings
are displayed in a large font. Inline markup is also styled to make them stand
out

Edited documents are saved as reStructuredText. GitHub: versioning! Editor
works on a repository level. Navigate to a repository. File tree displayed on
left. Commits to structed branch.

Collaborative editing. Simultaneous editing by multiple users. They need push
access to the repository.


Limitations
~~~~~~~~~~~

Not all document elements are supported. Supported elements are discussed in
the next section.

Many writing aids can be added. For example, popping up a list of available
reference targets. Inter-file cross-references.


Editing a Document
------------------

Toolbar, keyboard shortcuts, input rules

Toolbar doubles as a cheat sheet. Both keyboard shortcuts and input rules (in
orange) are shown in the tooltip when hovering the mouse pointer over the
corresponding menu bar button.


Structural Elements
~~~~~~~~~~~~~~~~~~~

Section titles or headings. ``#``

Try it, create a level-4 heading below:

Transitions


Body Elements
~~~~~~~~~~~~~

Paragraph is the default body element. Ctrl-Alt-0.

Inline markup. ``::``also at front of paragraph.

Literal block. For code.

Enumerated List

Comments.


Directives
~~~~~~~~~~

target (anchor), optional alias

substitution definition

custom interpreted text role

Custom directives (future).

.. _WYSIWYM: https://en.wikipedia.org/wiki/WYSIWYM

.. _reStructuredText: https://en.wikipedia.org/wiki/ReStructuredText


Future
------

.. Is it a good idea to include this?

Section outline

Support all rST elements, Sphinx

Highlight changes since last commit

Comments annotated with the user name

Backends: GitLab, DropBox, ...
