# CLAUDE.md

## Duplicated files: index.html and 404.html

`index.html` and `404.html` are kept byte-for-byte identical. `404.html` exists
so that ad traffic landing on `/quote` still renders the full page (including
the quote funnel) even when the host serves it as a 404 fallback instead of
routing `/quote` to `index.html`.

**Any change made to one of these files must be made identically to the
other.** Before committing, diff them to confirm they still match:

```
diff index.html 404.html
```

If they diverge, the `/quote` landing page (ad traffic) and the root site
will show different content/behavior.
