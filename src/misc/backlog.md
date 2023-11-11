# Backlog

Below are features that would be nice to have.  Some of these are already listed in Lute's [GitHub issues](https://github.com/jzohrab/lute-v3/issues).  These are not listed in any particular order.

> The issue IDs shown aren't correct, as the issues were transferred from the original lute repo to lute-v3; however, the links should still work.

# Feature backlog

## Improved language support

- Support non-consecutive multi-word terms - [issue 58](https://github.com/jzohrab/lute/issues/58)
- Change how dictionaries are defined and used - [issue 39](https://github.com/jzohrab/lute/issues/39)
  - Add Kobo dictionary support - [issue 41](https://github.com/jzohrab/lute/issues/41)
  - Integrate Golden dict app with Lute - [issue 5](https://github.com/jzohrab/lute/issues/5)

## Reading experience

- change book reading so that page content is ajaxed in, instead of moving to new URL.  This allows for audio player support.
- Add navigate to arbitrary page in book -- -- e.g. when on page 600 and want to go back to page 21.  maybe enter in a text box, dropdown, or vertical/horizontal slider.
- Hotkey status update should update the form if it's displayed - [issue 45](https://github.com/jzohrab/lute/issues/45)
- add "chapters" markings somehow to books, so I can build a table of contents, and see when a chapter ends
- add "force page break" markers to text imports, e.g. "---" forces a break.
- add book text search
- arrow up and down to increase/decrease status number
- add "Autopopulate" button for the parent term. In most languages, the parent is pretty visibly related to the child, but with a few letter changes. It´d be nice not to have to copy the whole word from below, but just press a button and then type the end of the word.

## Audio

- Add Audio controls to play text mp3.  This requires page content to be ajaxed in, not URL-per-page.
- Add word pronunciation.  Audio files could be stored in user's `data` folder, and files could be found by md5 of term, e.g.

## Backup

- if backup is automatic, when the backup completes, auto-redirect to home page
- show the file created and its size on the backup page

## Misc features

- Add improved export to Anki - [issue 24](https://github.com/jzohrab/lute/issues/24)
- Possibly ignore word accents when saving terms in DB - [issue 17](https://github.com/jzohrab/lute/issues/17)
- add bulk term delete
- Add stats
  - words read today/cumulative
  - terms created today/cumulative
  - statuses by date/cumulative
  - click on link to see filtered list in terms page - need more complex filtering
- editing text/sentence doesn't change the book WordCount.  setWordCount is called when book is first created, on setFullText.  If text is edited, should first save the old count, then update the book count


# Dev/code backlog

Code maintenance/improvements.  Doing these help deliver features or a better experience.

## misc

  - Increase acceptance test coverage (master list) - [issue 35](https://github.com/jzohrab/lute/issues/35)
  - Drop extra fields from texts table (sourceuri, mediauri, lgid, isarchived).  Started in branch hack_remove_texts_fields
  - save SeTextLC in sentences, use SeTextLC when looking up references
  - change statuses - null/0 unknown, 1-5, 6 = wellknown; 7 = ignored (currently 98 = ignored, good enough? or -1?)
  - RenderableSentence.php: public static function getParagraphs should not parse, move parsing to the facade
  - findTermsInText should use zws to join things, not null string.  Add tests for "Tengo un gato" - "Tengo un" "tengo un gato", "tengo un gat", "un gato", "un gat"
  - remove languages.islgremovespaces field
  - change book "is archived" cycle? - active -> completed -> archived
  - try not saving and retrieving entities, see if orm can get them
