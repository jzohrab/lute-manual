# Beta releases

When you do a `pip install` or `--upgrade`, pip will automatically use the latest stable release.

If you're feeling daring, you can also install Lute beta releases.  As Lute's developer/owner, I use the beta releases in my personal prod environment, actually using it to ensure there aren't any problems.  When the beta is good, it's made into a stable release.

Beta releases end with `b<number>`, and are betas for the _next_ planned release.  This follows [the Python recommendation](https://packaging.python.org/en/latest/specifications/version-specifiers/#version-specifiers).

For example, if the current prod release is `3.0.4`, the next planned release will be `3.0.5`.  Betas before that release will be `3.0.5.b1`, `.b2`, etc, so the numbering will be:

```
3.0.4
3.0.5b1
3.0.5
```

To install a beta release, you have to fully specify the version number, e.g.

```
pip install lute3==3.0.5.b1
```

Beta releases are not released to Docker Hub.