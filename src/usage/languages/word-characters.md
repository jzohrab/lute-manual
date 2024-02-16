# Word characters

The "Word characters" field in the language form tells Lute how to find words in your texts.  In most cases[^other_cases], Lute uses "regular expressions", or pattern matchers, to find words in a text.

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

## Unicode word characters

Many languages use non-Latin characters.  These are stored as unicode[^what_is_unicode].  For example, here's Sanskrit:

```
a-zA-Z\u0900-\u0963\u0966-\u097F
```

The entries `\u0900`, `\u0963`, etc are all python equivalents for the actual Unicode character points `U+0900`, `U+0963`, etc.

The `\u` indicator (called an "escape sequence") expects exactly four hexadecimal digits following it.  If your unicode character has 5 digits (e.g. `U+1F438`), `\u` won't work: you'd need to prepad the digits with 0, and have 8 digits.

* `U+0963`: `\u0963` is valid.
* `U+1F438`: `\u1F438` is *not* valid, `\U0001F438` works.

For example, for Cuneiform, the character range is:

```
\U00012000-\U000123FF\U00012400-\U0001247F\U00012480-\U0001254F
```

Which breaks down to: `U+12000` to `U+123FF` inclusive, plus `U+12400` to `U1247F` inclusive, plus `U+12480` to `U+1254F` inclusive.

---

[^other_cases]: Japanese uses MeCab for parsing.

[^what_is_unicode]: From [Wikipedia](https://en.wikipedia.org/wiki/Unicode): "Unicode ... is a text encoding standard maintained by the Unicode Consortium designed to support the use of text written in all of the world's major writing systems."