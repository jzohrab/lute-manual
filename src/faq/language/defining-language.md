# How can I figure out my language's "word characters"?

In most cases[^other_cases], Lute uses "regular expressions", or pattern matchers, to find words in a text.

The default value, "a-zA-ZÀ-ÖØ-öø-ȳáéíóúÁÉÍÓÚñÑ", covers most romance languages such as English, French, Spanish, etc.

For other languages, like Russian (word characters = "А-Яа-яЁё"), you have to find the characters.  This can be tricky, so here are some thoughts:

* search Google for "<your language> character python regex".  E.g. "russian character python regex" gives a few hits.
* search "<your language> unicode range"
* if you've _already_ searched and can't figure it out, that's what Discord is for!

## Understanding the "Word characters" field

The word characters can contain individual characters or a range of characters.  For example, the following are equivalent:

```
abcdef
```

```
a-f
```

As you can see, the default value `a-zA-ZÀ-ÖØ-öø-ȳáéíóúÁÉÍÓÚñÑ` contains all lowercase a through z, all uppercase A through Z, and whatever the heck those other character ranges are ... plus some extra accented characters.

---

[^other_cases]: Japanese uses MeCab for parsing.