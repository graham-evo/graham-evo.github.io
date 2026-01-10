---
title: Adding a favicon to your GitHub Jekyll Site 
layout: page
permalink: /coding_tutorials/favicon/
nav_exclude: true
---

If you’ve ever wondered why your GitHub Pages site still shows a blank tab icon, you’re not alone. Favicons are simple in principle, but GitHub Pages, Jekyll, and browser caching (especially Safari) can make them feel mysterious.

Here’s the clean, reliable way to add one when using Jekyll with the **Minima** theme.

---

## What is a favicon?
A favicon is the small icon shown in browser tabs, bookmarks, and history lists. Browsers only recognize favicons if they are **linked inside the HTML `<head>`** of a page.

This detail matters.

---

## Step 1: Create a favicon
Create a file named:

```

favicon.ico

```

You can generate this from any image using tools like:
- https://favicon.io  
- https://realfavicongenerator.net  

---

## Step 2: Put it in the repository root
Place `favicon.ico` at the **top level** of your GitHub Pages repository:

```

favicon.ico
_includes/
_layouts/
_config.yml

```

You should be able to visit:

```

[https://yourusername.github.io/favicon.ico](https://yourusername.github.io/favicon.ico)

```

If that URL works, GitHub Pages is serving the file correctly.

---

## Step 3: Add the favicon to the page `<head>`
If you’re using the **Minima** theme, the correct place to add favicon links is *not* `header.html`.

Instead, create this file:

```

_includes/head-custom.html

````

Add the following line:

```html
<link rel="icon" href="{{ '/favicon.ico' | relative_url }}">
````

Minima automatically injects `head-custom.html` into the page `<head>` during site generation. No layout edits required.

---

## A common mistake

It’s tempting to put favicon links in:

```
_includes/header.html
```

But this file controls the **visual page header**, not the HTML `<head>`. Browsers ignore favicon links placed there.

---

## Step 4: Clear your browser cache

Favicons are aggressively cached. If your icon doesn’t appear immediately:

* Hard reload the page (**Cmd + Shift + R**)
* Open the site in a private/incognito window
* Fully quit and restart the browser

Safari, in particular, is very stubborn.

---

## How to confirm everything worked

Open your browser’s developer tools and inspect the `<head>` element. You should see:

```html
<link rel="icon" href="/favicon.ico">
```

If the file loads directly but the icon still doesn’t change, the issue is almost always browser caching—not Jekyll.

---

## The minimal working setup

This is all you actually need:

```
favicon.ico
_includes/head-custom.html
```

With this single line in `head-custom.html`:

```html
<link rel="icon" href="{{ '/favicon.ico' | relative_url }}">
```

---

## Final thoughts

Once the favicon file is served and linked in `<head>`, your site is correctly configured. Any remaining weirdness is usually your browser remembering an old icon.

In other words: if `/favicon.ico` loads and the `<link rel="icon">` tag exists, you’re done.

Happy theming.

```

---

If you want, I can:
- Make this **even shorter** (micro-post style)
- Add **screenshots** of Safari DevTools
- Rewrite it for a **“lessons learned”** or troubleshooting tone
- Adapt it for **non-Minima** themes

Just say how you want to present it.
```
