# assets

Images and other media for the blog posts and works on two sites:

- **Studio**: sujeetk.com
- **Personal**: portfolio.sujeetk.com

The sites don't host these files. A post or work points at them by URL, served from this public repo through the jsDelivr CDN.

## Layout

```
studio/
  blog/<post-slug>/     cover and inline images for a studio blog post
  works/<work-slug>/    images for a studio work
personal/
  blog/<post-slug>/     the same, for the personal site
  works/<work-slug>/
```

The folder name matches the post's or work's `slug` on the site.

## Using a file on a site

Link a file by its URL:

```
https://cdn.jsdelivr.net/gh/Sujeet76/assets@main/<path>
```

For example, `studio/blog/my-post/cover.webp` is at
`https://cdn.jsdelivr.net/gh/Sujeet76/assets@main/studio/blog/my-post/cover.webp`.

Where that URL goes:

| Content | Field |
| --- | --- |
| Blog post cover | `coverImage` |
| Image inside a post | Markdown `![alt](url)` in `body` |
| Work images | `images` (the first one is the cover; up to 6) |

A file only works on the site after it has been pushed to `main`.

## Rules for files

- **Never replace a file in place.** jsDelivr caches files from `@main` for up to 7 days, so an overwritten image can keep showing the old version. To change an image, add it under a new name (`cover-v2.webp`) and update the link.
- Prefer `.webp`. Keep images under about 300 KB and no wider than 2000 px.
- Use lowercase file names with hyphens: `hero-diagram.webp`, not `Hero Diagram.PNG`.
- Every file in this repo is public. Don't commit anything private.

## Who uses this

The sites' owner, and a private workspace that writes the posts and works and links to these files through the sites' admin API. Nothing from that workspace belongs here: only the media files and this README.
