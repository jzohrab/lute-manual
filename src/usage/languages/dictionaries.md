# Dictionaries

## Term lookups

"Dictionary 1" and "Dictionary 2" are used for term lookup.

When you have the "Term" form open in the right-hand pane while reading, if you click the small arrow icon next to the term, either Dictionary 1 or 2 will be shown in a frame.  Click the arrow repeatedly to cycle through the dictionary.

The dictionary link entry on the form must contain "###".  Lute substitutes that with the actual term you're looking up.

### Specify a dictionary to open as a pop-up

To open a dictionary as a pop-up, add the "*" to the start of the dictionary.  For example, `*https://www.collinsdictionary.com/dictionary/english/###`.

Note: this is **required** for some dictionaries, as they can't be embedded in other websites.  For example, the Collins dictionary will show a "www.collinsdictionary.com refused to connect" error with a grey screen if the "*" is omitted (`https://www.collinsdictionary.com/dictionary/english/###`):

<img width="75%" alt="image" src="https://github.com/jzohrab/lute-manual/assets/1637133/e7488a9f-c4ea-4ecc-b124-adcebe504cce">


## Image lookups

To use a Bing image lookup, you can put the following into either Dictionary 1 or Dictionary 2:

```
https://www.bing.com/images/search?q=###&form=HDRSC2&first=1&tsc=ImageHoverTitle
```

_(I admit I'm not 100% sure on how to specify French only images, or German-only images, but just using a standard string above appears to work for the languages I've tried!)_

Note that the Term form (the right-hand frame when reading) has an "eye" icon next to the term ... you can click on that and it does a common bing image search (disregarding your custom image search url you might have saved with the language).

## Sentence lookups

You could use either DeepL or Google translate for sentence lookups.

## External dictionary lookups

Some sites, like DeepL and Google Translate, don't work when embedded within sites.  These sites have to be viewed in separate pop-up windows, outside of Lute itself.

To mark a URL as "external", precede it by an asterisk, e.g.:

```
*https://www.deepl.com/translator#es/en/###
```