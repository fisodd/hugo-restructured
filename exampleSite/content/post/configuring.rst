+++
title = "Configuring Hugo Restructured"
author = "Alexander Carlton"
description = "What settings are available for Hugo Restructured."
date = "Sat Dec 30 09:56:54 PST 2017"
categories = ["Demo"]
tags = ["config", "theme", "Hugo"]
weight = 3

#hero_shade = """background: 
#   linear-gradient(217deg, rgba(255,0,0,.8), rgba(255,0,0,0) 70.71%), 
#   linear-gradient(127deg, rgba(0,255,0,.8), rgba(0,255,0,0) 70.71%), 
#   linear-gradient(336deg, rgba(0,0,255,.8), rgba(0,0,255,0) 70.71%)"""

hero_shade = """background:
   linear-gradient(27deg, #151515 5px, transparent 5px) 0 5px,
   linear-gradient(207deg, #151515 5px, transparent 5px) 10px 0px,
   linear-gradient(27deg, #222 5px, transparent 5px) 0px 10px,
   linear-gradient(207deg, #222 5px, transparent 5px) 10px 5px,
   linear-gradient(90deg, #1b1b1b 10px, transparent 10px),
   linear-gradient(#1d1d1d 25%, #1a1a1a 25%, #1a1a1a 50%, transparent 50%, transparent 75%, #242424 75%, #242424);
   background-color: #131313;
   background-size: 20px 20px"""
  
#hero_image = "/post/using-rest/rst.png"
hero_color = "darkred"

edge_shade = "background: linear-gradient(to bottom, white, gray)"
#edge_image = "/post/using-rest/rst-rotated.png"

+++

.. _contents:

.. contents::
   :class: sidebar

#############################
Configuring Hugo Restructured
#############################

The templates in this theme do utilize several settings
from the site's "config.toml" file and from each page's front matter.


Article Information
*******************

The "list" display for listing designated articles
and the "single" display for showing an article in full
both use several values pulled from the "config.toml" file
or from the designated pages' front matter.


Title
=====

As usual, the page title is taken from Hugo's ``.Title`` value
which is the string set for the "title" setting in the front matter
(or, for the home page, possibly set in "config.toml")


Description
===========

The "list" templates will use the value of the "description" setting
as part of the information provided with the link to the page.

If there is no value for "description", then the templates will
use the default extraction from the beginning of the page's content.


Author
======

If set, the "author" value will be added to the article's description
in the list displays |--| along with the date and
the categories and tags taxonomy values.


Page Coloring
*************

By default the splash of color used at the top of each page
is just a shade of red.

However, this splash can be redefined at the site level
(by setting values in "config.toml") or at the page level
(by specifying a setting in the page's front matter).


Hero Shade
==========

If set, ``hero_shade`` will be used as a CSS style for the actual HTML ``div``
that contains the page's heading area |--| and hence will override
the default splash of color.

This can be used to set the splash color, for example

.. code::

   hero_shade = "background: green"

This same setting can be used to create much flashier effects.

A wild color example is from https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Images/Using_CSS_gradients

.. code::

   hero_shade = """background:
      linear-gradient(217deg, rgba(255,0,0,.8), rgba(255,0,0,0) 70.71%),
      linear-gradient(127deg, rgba(0,255,0,.8), rgba(0,255,0,0) 70.71%),
      linear-gradient(336deg, rgba(0,0,255,.8), rgba(0,0,255,0) 70.71%)
   """

Or a carbon-fiber effect from http://lea.verou.me/css3patterns/#carbon

.. code::

   hero_shade = """background:
      linear-gradient(27deg, #151515 5px, transparent 5px) 0 5px,
      linear-gradient(207deg, #151515 5px, transparent 5px) 10px 0px,
      linear-gradient(27deg, #222 5px, transparent 5px) 0px 10px,
      linear-gradient(207deg, #222 5px, transparent 5px) 10px 5px,
      linear-gradient(90deg, #1b1b1b 10px, transparent 10px),
      linear-gradient(#1d1d1d 25%, #1a1a1a 25%, #1a1a1a 50%, transparent 50%, transparent 75%, #242424 75%, #242424);
      background-color: #131313;
      background-size: 20px 20px
   """


Hero Image
==========

If set, "hero_image" is assumed to be a path to an image file
to use as a hero image |--| a background image used to replace the
default splash of color at the top of the page.

If a page sets a value for "hero_image" in the front matter
that will override any value set in the site's main "config.toml" file.

.. code::

   hero_image = "/img/rst.png"


Hero Color
==========

If set, this specifies the color for the text in the hero heading.

Assuming a bright color splash, the default value is "white",
but for those cases where the hero splash is closer to pastel hues,
the ``hero_color`` can be set to something dark for readable contrast.

.. code::

   hero_color = "darkred"


Edge Shade
==========

For the displays that are wide enough to show some space to the left and right
of the main article column, it is possible to color that space with the
``edge_shade`` setting.

This works the same way as the ``hero_shade`` setting described above.

.. code::

   edge_shade = "background: linear-gradient(to bottom, white, gray)"


Edge Image
==========

The "image" version of the ``edge_shade`` setting |--| if set
it will cause the specified image file to be used as a repeating
pattern to fill in the spaces around the main column.

.. code::

   hero_image = "/img/rst-rotated.png"


Conflicting Settings
====================

Between the "config.toml" file and pages' front matter,
it is possible to find different values for the same settings.
In this case, the settings in a page's front matter override
the values obtained from the config file.
Within either location
if there is a setting for both an "image" and a "shade" setting,
the image is the setting used;
for example, if both ``hero_image`` and ``hero_shade`` are set,
the splash area will display the hero image.


.. |--| unicode:: U+2013   .. en dash

