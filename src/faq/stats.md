# The stats calculation

In your Book listing, Lute shows the word count for each book, and an estimated percent known for the book.

For example, in my book "Breve Historia del Mundo", Lute shows "92461 (90%)" for the text.  If I hover over the percentage, it says "235 unknowns in next 2445 unique terms":

<img width="288" alt="image" src="https://github.com/jzohrab/lute/assets/1637133/d95b54a4-cfc5-49b5-a792-911a3f9a5864">

To do the calculation, Lute samples the next ~10,000 words or characters in the Book, and determines what words or characters are completely unknown (brand new) to you, taking into account all of your defined single-word and multi-word Terms.

## Example

Suppose you're studying Chinese, a character-based language, and are reading the text "這是東西".  If you you define "東西" (the last two characters of the text) as a Term, Lute will say that you now know 33% of the text:

* "這" is unknown
* "是" is unknown
* "東西" is considered "known", regardless of its status (1-5 etc)

## Can't Lute calculate the percent using the whole text?

Yes, but it's too slow for long texts.

Since multi-term words can overlap or hide other terms, Lute needs to work through the full display of each text.  For longer novels (e.g. 200K+ words), the full calculation is far too slow to be usable.

I've considered various simplifications to the calculation, such as ignoring multi-word Terms.  This makes the checks faster, but wildly inaccurate, and so not useful in some cases.

As a compromise, I figured that a large sample like this would be good enough.  When considering a book, I just check a few pages to see if it's way above my level, I don't need to flip through every page.  So that's the approach that Lute takes, and it seems sensible.