# Blog template

A [Quarto](https://quarto.org) blog for research notes: a log for a single
project, or one place for all of your work. The example posts in `posts/` show
the most useful features; the group handbook covers the rest.

## Published or local?

Depending on how sensitive the work is, choose one of two setups:

- **Published:** the repository is public and GitHub Pages publishes the blog
  as a website that anyone can read.
- **Local:** the repository is private, or not on GitHub at all, and the blog
  is only viewed with `pixi run preview`. This works fine for showing the blog
  at a group meeting.

A site published by GitHub Pages is public even when the repository is
private, so use the local setup for anything that should not be public.

## Getting started

1. Click **Use this template** on GitHub to make your own copy (public or
   private, see above), and clone it.
2. *Published:* in the new repository, go to **Settings → Pages** and set
   **Source** to **GitHub Actions**. Every push to `main` then publishes the
   blog.

   *Local:* delete `.github/workflows/publish.yml`. Otherwise GitHub tries to
   publish the blog on every push, and the run fails.
3. In `_quarto.yml`, change `title`, `site-url` and the GitHub link to point
   to your blog. For a local blog, `site-url` can be left as it is.
4. Run `pixi run preview` to open a live preview that updates when you save.

## Writing a post

Each post is a folder in `posts/` with an `index.qmd` file in it, e.g.

```
posts/2026-11-20-phonon-results/index.qmd
```

Starting the folder name with the date keeps the posts in order. Put
everything the post uses (data, images, a `references.bib` file) in the same
folder. The file starts with a front matter block:

```yaml
---
title: "Phonon results"
description: "One sentence shown in the list of posts."
author: "Your Name"
date: 2026-11-20
categories: [phonons]
draft: true  # remove this line to publish the post
---
```

Write the post below it in Markdown. The example post *Writing a post* shows
what you can do. If a post runs Python code, commit its folder in `_freeze/`
along with it (see the example post *Python in a post*).

## Starting from a bare blog

Once you have read the example posts, delete them along with their stored
results:

```bash
rm -r posts/2026-11-01-writing-a-post posts/2026-11-05-python-figures posts/2026-11-10-interactive-charts
rm -r _freeze/posts/2026-11-05-python-figures _freeze/posts/2026-11-10-interactive-charts
```

Then rewrite `about.qmd` to describe your blog.
