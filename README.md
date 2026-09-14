# vélgreind.magnusmh.is

Dispatches on Magnús M. Halldórsson's AI-related work at Reykjavik University.
A Jekyll site built by GitHub Pages from `main`; nothing to install locally.

## Files

| | |
|---|---|
| `_posts/YYYY-MM-DD-slug.md` | one dispatch each; front matter `title`, `date`, `topic` |
| `_data/topics.yml` | the five fixed topics; keys are the `topic:` values and the `/efni/<key>/` paths |
| `efni/<key>.md` | one index page per topic (four lines each) |
| `um.md` | the About page |
| `_layouts/` | `default` (masthead + footer), `post`, `topic` |
| `assets/style.css` | the same palette and type as magnusmh.is |
| `CNAME` | the hostname, as punycode. **Do not delete** — removing it drops the domain on the next build |

The Atom feed at `/feed.xml` is produced by `jekyll-feed`, which GitHub Pages allows.

## Adding a dispatch

Write it as markdown with this header, drop it in `_posts/`, push:

```yaml
---
title: A town-hall meeting on AI and university education
date: 2026-08-07
topic: town-hall      # one of the keys in _data/topics.yml
---
```

The first paragraph is the excerpt shown on the front page, so make it stand alone.

## Hostname

`vélgreind.magnusmh.is` is an internationalized domain name; on the wire it is
`xn--vlgreind-b1a.magnusmh.is`, and that is what `CNAME` and the Pages custom
domain hold. Browsers convert for you. Apple's `curl` does not, so from the terminal:

```sh
curl -sSI https://xn--vlgreind-b1a.magnusmh.is | head -3
```

DNS is one CNAME record in the Cloudflare zone for `magnusmh.is`
(`vélgreind` → `magnusmhalldorsson.github.io`, DNS only). Certificate issuance did
not start on its own after the record went in; clearing and re-setting the
custom domain through the Pages API triggered it.
