# APEX Calculus, PreTeXt edition

This repository contains the source code for the APEX Calculus textbook.

APEX Calculus was originally [written in LaTeX](https://github.com/APEXCalculus/APEXCalculusV4); this version of the book uses [https://pretextbook.org](PreTeXt).

To build the book, use of the [PreTeXt CLI](https://github.com/PreTeXtBook/pretext-cli) is recommended.
See below for instructions on how to use GitHub Codespaces to contribute to this repository with only a
web browser.

Note that the build time is quite long. 
(If you're building on Windows, make sure your computer is not set to sleep after an hour!)

Preparation for generating APEX Calculus from source:

Software requirements:
- a recent LaTeX distribution that includes Asymptote
- Python (version 3.13 or later)
- the PreTeXt CLI (do `pip install pretext`)

Configuration:

- In `publication/publication.ptx`, change the `baseurl` to the URL where your copy will be hosted, and set the `webwork` server to your local server.
- If you wish to set a custom stylesheet, place it in the `style` folder, and add `<xsl>style/custom-style.xsl</xsl>` tags to the appropriate targets in the `project.ptx` file, where you should of course replace `custom-style.xsl` with whatever you named your style file.
- You can also use `<xsl>...</xsl>` tags in `project.ptx` to point to a newer version of one of the PreTeXt XSL files than the one that ships with the CLI. (This is not officially supported, so use with caution.)

To build HTML, run `pretext build apex-calculus`

To build a version with videos, run `pretext build apex-video`

To build PDF, run `pretext build apex-pdf`.

The following variations are also available:
- `pretext build apex-pdf-video`: include QR code links to videos
- `pretext build apex-print`: black and white, for print on demand
- `pretext build apex-print-video`: black and white, with video links
- `pretext build apex-color-print`: in color, but two-sided layout for printing
- `pretext build latex-color-print-video`: as above, but with QR codes for videos

The PDF should work "out of the box", but in case something doesn't look right, the PDF build includes the `.tex` file.
You can edit this and rebuild as needed.

**Note**: changes to placement of images in the margin are controlled in the PreTeXt source.
Changes to page breaks are controlled in the publisher files.

At this time, EPUB generation is not fully supported.

## GitHub Codespaces support

This repository is configured to support GitHub Codespaces. If you are not an owner
of this repository, first create a fork.

Then to set up a codespace in your browser, click the green `Code` button [on your fork],
click the "Codespaces" tab, and then click "Create codespace on main". After a few
minutes, you'll have a PreTeXt-ready authoring environment, and can use the PreTeXt-tools
extension (automatically installed) at the bottom of the page to manage your project.

Build times are long (one build of the default HTML target took around an hour in testing),
so be sure your codespace is [configured to not go to sleep before it's done][0]. You may also
want to set up your codespace [to not expire so cached assets aren't rebuilt][1].

[0]: https://docs.github.com/en/codespaces/setting-your-user-preferences/setting-your-timeout-period-for-github-codespaces
[1]: https://docs.github.com/en/codespaces/setting-your-user-preferences/configuring-automatic-deletion-of-your-codespaces
