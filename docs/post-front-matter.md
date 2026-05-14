# Post Front Matter Guide

Use this as the standard header for every file in `_posts/`.

```yaml
---
layout: post
title: "Readable Post Title"
date: YYYY-MM-DD
category: "Research"
tags: ["Tag One", "Tag Two"]
description: "One sentence summary used by blog cards and SEO."
cover_image: /images/category/image-name.jpg
location: "Optional location"
---
```

## Required Fields

- `layout`: Always use `post`.
- `title`: The public title shown on the card and article page.
- `date`: Match the filename date unless there is a reason not to.
- `category`: Use one stable category name.
- `tags`: Use an array of short tags.
- `description`: Write a concise summary. Prefer this over `excerpt` for card text.
- `cover_image`: Use an absolute site path beginning with `/images/`.

## Current Categories

- `Research`
- `Language Learning`
- `J-POP`

## Style Notes

- Prefer `description` instead of `excerpt`; `excerpt` can still be kept for legacy posts.
- Keep `cover_image` paths consistent, for example `/images/DataAssimilation/DA.png`.
- Use English commas and spaces in tag arrays: `["GEOS-Chem", "Model"]`.
- Add `location` only when the place matters to the post.
