# Bulk term import

If you have existing vocabulary lists, you can bulk import new Terms into Lute with a properly-formatted CSV file.  This is only for importing new Terms into Lute, existing Terms are not changed.

# CSV File Format

* The CSV file should be properly formatted; i.e., carriage returns in fields are allowed, but the field should be enclosed in quotes.
* The first line of the CSV file **must** have the field headings: `language, term`
* The first line of the CSV file may also have any of these headings: `translation, parent, status, tags, pronunciation`
* Fields can be in any order.
* An error is raised if the file contains other headings.

## Field notes

| Field | Required | Notes |
| --- | --- | --- |
| language | Yes | Must be the name of one of the languages you have saved in Lute |
| term | Yes | The new Term |
| translation | | |
| parent | | The "parent" of this term (e.g., an infinitive form of a verb, etc.).  This will automatically create the parent term if it doesn't exist already, or if it's not created in the same import file. |
| status | | One of 1, 2, 3, 4, 5, W (for Well-Known), or I (for Ignored).  If missing, it's set to 1 |
| tags | | A comma-delimited list of tags to add to the Term |
| pronunciation | | |

## Examples

### ex. 1 - single record

The simplest example.  Note that the tags `animal, noun` must be enclosed in quotes.

```
language, term, translation, parent, status, tags, pronunciation
Spanish,gato,cat,,W,"animal, noun",GA-toh
```

### ex. 2 - carriage return in field

```
language,term,translation,parent,status,tags,pronunciation
Spanish,gato,"A cat.
A house cat.",,1,"animal, noun",GA-toh
```

This would create a term "gato" with the translation "A cat (carriage return) A house cat".

### ex. 3 - parent record

```
language,term,translation,parent,status,tags,pronunciation
Spanish,gatos,cat,gato,W,,
```

This would create the term "gatos" (status = Well Known), and also the term "gato", setting "gato" as the parent for "gatos" (the plural form).

Parent records may be useful, for example, if you're learning conjugations of irregular verbs.

### ex. 4 - translation only

```
language,term,translation
Spanish,gato,cat
```

# Creating CSV files

The easiest way to create properly-formatted CSV files is probably through something like Google Sheets.  Create a sheet with the correct headings.  You can enter carriage returns into a given cell using something like Shift-Return, or Ctrl-Return ... depending on your system.  Then export that as a CSV using File > Download > Comma Separated Values.

Using Google Sheets, you might also be able to get some _basic_ translations.  For example, if I have "colima" in cell B2, the formula `=GOOGLETRANSLATE(B2,"es", "en")` in cell B3 would give "hill".