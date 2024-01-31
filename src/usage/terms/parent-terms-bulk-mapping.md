# Bulk mapping parent terms

(NOTE: the UI and implementation has changed since this was written, but the idea is still the same.  TODO: update this section!)

Lute supports [Parent Terms](./parent-terms.md), and also supports a bulk mapping of Parent Terms to Terms, using a mapping file that you create and import.

**Why would you want this?**  In my experience reading extensively with Lute, I am usually familiar with words, but it is _very_ nice having the previously-entered information for their Parent Terms.  As I read, I often find myself interrupting myself to just map terms to parent terms.  Of course, this mapping is completely optional, and sometimes I don't do it ... but having this automatically taken care of is pretty nice.

On the Home page, the link "Parent Term mapping" takes you to a page with links to export a file that you can use to create your mapping file, and to import this mapping file.  You may want to run through this process for every large new text or book that you import, so that you can focus on the **really new stuff** in that text.

## What mapping does

When the file is imported, Terms and Parents are created and associated as needed, depending on the Terms currently in your Lute database.  For example, given a mapping file:

```
dog    dogs
```

We have the following scenarios:

| Child term "dogs" exists? | Scenario | Result |
| --- | --- | --- |
| Yes | If "dogs" doesn't have a Parent Term, and "dog" exists | "dog" is assigned as the Parent Term for "dogs" |
| Yes | If "dogs" doesn't have a Parent Term, and "dog" doesn't exist | "dog" is _automatically created_, and assigned as the Parent Term for "dogs" |
| Yes | If "dogs" already has a Parent Term | nothing happens |
| No | If "dog" exists | "dogs" is _automatically created_, and "dog" is assigned as its Parent Term |
| No | If "dog" does not exist | nothing happens |

If a term is automatically created, you'll see a small asterisk next to it when reading, and a small message will be included in its popup:

![image](https://user-images.githubusercontent.com/1637133/236732831-94fc2209-4821-4580-8344-cb8615ac4586.png)

![image](https://user-images.githubusercontent.com/1637133/236732902-3feed1cf-6f18-4463-9882-7142388a23c0.png)

That message and asterisk will disappear when you click on the term and either click "Save" or refresh the page.  (The action of viewing the form seems to me like the easiest way of "acknowledging" the automatically created term).

## The import mapping file

A mapping file is a list of records, of format `parent-term <TAB> term`.  A sample import file for English would look like this:

```
cat      cats
cat      kitten
dog      dogs
```

## Generating an import file

When you click on one of the "export" links from the "Parent Term mapping" page, a file is generated for you (e.g. `/data/parents/terms_3.txt`).  You can pull this into a spreadsheet and fill in the parent in a new column.

Optionally, if you have Python 3.11 installed, and your language is one of the 60+ languages supported by the Stanford Stanza library (see https://stanfordnlp.github.io/stanza/available_models.html), you can use [LuteLemma](https://github.com/jzohrab/LuteLemma) to convert this exported file to a mapping file.

## Exporting "books" vs "language"

The "map Parent Terms" page has two kinds of exports:

* "book": export unknown terms in a book.
* "language": only exports known terms without parents.

My current usage recommendation is to only export new "books" to try to map unknown words to existing Terms that you've defined while reading prior books.  This clears up some terms during your reading and hopefully makes reading more productive.

Full "language" exports, for setting up relationships in existing words, is useful, but it could also be a low-value-yield activity.  It's interesting, but I don't know if it will help you read more better faster.  Perhaps try exporting and see if there are any interesting word parent assignments that you really want.

Use these exported files to create your import file.

## Why isn't this automatically built in to Lute?

Great question.  The process of mapping terms to a root form is non-trivial, and the current implementation in Lute is not seamless (though it works!).  The current implementation was driven by the following technical considerations:

When coming up with the current process and implementation, I considered the following technical issues:

- **performance** - Lemmatization is a potentially tricky operation, requiring either a lot of space or a lot of time.  My current thought is that keeping it out of Lute ensures that Lute is responsive during regular use, and that you can choose when you want to run this expensive operation.
- **availability** - lemmatization tools available appear to depend on the language (I'm not completely sure about this).  I can't reliably code for what I don't understand. :-)
- **complexity** - Mapping words to their parents is easy, but not trivial, if you get me.

Beyond tech, there were a few other things I had in mind:

- **philosophy** - Lute is as much for learning as it is for reading.  I believe that taking the time to look up words, find the best definition, and write it down, is part of the process of learning.  I'm not _certain_, but sometimes it feels like _not_ having everything be automatic is useful.
- **necessity**: mapping to root terms is perhaps only needed once you reach a certain level in reading.

Of course, everything is in flux, and as I use this feature more myself, I may change my approach.
