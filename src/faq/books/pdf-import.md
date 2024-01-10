# Why won't my pdf import correctly?

Lute uses the [PyPDF2](https://pypi.org/project/PyPDF2/) library for PDF imports.

PDF imports sometimes add extra unwanted spaces: for example, the word "happiness" in your PDF may be imported as "happi ness".  For this reason, when you import your PDF, Lute will give you a warning that it may be inaccurate.

This issue is not a problem with Lute, or even with the PyPDF2 library ... correctly parsing PDFs is actually _extremely_ tough.  Per the authors of PyPDF2:

> Getting whitespaces right is notoriously hard. @pubpub-zz is the expert in that topic; I'll leave it to him to decide if we should leave this issue open. The issue is that PDF does not (necessarily) represent the words as words internally. In the worst case, it just gives the absolute position of each character in the document.

References:

* [StackOverflow - pypdf extra spaces](https://stackoverflow.com/questions/76546531/why-does-pypdf-stuff-text-with-extra-spaces-when-extracting-text)
* [Random whitespaces are inserted when using page.extract_text()](https://github.com/py-pdf/pypdf/issues/1507)

In summary, the best that we can do is say that PDF imports are not perfect, and you should be aware of that while reading.  You can edit each page as you come across problems, or just ignore the incorrect words.