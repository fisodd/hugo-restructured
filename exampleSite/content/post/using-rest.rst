+++
title = "Using Hugo Restructured"
author = "Alexander Carlton"
description = "An introduction to using reStructuredText with Hugo Restructured."
date = "Sat Dec 30 09:59:24 PST 2017"
categories = ["Demo"]
tags = ["reStructuredText", "responsive", "theme", "markup"]
weight = 2

+++

.. class:: sidebar

.. contents:: Table of Contents


##############################
Using reStructuredText in Hugo
##############################

Hugo does support
`reStructuredText <http://docutils.sourceforge.org/rst.html>`__
as one of the
`additional formats <https://gohugo.io/content-management/formats/#additional-formats-through-external-helpers>`__
in Hugo.
However, there is not a lot of documentation about how
to use reStructuredText (or ReST) in a Hugo setup.

The `Hugo and reStructuredText post </post/hugo-and-rest/>`__
provides a decent example of what can be done with this setup.
What follows here is some basic information and details not
covered in that demonstration page.


reStructuredText Background
***************************

.. figure:: /img/rst-rotated.png
   :align: left

By default, Hugo uses
`BlackFriday syntax <http://gohugo.io/content-management/formats/>`__
as the input markup,
and this offers several extensions to the deliberately simplistic
`markdown syntax <https://daringfireball.net/projects/markdown/>`__.

Rather than use extensions to what was defined to be simple,
working with Hugo and reStructuredText
enables the same clean workflow that a plaintext markup language provides
but with a markup language
that was designed from the start to handle far more than a simple blog page.

.. class:: sidebar narrow

.. [*] This is a symbolic note, implemented as a sidenote.

For example, BlackFriday and other markdown processors have added
a form of footnotes to the original syntax.
reStructuredText not only defined a clean footnote syntax,
this syntax can separate sequences of footnotes (one set numbered\ [#]_,
the other set tracked by a series of symbols\ [*]_) and even support
a separate set of citation references [ReST]_ as is done for academic journals.
Hence, as has been done for the notes in this paragraph,
it is possible to have a set of notes
that are defined at the end of the page
and another set of notes that are defined and displayed
inline with the content.


.. sidebar:: ReST Directives
   :class: narrow

   A partial list of ReST directives
   pulled from a table of contents
   in the ReST documentation.

   .. class:: bulletless

   * `Admonitions <http://docutils.sourceforge.net/docs/ref/rst/directives.html#admonitions>`__
   * `Image <http://docutils.sourceforge.net/docs/ref/rst/directives.html#image>`__
   * `Figure <http://docutils.sourceforge.net/docs/ref/rst/directives.html#figure>`__
   * `Topic <http://docutils.sourceforge.net/docs/ref/rst/directives.html#topic>`__
   * `Sidebar <http://docutils.sourceforge.net/docs/ref/rst/directives.html#sidebar>`__
   * `Code <http://docutils.sourceforge.net/docs/ref/rst/directives.html#code>`__
   * `Math <http://docutils.sourceforge.net/docs/ref/rst/directives.html#math>`__
   * `Epigraph <http://docutils.sourceforge.net/docs/ref/rst/directives.html#epigraph>`__
   * `Highlights <http://docutils.sourceforge.net/docs/ref/rst/directives.html#highlights>`__
   * `Pull-Quote <http://docutils.sourceforge.net/docs/ref/rst/directives.html#pull-quote>`__
   * `Table <http://docutils.sourceforge.net/docs/ref/rst/directives.html#table>`__
   * `CSV Table <http://docutils.sourceforge.net/docs/ref/rst/directives.html#id4>`__
   * `List Table <http://docutils.sourceforge.net/docs/ref/rst/directives.html#list-table>`__


Perhaps much more relevant to a Hugo audience,
reStructuredText provides support for a variety of useful features
for those who would like to move beyond just a column of text.
reStructuredText supports both
images as well as figures
(images that have a caption or legend associated with the image),
sidebars (independent threads of text that are formatted into a separate
column next to main running text),
also pull quotes which are different from epigraphs,
as well as admonitions (call out boxes for tips or warnings).

reStructuredText also offers a clean way to specify additional parameters
for each elements in an article.
With this, there is a standard way for an author to specify
that a figure is to be flushed to the left, or the right,
rather than centered in the column.
This also allows us a way to specify if a sidebar is
narrow, or extra wide.


Learning reStructuredText
=========================

.. sidebar:: ReST References
   :class: align-left narrow

   .. class:: bulletless

   * `Quick Start <http://docutils.sourceforge.net/docs/user/rst/quickstart.html>`__
   * `Cheatsheet <http://docutils.sourceforge.net/docs/user/rst/cheatsheet.html>`__
   * `Examples <http://docutils.sourceforge.net/docs/user/rst/quickref.html>`__

   .. class:: bulletless

   * `Specification <http://docutils.sourceforge.net/docs/ref/rst/restructuredtext.html>`__
   * `Directives <http://docutils.sourceforge.net/docs/ref/rst/directives.html>`__
   * `Text Roles <http://docutils.sourceforge.net/docs/ref/rst/roles.html>`__

The basics of reStructuredText is not very different from
any other plaintext markup, so it is easy to get started.
Separate paragraphs with blank lines,
use an asterisk pattern such as ``*emphasis*`` to mark *emphasis*,
use double asterisks such as ``**bold**`` to be **bold**.

Much of the basics are demonstrated
in the
`Quick Start Guide <http://docutils.sourceforge.net/docs/user/rst/quickstart.html>`__
and are covered
in the
`Quick Syntax Overview <http://docutils.sourceforge.net/docs/ref/rst/restructuredtext.html#quick-syntax-overview>`__.

.. sidebar:: Anonymous Hyperlink References
   :class: titleless

   While reStructuredText provides a very rich system for
   defining and referencing hyperlinks,
   there is also support for a hyperlink reference
   somewhat similar to the common markdown that uses ``[Text](URL)``.
   In reStructuredText the similar form would be
   ```Text <URL>`__``
   (the back-quotes serve a somewhat similar function
   as standard markdown's square-brackets,
   the angle-brackets are similar to standard markdown's parentheses,
   and the trailing underscores are reStructuredText's way
   of marking a reference
   [specifically, an anonymous reference where there is no need
   to track the tag to find a definition elswhere in the document]).

Perhaps the most difficult concept in basic reStructuredText
is how hyperlinks are formatted.
To enable better readability of the raw text,
in reStructuredText hyperlinks are treated like footnotes and citations;
the main text just has a reference to a link,
and the ugly details of the URL itself is defined elsewhere in the document.

The full power of reStructuredText comes in its extensible
`Directives <http://docutils.sourceforge.net/docs/ref/rst/directives.html>`__
such as Figures and Tables.
By use of a specific syntax for these directives,
it is easy to specify different options for each use,
and the same system allows implementations to define extensions
such as :title:`Hugo Restructured`'s ``narrow`` and ``wide`` options for sidebars.


.. figure:: /img/rst.png
   :align: center


Hugo Specific Extensions
************************

reStructuredText, and the entire Docutils system,
is both powerful and flexible,
capable of generating entire volume-sets of documentation.
:title:`Hugo Restructured` focuses Docutil's tools
on the relatively simple needs of blog-centric Hugo |--|
but while the content for blogs may be relatively simple
compared to a documentation system's more typical material,
difficulties arise from the reality that the audience for blog content
often encompasses a much wider and richer variety of browser environments.

The CSS provided with :title:`Hugo Restructured`
is based on the HTML generated by Docutils.
Any content that follows
`reStructuredText definitions <http://docutils.sourceforge.net/docs/user/rst/quickstart.html>`__
should be well handled.

.. note::
   :class: sidebar narrow align-left

   It can be illustrative to see the original markup,
   to compare with the finished results.
   A copy of the raw markup that was used for this page is available
   within the
   `source repository <https://github.com/fisodd/hugo-restructured/>`__.

There are a few areas where this shift of focus and emphasis
can be greatly assisted if the authors respect a few details
in the markup they write.
Since reStructuredText is designed to be extensible,
many useful effects can be achieved through existing CSS definitions
with nothing more than a bit of care to define a few optional values
when using some of the more powerful directives.


Making Figures Responsive
=========================

The HTML generated by the Docutils that support reStructuredText
is generally constructed well enough to be adaptable to a wide
range of usages.
However, being specific in the markup can help
make the figures more responsive to mobile visitors
and the many varieties of browser display sizes.

.. figure:: /img/rst.png
   :align: left
   :figwidth: 30%
   :width: 100%

Specifically, for the figure directives
it may help to specify a ``:figwidth:`` option as a percentage, e.g. 30%,
as this allows the figure to scale the image's display size
to match the relative size of the column in the user's browser display.
Note: Specifying a fixed pixel width for figures
can lead to problems as browsers adapt to different window sizes.

In addition, providing an additional ``:width:`` option,
even ``:width: 100%`` just to restate the desire to use 100% of the width,
provides a necessary definition so that the image can be constrained
to remain within the figure's defined space.
Without this additional ``:width:`` option,
images may spill out beyond the figure to either obscure the other
content or run off the far edge of the page.


Sidebars
========

.. sidebar:: Sidebars

   To quote the
   `documentation <http://docutils.sourceforge.net/docs/ref/rst/directives.html#sidebar>`__:

   Sidebars are like miniature, parallel documents
   that occur inside other documents,
   providing related or reference material.
   A sidebar is typically offset by a border
   and "floats" to the side of the page;
   the document's main text may flow around it.
   Sidebars can also be likened to super-footnotes;
   their content is outside of the flow of the document's main text.

reStructuredText defines a ``sidebar`` directive that creates a
side channel of content with a title that can be displayed alongside
the main column of the article.


Overriding the Sidebar Defaults
-------------------------------

:title:`Hugo Restructured` enables a sidebar-like treatment
for several other elements.
Pull-quotes, admonitions, and topics can be given the same treatment
if they are defined to include a ``class`` of "sidebar".
Thus these items can be shifted from their usual placement
across the entire width of the column
to instead become floating elements beside the main body of content.

.. sidebar:: Narrow
   :class: narrow titleless

   This is a narrow sidebar.
   Potentially useful if the content is skinny.

   ===== ====
   Num   Word
   ===== ====
    0    Zero
    1    One
    2    Two
    3    Many
    4    Many
   ...   ...
   |inf| Many
   ===== ====

.. |INF| replace:: :math:`\infty`

Adding a ``:class: titleless`` option
to a topic, sidebar, or admonition directive
will suppress the display of that block's title.
This is occasionally helpful
when a block's title ends up being more distracting than useful.

Add a ``:class: narrow`` or ``:class: wide`` option
to the sidebar definition and the matching CSS specification will be used,
so sidebars can be made to target
20% (narrow) or 40% (default) or 60% (wide)
of the width of the column.

.. class:: sidebar align-left

.. pull-quote::
   Predictably, demonstrating too many features within a single webpage
   leads to overly cluttered looking results.

Furthermore, several of the other directives,
notably the admonition and topic directives,
can be given a "sidebar" treatment rather than their default
front-and-center appearance.
Just by specifying an optional ``:class: sidebar``
to the directive's definition.
This can be useful for those cases where the author
chooses to place less emphasis on the material in the directive.

Finally, if a full-size pull-quote is too much,
the CSS provided with this theme
enables this same "sidebar" treatment of pull-quotes.
However, the markup syntax is a bit more cumbersome
since the definition for pull-quote in reStructuredText
does not include optional arguments.
Still, the use of reStructuredText's ``class`` directive
will assign the specified class to whatever is the directive that follows.

.. code:: ReST

   .. class:: sidebar align-left

   .. pull-quote::
      Predictably, demonstrating too many features within a single webpage
      leads to overly cluttered looking results.


.. figure:: /img/rst-rotated.png
   :align: right

Left and Right Alignments
-------------------------

The ``figure`` and ``image`` directives already understand
``:align: left`` and ``:align: right`` options.
:title:`Hugo Restructured`'s CSS implements the means to push these elements
flush left or flush right and allows the main text to flow around
these elements.

.. admonition:: Tip
   :class: align-left

   Admonitions can be pushed to the left.

Additionally, :title:`Hugo Restructured`'s CSS enables similar treatments
for ``sidebar``, ``admonition``, and ``pull-quote`` elements whenever
these elements are given a ``class`` parameter of ``align-left``
or ``align-right``.

.. code:: ReST

   .. admonition:: Tip
      :class: align-left
   
      Admonitions can be pushed to the left.


Code Displays
=============

As has been demonstrated elsewhere in this page,
:title:`Hugo Restructured` includes support for
`code <http://docutils.sourceforge.net/docs/ref/rst/directives.html#code>`__
blocks.

.. sidebar:: Hugo's Chroma
   :class: align-left

   The Docutils parser is independent of the default Hugo markdown parser
   and hence does not invoke Hugo's default
   `syntax highlighting
   <https://gohugo.io/content-management/syntax-highlighting/>`__,
   and so does not include the Chroma highlighter
   that is part of the more recent releases of Hugo.
   
   Full support for syntax highlighting may come
   if/when there is a native Go implementation of reStructuredText.
   Unfortunately, while there are different implementations of
   reStructuredText in Go, none has yet reached sufficient maturity
   to be included in Hugo and
   `the ticket <https://github.com/gohugoio/hugo/issues/1436>`__
   for this enhancement request
   was closed in late 2017 for lack of activity.
   
The Docutils package that implements reStructuredText
utilizes the
`Pygments <http://pygments.org/>`__
package to perform parsing and
marking of code blocks |--| this is the same package
that Hugo used prior to switching to the Go-native
Chroma code processor.

:title:`Hugo Restructured`'s CSS implements
a somewhat muted coloring based on Pygment's "lovelace" style.
Those that are interested, the CSS can be replaced by a different style.
Because Docutils uses the "long-form" option for class names
this does mean that Pygment's default method of generating style definitions
does not work directly |--| the short class names need to be swapped
with the longer class names that by default show in the comments.

Something like the following Unix script can be useful to get suitable CSS:

.. code:: Bash

   #!/bin/bash
   
   style=$1
   if [ "$style" = "" ]
   then
           echo "Need to specify a style name that Pygments recognizes"
           exit 1
   fi
   
   regularexpression='s/^\.(\w+) \{ (.*) \} \/\* (.*) \*\//.\L$3 { $2 } \/* $1 *\//'
           # first match: a character string after a period at the beginning
           # second match: the stuff between the curly braces
           # third match: the stuff between the comment markers
           # output: lower case of 3rd match, 2nd inside braces, 1st in comment
   
   
   pygmentize -f html -S $style | perl -pe "$regularexpression"
   
   exit $?


Hugo Restructured's Classes
===========================

Along the way there have been a few potentially useful classes
added to Hero Restructured's CSS.

Classes for Sidebars
--------------------

As noted above,
sidebars (and other elements that can be given a ``sidebar`` class)
can have additional classes added to their definition to enable
potentially useful effects.

The complete list of optional classes for sidebars is below.

align-left
   By default sidebars are flushed right, with a class of ``align-left``
   the specified sidebar item will be flushed left.
   Works similarly to figures that specify an option of ``:align: left``.

align-right
   This can override a left leaning item to instead be flushed right.

align-center
   Let an element span the width of the available column
   with its content centered in the available space.

titleless
   Suppresses the visibility of a title;
   sometimes useful with the ``sidebar`` directive that insists
   that every properly defined sidebar must display a title.

narrow
   Reduce the width of the sidebar from 40% to 20% of the main column.

wide
   Expand the sidebar to cover 60% of the main column.


.. sidebar:: Bulletless List Example

   The list of "ReST Directives" above includes markup
   like the code below.

   .. code:: ReST
   
      .. class:: bulletless
   
      * Admonitions
      * Image
      * Figure

Bulletless Lists
----------------

For those cases where a fully formatted list is over kill
(and perhaps would not fit in a narrow sidebar),
a list can be given the class ``bulletless``
which would lead the list being formatted without bullets
and with a notably smaller amount of indentation.


Responsive Lists
----------------

By default, the indentation for a nested list
is a fixed amount of pixels |--| which can be a problem on small devices,
especially if the list is attempting to fit within a sidebar or other
place where width is limited.

The CSS for :title:`Hugo Restructured` implements a ``responsive`` class
for lists which will drop the bullets from an unnumbered list
and will shrink the amount of indentation.

This is the difference between:

* One
   * Two
      * Three

and (which will look the same unless the browser display is narrow):

.. class:: responsive

* One
   * Two
      * Three

implemented as:

.. code:: ReST

   .. class:: responsive

   * One
      * Two
         * Three

This CSS does recognize attempts to place a
`table of contents <http://docutils.sourceforge.net/docs/ref/rst/directives.html#table-of-contents>`__
in a
`sidebar <http://docutils.sourceforge.net/docs/ref/rst/directives.html#sidebar>`__
and will use this responsive form in those cases.


Responsive Tables
-----------------

When the display gets narrow (such as on some mobile devices)
some standard HTML tables become difficult to read.
For example, tables that have many columns:

=== === === === === === === === === === === === ===
Mon Jan Feb Mar Apr May Jun Jul Aug Sep Oct Nov Dec
=== === === === === === === === === === === === ===
°C  5   7   9   11  14  16  19  19  17  13  10  7
°F  41  45  48  52  57  61  66  66  63  55  50  45
=== === === === === === === === === === === === ===

These may not fit into narrow displays |--|
resulting in page content that runs off the end of the display
and hence cannot be seen at all.
In the more severe cases it may be necessary on small devices
to reorient a wide table in more of a long-list format
so that small screens can scroll through the entire content.
:title:`Hugo Restructured` add an optional ``responsive`` class 
for table definitions that will trigger an alternative display
when the browser display is very narrow.

The table below is a copy of the table above with
the addition of this ``responsive`` class to the definition.
Notice that the table format will be displayed differently
when the width of the browser is recognized to be narrow.

.. class:: responsive

=== === === === === === === === === === === === ===
Mon Jan Feb Mar Apr May Jun Jul Aug Sep Oct Nov Dec
=== === === === === === === === === === === === ===
°C  5   7   9   11  14  16  19  19  17  13  10  7
°F  41  45  48  52  57  61  66  66  63  55  50  45
=== === === === === === === === === === === === ===

Responsive tables in markup
is something of a cure for a corner-case
that is probably best avoided rather than addressed.
Still, there are cases where this kind of transformation can be useful,
so :title:`Hugo Restructured` offers this as a simple solution
that perhaps may help.


.. the dots below create a horizontal line to separate the notes

....

.. [#] This is a numeric note,
   implemented as a traditional footnote
   (shown at the end of the page).
   The footnote label is a link to return back
   to the previous part of the page.

.. [ReST] :title:`reStructuredText Documentation`, http://docutils.sourceforge.net/rst.html

.. |--| unicode:: U+2013   .. en dash

