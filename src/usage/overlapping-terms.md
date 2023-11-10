# Overlapping terms

Sometimes Terms you define may "overlap", so Lute displays those with an extra indicator.

For example, suppose you're studying Spanish, and you have already defined two Terms: "tengo un gato", and "un gato bueno y gordo" (with different Statuses, one is new, the other is easy).  If you were reading a book with text "Tengo un gato bueno y gordo.", Lute displays that like this:

<img width="293" alt="image" src="https://github.com/jzohrab/lute/assets/1637133/b6fa96c4-5c28-4f9f-a86a-ef84e651aa39">

The small "+" sign next to the "bueno y gordo" indicates that the full Term "un gato bueno y gordo" is _partially overlapped by the preceding term.

If you hover over the "+ bueno y gordo", you'll see the full term:

<img width="313" alt="image" src="https://github.com/jzohrab/lute/assets/1637133/d91e1330-1be6-4191-ad2a-8333d2760a44">

and clicking on it will open the Term form with the full term as well:

<img width="592" alt="image" src="https://github.com/jzohrab/lute/assets/1637133/14307108-3493-4128-ac77-87e1d9ef4f47">

If you don't like the "+" sign as the overlap indicator, you can customize it using a custom style:

```
/* content in data/custom_styles/custom_styles.css */
span.overlapped:before {
   content: "\00BA";
   color: green;
}
```

which gives this:

<img width="300" alt="image" src="https://github.com/jzohrab/lute/assets/1637133/9d3f3063-067c-45c2-a255-811df28c780c">