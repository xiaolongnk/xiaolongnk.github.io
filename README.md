# xiaolongnk.github.io

The product site: https://xiaolongnk.github.io — static HTML, no build step, served by GitHub Pages from `main`.

```
index.html               home: every product, one card each
agent-fleet/index.html   the "one person, one fleet" write-up (EN)
zh/agent-fleet/          same, Chinese
assets/style.css         the one stylesheet (house style: IBM Plex Sans + JetBrains Mono, light)
assets/*.gif|png         media referenced by the pages
```

## Adding a page

1. Copy `agent-fleet/index.html` to `<slug>/index.html`, keep the `<nav>` and the stylesheet link
   (`href="../assets/style.css"`, one more `../` per directory level).
2. Put media in `assets/` and reference it relatively — never base64-embed (keeps the repo small).
3. Link it from `index.html`. Push to `main`; Pages rebuilds in about a minute.

Social posts link to the GitHub repo for the product (that's what people want to inspect) and to a
page here for the longer story.
