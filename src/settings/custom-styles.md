# Custom styles

Lute doesn't have "theming" support yet, but you _can_ modify the styles in the Settings menu.

Open Settings, and in the "Custom styles" text box in the settings, enter valid CSS.

Below are some examples:

```
/* Change reading text font. */
span.textitem { font-size: 16px; }

/* Change background color etc for statuses: */
span.status1 { background-color: pink; }   /* status2-5 for the rest */

/* Ignored is 98 */
span.status98 { background-color: lightgrey; }

/* Well-known is 99 */
span.status99 { background-color: none; color: red; }
```

With those rather ugly styles, some text might look like this:

<img width="194" alt="image" src="https://github.com/jzohrab/lute/assets/1637133/8b088df2-35fd-486c-8694-8bd580afe974">

It's also possible to get a bit more fancy with CSS.  For example, you might want to _remove_ all background colors, except when you hover over a term:

```
 span[class*="status"] { background-color: transparent; }
 span.status0 { background-color: #D5FFFF; }
 span.status1:hover { background-color: #F5B8A9; }
 span.status2:hover { background-color: #F5B8A9; }
 span.status3:hover { background-color: #F5E1A9; }
 span.status4:hover { background-color: #F5E1A9; }
 span.status5:hover { background-color: #DDFFDD; }
```

Or, you know:

```
body { font-family: "Comic Sans MS"; }
```

Yuck.

## Notes:

* The styles used by Lute out-of-the-box are in [the GitHub repo](https://github.com/jzohrab/lute-v3/blob/master/lute/static/css/styles.css), hack away!
* The data you put in the text box must be valid CSS, as it is picked up verbatim and inserted into the HTML.
* Some of the current css class names are bad (e.g. "status98" means "ignored", but that's pretty hard to follow).  If those class names get changed in a future release, I'll add a note in the release notes.
* Using css is pretty tricky, but it works for now!
