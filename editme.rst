
struct:ed Tutorial
==================

This document demonstrates the features of *struct:ed* and reStructuredText_,
the markup language upon which *struct:ed* builds.


What is struct:ed?
------------------

*struct:ed* is a WYSIWYM_ editor. This means that documents are represented in
a structured way, not necessarily reflecting the look of the final, published
document. This helps separate content and presentation and focus on semantics.
For example, text can be marked as *emphasized* or **strongly emphasized**. In
the publishing stage, styles are applied to represent these semantics.
*Italics* and **bold** font are typically employed to make emphasized text
stand out.

Documents are stored in the reStructuredText_ format, an open, extensible
lightweight markup language suited fro publishing to a multitude of formats
including HTML, EPub and PDF. *struct:ed* facilitates editing of
reStructuredText documents by providing the user with an environment that frees
the user from having to remember the syntax for all document elements.
Additionally, it respresents the document in a format that is easy to navigate.

The reStructuredText documents need to be stored somewhere, of course. The
first backend *struct:ed* supports is GitHub. Documents are stored in a git
repository and their edit history is thus being preserved. *struct:ed* works on
a repository level; the panel on the left shows a tree of the files present on
in the repository. Clicking a file will open it for editing. Clicking the
*Commit* button at the top right will commit changes to all files to the
*structed* branch of the repository.

Finally, *struct:ed* also supports collaborative editing. Several users can
edit a document at the same time. Their changes will be visible immediate by
others editing the same document. Note that all users need *push* access to a
repository to be able to edit documents stored in it.


Current Limitations
~~~~~~~~~~~~~~~~~~~

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

Commit


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

.. _lightweight markup language: https://en.wikipedia.org/wiki/Lightweight_markup_language


Future
------

.. Is it a good idea to include this?

Section outline

Support all rST elements, Sphinx

Highlight changes since last commit

Comments annotated with the user name

Backends: GitLab, DropBox, ...
