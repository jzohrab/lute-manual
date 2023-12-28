# Why won't my epub import correctly?

Lute uses an open source epub parser named `openepub` kindly created by a Lute user to avoid licensing issues with currently available epub parsers.

The parser project is on GitHub at [https://github.com/sakolkar/openepub](https://github.com/sakolkar/openepub).[^1]

Parsing is always a challenge, and some epubs may contain strange formatting that the library can't handle.  If your epub doesn't parse correctly, please open a GitHub issue in the `openepub` repo.

In the meantime, use any of the tools available to convert your epub to a text file for import, such as [Calibre](https://calibre-ebook.com/).

[^1]: as at Dec 28, 2023!