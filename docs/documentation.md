## Installation

Download Pantyshot from [Github][1] and run the following command. Keep in mind
that Pantyshot has only been tested with Python 2.7.

    python setup.py install

And you're done.


 [1]: https://github.com/FSX/pantyshot


## Usage

Example:

    import pantyshot

    pantyshot.html('Hello, world!')

With extensions and render flags:

    import pantyshot as p

    p.html(
        'Hello, world!',
        p.EXT_AUTOLINK | p.EXT_TABLES,
        p.HTML_EXPAND_TABS
    )

In combination with functools.partial:

    import functools
    import pantyshot as p

    markdown = functools.partial(
        p.html,
        extensions=p.EXT_AUTOLINK | p.EXT_TABLES,
        render_flags=p.HTML_EXPAND_TABS
    )
    markdown('Awesome!')

Or generate a table of contents:

    pantyshot.toc('''
    # Header one

    Some text here.

    ## Header two

    Some more text
    ''')


## API

All of the following functions and constants are from the `pantyshot` module.


### pantyshot.html

The `html` function converts the Markdown text to HTML. It accepts the following arguments.

 * `text`: The Markdown source text.
 * `extensions`: One or more extension constants (optional).
 * `render_flags`: One or more render flag constants (optional).


### pantyshot.toc

The `toc` function generates a table of contents and accepts the following argument.

 * `text`: The Markdown source text.


### Extensions

The functionality of the following constants is explained at *Markdown Extensions*.

    EXT_AUTOLINK
    EXT_LAX_HTML_BLOCKS
    EXT_TABLES
    EXT_NO_INTRA_EMPHASIS
    EXT_STRIKETHROUGH
    EXT_FENCED_CODE
    EXT_SPACE_HEADERS


### Render Flags

The functionality of the following constants is explained at *Render Flags*.


    HTML_GITHUB_BLOCKCODE
    HTML_SKIP_HTML
    HTML_SKIP_STYLE
    HTML_HARD_WRAP
    HTML_TOC
    HTML_SKIP_LINKS
    HTML_SAFELINK
    HTML_SKIP_IMAGES
    HTML_EXPAND_TABS
    HTML_USE_XHTML
    HTML_SMARTYPANTS


## Changelog

### 0.2.0 (2011-05-??)

 * Added Smartypants render flag.
 * Added a ``toc`` function that outputs a table of contents.
 * Renamed ``markdown`` function to ``html``.
 * Updated Upskirt files;
   See commits from 2011-05-02 to 2011-05-16:
   https://github.com/tanoku/upskirt/commits/master/


### 0.1.1 (2011-05-01)

 * Updated Upskirt files; a HTML escaping bug in the XHTML renderer was fixed.


### 0.1.0 (2011-05-01)

 * Initial release.




## License

    Copyright (C) 2011 by Frank Smit <frank@61924.nl>

    Permission is hereby granted, free of charge, to any person obtaining a copy
    of this software and associated documentation files (the "Software"), to deal
    in the Software without restriction, including without limitation the rights
    to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
    copies of the Software, and to permit persons to whom the Software is
    furnished to do so, subject to the following conditions:

    The above copyright notice and this permission notice shall be included in
    all copies or substantial portions of the Software.

    THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
    IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
    FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
    AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
    LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
    OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN
    THE SOFTWARE.