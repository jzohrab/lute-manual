# My text file import is givinga "utf-8 encoding" error message

Lute can only import utf-8 encoded text files.[^1]

Your file may already be in utf-8 encoding, but if not, you'll need to first convert it.

I don't know of all of the options available, but here are some suggestions:

* [https://subtitletools.com/convert-text-files-to-utf8-online](https://subtitletools.com/convert-text-files-to-utf8-online)
* if using Microsoft Word, you can export your file, but you have to choose "other encoding" and then unicode (utf-8).  See e.g. [https://support.3playmedia.com/hc/en-us/articles/227730088-Exporting-a-UTF-8-txt-file-from-Word](https://support.3playmedia.com/hc/en-us/articles/227730088-Exporting-a-UTF-8-txt-file-from-Word)

[^1]: [https://en.wikipedia.org/wiki/UTF-8](https://en.wikipedia.org/wiki/UTF-8): "UTF-8 is a variable-length character encoding standard used for electronic communication."  It defines how characters are actually written to disk, essentially.