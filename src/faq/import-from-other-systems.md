# Can I import data from other systems?

You can import data into Lute via [bulk term import](../usage/terms/bulk-term-import.html), you just have to get your data into .csv file format.

## Importing data from LWT

LWT has an "export" feature:

![image](https://github.com/jzohrab/lute-manual/assets/1637133/46153912-f6af-4857-bfce-2ec47b51d262)

Use "Export ALL Terms (TSV)" to export a tab-separated value file.  The file may get downloaded as a ".txt" file, in which case, rename it to ".tsv".

A sample row of data exported from LWT looks like this:

```
gato	cat	Tengo un {gato}		1	Spanish	20
```

You can then import that file into something like [Google Sheets](https://docs.google.com/spreadsheets/u/0/), and prepare it for import.

As the [bulk term import](../usage/terms/bulk-term-import.html) page says:

* The first line of the CSV file must have the field headings: language, term
* The first line of the CSV file may also have any of these headings: translation, parent, status, tags, pronunciation

Add a blank line, and then place Lute headings in the appropriate columns.  Continuing with the above example, the data becomes:

| term | translation | n/a | n/a | status | language | n/a | tags |
| --- | --- | --- | --- | --- | --- | --- | --- |
| gato | cat | Tengo un {gato} |  | 1 | Spanish | 20 | |


Removing the unmapped columns (with "n/a" in the heading) gives:

| term | translation | status | language | tags |
| --- | --- | --- | --- | --- |
| gato | cat | 1 | Spanish | |

Export this to a .csv file, and import it into Lute.