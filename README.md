# johnwright.ai

Static site for **johnwright.ai**, hosted on GitHub Pages.

## How URLs work (clean, no `.html`, trailing slash)

GitHub Pages serves a folder's `index.html` when you visit the folder. So the URL
is just the folder path with a trailing slash — no `.html` ever appears.

| File in repo                         | Live URL                              |
| ------------------------------------ | ------------------------------------- |
| `index.html`                         | `https://johnwright.ai/`              |
| `blog/index.html`                    | `https://johnwright.ai/blog/`         |
| `blog/my-first-post/index.html`      | `https://johnwright.ai/blog/my-first-post/` |

Pages also auto-redirects `…/my-first-post` → `…/my-first-post/`.

## Adding a blog post

1. Create a folder: `blog/<post-slug>/` (use lowercase-with-hyphens for the slug —
   that becomes the URL: `johnwright.ai/blog/<post-slug>/`).
2. Inside it, create `index.html`. Start from the template below.
3. Add a link to it at the top of the `<ul class="posts">` list in `blog/index.html`,
   and remove the `<p class="empty">…</p>` line once there's a real post.
4. Commit and push — it's live within a minute or two.

### Post template (`blog/<post-slug>/index.html`)

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="utf-8">
  <meta name="viewport" content="width=device-width, initial-scale=1">
  <title>POST TITLE — John Wright</title>
  <meta name="description" content="ONE-LINE SUMMARY">
  <link rel="canonical" href="https://johnwright.ai/blog/POST-SLUG/">
  <style>
    * { margin:0; padding:0; box-sizing:border-box; }
    body { background:#fbfbfa; color:#1a1a1a; line-height:1.7;
      font-family:-apple-system,BlinkMacSystemFont,"Segoe UI",Roboto,Helvetica,Arial,sans-serif; }
    .wrap { max-width:680px; margin:0 auto; padding:64px 24px 96px; }
    a.back { color:#777; text-decoration:none; font-size:15px; }
    h1 { font-size:34px; letter-spacing:-0.02em; margin:32px 0 8px; }
    .meta { color:#999; font-size:14px; margin-bottom:40px; }
    article p { margin:0 0 20px; font-size:18px; }
    article h2 { font-size:24px; margin:40px 0 12px; }
    article a { color:#1a1a1a; }
  </style>
</head>
<body>
  <div class="wrap">
    <a class="back" href="/blog/">← Blog</a>
    <h1>POST TITLE</h1>
    <p class="meta">Month DD, YYYY</p>
    <article>
      <p>Write your post here.</p>
    </article>
  </div>
</body>
</html>
```

## The homepage

`index.html` is the exported Wix homepage (a self-contained bundle that renders
the original design client-side). Replace it any time with a hand-built page.

## Files

- `CNAME` — custom domain (`johnwright.ai`). Don't delete; GitHub Pages needs it.
- `.nojekyll` — tells Pages to serve files verbatim (no Jekyll build step).
- `404.html` — shown for unknown URLs.
