# Why is my dictionary not working?

Some dictionaries cannot be used as "inline" or embedded dictionaries.

For example, the Collins online dictionary at [https://www.collinsdictionary.com/](https://www.collinsdictionary.com/) will show the following if it is configured as a language dictionary with `https://www.collinsdictionary.com/dictionary/english/###`:

<img width="903" alt="image" src="https://github.com/jzohrab/lute-manual/assets/1637133/e7488a9f-c4ea-4ecc-b124-adcebe504cce">

In these cases, you must prepend the url with "*", e.g.:

```
*https://www.collinsdictionary.com/dictionary/english/###
```

With this, the dictionary will be shown as a popup.