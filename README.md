# Modifying this website

This is a Jekyll website built with Ruby. The site uses Liquid templates, Markdown pages/posts, and HTML partials.

## Folder purpose

### `_includes/`
Reusable partial templates that are inserted into layouts and pages.

Common examples in this repo:
- `header.html`: top navigation + site title
- `head-custom.html`: custom tags in `<head>` (favicons, manifest, etc.)

Use this folder when you want to change shared UI sections that appear across multiple pages.

### `_layouts/`
Page wrappers that define the overall structure of a page (head, header, main content, footer).  
Pages and posts select a layout via front matter (for example `layout: page` or `layout: post`).

Use this folder when you want to change global page structure instead of a small reusable fragment.

## Where to modify CSS styling

Primary custom stylesheet for this site:
- `assets/main.scss`

This file imports Minima first and then overrides it:

```scss
@import "minima";
```

So, for most visual changes (fonts, spacing, nav styles, colors), edit `assets/main.scss`.

Also note:
- `_includes/head-custom.html` is for extra `<head>` tags, not main CSS rules.
- `_config.yml` stores site config values (title, url, baseurl, etc.), not CSS styling.