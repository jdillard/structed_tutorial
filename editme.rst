
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
`lightweight markup language`_ that supports publishing to a multitude of
formats including HTML, EPub and PDF. *struct:ed* facilitates editing of
reStructuredText documents by providing an environment that frees the user from
having to remember the syntax for all of the different document elements and
eliminating the occurrence of syntax errors. Additionally, it represents the
document in a format that is easy to navigate, for example by displaying the
section titles in a larger font.

These reStructuredText documents need to be stored somewhere, of course. The
first backend *struct:ed* supports is **GitHub**. Documents are stored in a git
repository and their edit history is thus being preserved. *struct:ed* works on
a repository level; the panel on the left shows a tree of the files in the
repository. Clicking a file will open it for editing. Clicking the *Commit*
button at the top right will commit changes to all files to the *structed*
branch of the repository.

Finally, *struct:ed* supports **collaborative editing**. Several users can edit
a document simultaneously. Their changes will be immediately visible to others
editing the same document. Note that all users need *push* access to a
repository to be able to edit documents stored in it.


Current Limitations
~~~~~~~~~~~~~~~~~~~

As this is a only a preview version of struct:ed, there are some limitations
you should be aware of:

* Not all reStructuredText document elements are supported. Those that are
  currently supported are discussed in the next section.

* There are many opportunities for facilitating editing documents, such as
  popping up a list of available reference targets when inserting a reference.
  However, very few of these writing aids are available at this point.


Editing a Document
------------------

The toolbar at the top helps inserting structural, body and inline elements
into the document. Hover your mouse pointer over each of the buttons to learn
what they do. In addition to a label, the tooltip also includes an input rule
(in orange) and sometimes a keyboard shortcut.

**Input rules** allow applying inline styles or inserting document elements by
means of specific character patterns. These have been chosen to be the same as
the corresponding reStructuredText syntax if possible, or similar otherwise.

Hint: use the toolbar as a cheat sheet to quickly look up input rules and
keyboard shortcuts.


Structural Elements
-------------------

Structural elements include section titles or **headings**. Use the heading
toolbar button to toggle between a plain paragraph and a heading. With the text
cursor positioned on a heading, use the right/left arrow buttons to in/decrease
the heading level. Go ahead, try this on the next paragraph!

I want to be a heading!

You can set the heading level in a single step by using the *Ctrl-Alt-<number>*
keyboard shortcut corresponding to the heading level (1 through 6). Use
*Ctrl-Alt-0* (zero) to reset a title to a paragraph. *Alt-Right* and *Alt-Left*
increase and decrease the heading level.

To create a new heading, start a paragraph with a series of hashes (``#``)
followed by a space. The number of hashes determines the heading level. You can
also convert an existing paragraph to a heading by inserting hashes and a space
at the front of the paragraph. Try creating a new level-3 heading below.

Note that struct:ed will enforce a consistent document structure by
automatically fixing heading levels. For example, if you try to insert a
level-6 heading below a level-2 heading, it will automatically be changed to a
level-3 heading.

The other structural element is the **transition** which divides the section.
Enter four consecutive hyphens (``----``) at the start of a paragraph to insert
a transition. Why don't you add a transition below?


Body Elements
-------------


Paragraphs
~~~~~~~~~~

The default body element, created by pressing *Enter*, is the paragraph. You
can convert some other types of body elements to a paragraph by means of the
*Ctrl-Alt-0* shortcut.

Inside paragraphs, **inline markup** can be applied to words or phrases. These
markup constructs have simple input rules:

* **emphasis**: wrap text in single asterisks (``*``)

* **strong emphasis**: wrap text in double asterisks (``**``)

* **literals**: wrap text in double backticks (``````)

This markup can be also be applied to selected text by using the keyboard
shortcuts shown in the tooltips.

**Subscript** and **superscript** employ the generic reStructuredText
interpreted text role syntax. Type ``:sub:`` or ``:sup:`` followed by the text
to mark up enclosed in single backticks (`````). For example, ``:sup:`super!```
results in :sup:`super!`.

**References** create internal or external hyperlinks. When not specifying a
target, the reference links to the target matching the marked name (targets are
discussed below). For example, ```mytarget`_`` creates a reference to
``mytarget``. To link to ``mytarget`` using a different link label, specify the
target within less/greater than characters, like so: ```My Label
<mytarget>`_``. This reference is displayed as follows: `My Label
<mytarget_>`_. Clicking the reference will pop up a tooltip that allows you to
change the target. The label can be edited just like normal text.

Finally, **substitution references** are labels that are to be replaced by a
text string when a document is published. The corresponding `substitution
definition`_ determines the text that will be |substituted|. You can create a
substitution reference by wrapping text within vertical lines (``|``).

Note that reStructuredText does not support nesting inline markup. However,
since we only need to describe semantics and not presentation, this is not
necessarily a problem. `Custom interpreted text roles`_ allow for extra classes
of inline markup to be defined which can be styled as required on publication.


Block Quotes
~~~~~~~~~~~~

The left/right toolbar buttons and corresponding keyboard shortcuts
increase/decrease the block quote level of a paragraph. Entering two spaces at
the front of a paragraph will also increase the quote level. Let's transform
the following paragraph into a block quote by any means you fancy:

Reality is merely an illusion, albeit a very persistent one.


Literal Blocks
~~~~~~~~~~~~~~

Literal blocks can be used for code snippets or other preformatted text. Use
the *Ctrl-Alt-=* shortcut to convert a paragraph to a literal block or enter
two colons (``::``) at the start of a paragraph. Line feed are inserted into
the literal block when pressing *Enter*. To exit from the literal block using
*Cmd-Enter* on Mac or *Ctrl-Enter* on other platforms. Below is an example of a
literal block:

::

  for i in range(5):
      print(i)

Note that inline markup is not supported within literal blocks.


Lists
~~~~~

To convert a paragraph to a **bullet list** item, use the *Ctrl-Alt-B*
shortcut. A new bullet list can be created by starting a paragraph with a
hyphen (``-``) and a space, after which you can start entering the list item
text. Pressing *Enter* will create a new list item. At this point you have
three options:

1. Enter the text for the new list item.

2. Press *Enter* to end the list.

3. Press *Backspace* to remove the second bullet. The cursor is now at the
   start of the second paragraph of the first list item.

**Enumerated lists** are very similar to bullet lists. They can be created by
starting a paragrah with ``1.`` followed by a space. Paragraphs can be
transformed to a list item using the *Ctrl-Alt-E* keyboard shortcut.

List items can contain any number of body elements. These are not limited to
paragraphs, so you can include a literal block or another list, as illustrated
below. Be sure to perform some experiments!

* This is a plain paragraph with *inline markup*.

  This is the second paragraph of the first list item.

* Use *Alt-Right* or *Tab* to increase the list item level.

  - Use *Alt-Left* or *Shift-Tab* to decrease the list item level.

  - Use *Ctrl-Alt-E* to transform this list to an enumerated list.

* ::

    This is a literal block...

  1. followed by an enumerated list

  2. with two list items


Comments
~~~~~~~~

Comments are discarded when plublishing the document. Use these to keep track
of to-do items or meta-discussions. Create a comment by starting a paragraph
with double full stop characters (``..``).

.. TODO: improve wording of this section


Directives
----------

.. _targets:

target (anchor), optional alias

.. _substitution definition:

substitution definition

custom interpreted text role

Custom directives (future).

.. _wysiwym: https://en.wikipedia.org/wiki/WYSIWYM

.. _lbl: abcdeffef_

.. _restructuredtext: https://en.wikipedia.org/wiki/ReStructuredText

.. _lightweight markup language: https://en.wikipedia.org/wiki/Lightweight_markup_language


Future
------

.. Is it a good idea to include this?

Section outline

Support all rST elements, Sphinx

Highlight changes since last commit

Comments annotated with the user name

Backends: GitLab, DropBox, ...
