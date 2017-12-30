# Hugo Restructured

A theme for [Hugo](https://gohugo.io/)
that takes advantage of
[reStructuredText](http://docutils.sourceforge.net/rst.html)
as the input markup.

See the
[live demo](https://hugo-restructured-demo.netlify.com).

Features

- Responsive page layout (scales from 300 to 1300 pixels wide)
- Supports reStructuredText markup features

Including

- [Images](http://docutils.sourceforge.net/docs/ref/rst/directives.html#image) and [figures](http://docutils.sourceforge.net/docs/ref/rst/directives.html#figure), both right- and left-aligned
- [Footnotes](http://docutils.sourceforge.net/docs/ref/rst/restructuredtext.html#footnotes) and [citations](http://docutils.sourceforge.net/docs/ref/rst/restructuredtext.html#citations)
- [Pull-quotes](http://docutils.sourceforge.net/docs/ref/rst/directives.html#pull-quote), and [epigraphs](http://docutils.sourceforge.net/docs/ref/rst/directives.html#epigraph)
- [Sidebars](http://docutils.sourceforge.net/docs/ref/rst/directives.html#sidebar) (implemented in narrow, standard, and wide forms)
- [Admonitions](http://docutils.sourceforge.net/docs/ref/rst/directives.html#admonitions)
and [topics](http://docutils.sourceforge.net/docs/ref/rst/directives.html#topic), notably [table of contents topics](http://docutils.sourceforge.net/docs/ref/rst/directives.html#table-of-contents)
- Support for [Math](http://docutils.sourceforge.net/docs/ref/rst/directives.html#math) and [Code](http://docutils.sourceforge.net/docs/ref/rst/directives.html#code) directives
- [Tables](http://docutils.sourceforge.net/docs/ref/rst/restructuredtext.html#tables), including [list-tables](http://docutils.sourceforge.net/docs/ref/rst/directives.html#list-table), as well as [field lists](http://docutils.sourceforge.net/docs/ref/rst/restructuredtext.html#field-lists), including [bibliographic fields](http://docutils.sourceforge.net/docs/ref/rst/restructuredtext.html#bibliographic-fields)

Also

- Pages begin with a splash of color with support for hero images or background gradients

![Screenshot](https://github.com/fisodd/hugo-restructured/raw/master/images/tn.png)


## Installation

Installation is much like any other Hugo theme.


### Getting started

Inside the folder of your Hugo site run:

    $ cd themes
    $ git clone https://github.com/fisodd/hugo-restructured.git

For more information read
[install and use themes](https://gohugo.io/themes/installing-and-using-themes/)
or begin with Hugo's
[get started](//gohugo.io/overview/installing/) help page.


### The config file

Inside the
[`exampleSite`](https://github.com/fisodd/hugo-restructured/tree/master/exampleSite)
folder of this theme, there is a file called
[`config.toml`](https://github.com/fisodd/hugo-restructured/blob/master/exampleSite/config.toml).
Use this configuration as an example,
and modify to suit your needs.


### Create your content as ReST files

Hugo recognizes files ending with a ".rst" suffix as
[reStructuredText](http://docutils.sourceforge.net/rst.html)
and will call out to the [docutils](http://docutils.sourceforge.net/)
python package to process these files.

example: hugo new content/post/first-post.rst

To learn more about reStructuredText markup, start with
[a reStructuredText Primer](http://docutils.sourceforge.net/docs/user/rst/quickstart.html).


### Change the hero background

The top part of each page has an area of color or potentially an image.
For any page or post you can specify a hero image for this area
by including the local path in front matter
(see content in the exampleSite folder for examples):
`hero_image: '/images/gohugo-default-sample-hero-image.jpg'`

An image is not required.
The hero background can also be configured by the 'hero_shade' setting.
The 'hero_shade' setting in the front matter can take a full
[CSS background definition](https://developer.mozilla.org/en-US/docs/Web/CSS/background),
and can be used to set any HTML color,
or even use a gradient instead by specifying a
[linear gradient](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Images/Using_CSS_gradients#Using_linear_gradients).

example: `hero_shade = "background: linear_gradient(to right, blue, pink);"`


### See the results

In order to see your site in action, run Hugo's built-in local server.

    $ hugo server

Now enter [localhost:1313](localhost:1313)
in the address bar of your browser.


## License

This theme is released under the MIT License.

The specifics can be found within the [License](/LICENSE)


## Recognition

The author learned most of what he has learned about Hugo themes
by studying the excellent example of the
[Ananke theme](https://github.com/budparr/gohugo-theme-ananke).
I am very grateful for the clean implementation and the helpful comments.

Also, many, many thanks to
[all the folks](https://github.com/gohugoio/hugo/graphs/contributors)
who make Hugo rock.


## See Also

* [Ananke Theme](https://github.com/budparr/gohugo-theme-ananke)

