# Custom styles

Lute doesn't have "theming" support yet, but you _can_ modify the styles in the Settings menu.

Open Settings, and in the "Custom styles" text box in the settings, enter valid CSS.  For example, this:

```
span.textitem { font-size: 16px; }
span.status1 { background-color: pink; }               /* status2-5 for the rest */
span.status98 { background-color: lightgrey; }         /* Ignored terms */
span.status99 { background-color: none; color: red; }  /* Well-known terms */
```

yields this:

<img width="194" alt="image" src="https://github.com/jzohrab/lute/assets/1637133/8b088df2-35fd-486c-8694-8bd580afe974">

## Styling examples for your inspiration

fyi the CSS selectors for the statuses are `span.status1` through `span.status5`, with `.status98` for ignored and `.status99` for well-known.

### Larger reading font

```
span.textitem { font-size: 16px; }
```

### Change colors

```
 span.status0  { background-color: #ADD8E6; }  /* Unknown. */
 span.status1  { background-color: red; }
 span.status2  { background-color: red; }
 span.status3  { background-color: orange; }
 span.status4  { background-color: orange; }
 span.status5  { background-color: green; }
 span.status98 { background-color: white; }    /* Ignored. */
 span.status99 { background-color: white; }    /* Well known. */
```

### Language-specific styles

You might want different colors or font sizes for different languages.  You can get the language ID by clicking on it in the language listing (Settings > Languages), it's at the end of the URL; e.g., `http://localhost:5000/language/edit/9`, "9" is the ID.

```
span.status0[lid="8"] { background-color: red; }
span.status0[lid="4"] { background-color: blue; }
```

### Remove all term highlights, only show on hover

```
 span[class*="status"] { background-color: transparent; }
 
 span.status0 { background-color: #D5FFFF; }
 span.status1:hover { background-color: #F5B8A9; }
 span.status2:hover { background-color: #F5B8A9; }
 span.status3:hover { background-color: #F5E1A9; }
 span.status4:hover { background-color: #F5E1A9; }
 span.status5:hover { background-color: #DDFFDD; }
 span.status98:hover { background-color: #DDFFDD; }
 span.status99:hover { background-color: #DDFFDD; }
```

### Hide the green checkmarks at the bottom of the reading pane

Clicking the green checks sets unknown to well-known, which you might not like.


```
#footerMarkRestAsKnown { display: none; }
#footerMarkRestAsKnownNextPage { display: none; }
```

### Why would you ever do this?

```
body { font-family: "Comic Sans MS"; }
```

Yuck.

## Notes:

* The styles used by Lute out-of-the-box are in [the GitHub repo](https://github.com/jzohrab/lute-v3/blob/master/lute/static/css/styles.css), hack away!
* The data you put in the text box must be valid CSS, as it is picked up verbatim and inserted into the HTML.
* Some of the current css class names are bad (e.g. "status98" means "ignored", but that's pretty hard to follow).  If those class names get changed in a future release, I'll add a note in the release notes.
* Using css is pretty tricky, but it works for now!
