# Neeko ✿

A cute personal site for reviews and thoughts on books, games, movies, shows, anime and music. It runs free on GitHub Pages, with nothing to install.

## Put it online (one time, ~5 minutes)

1. Sign in to GitHub and click **+ → New repository**.
2. Name it **`neeko`**. Make it **Public**. Click **Create repository**.
3. On the new repo page, click **uploading an existing file**. Drag in **everything inside this folder** (the files and folders, not the folder itself). Click **Commit changes**.
4. Go to **Settings → Pages**. Under *Build and deployment*, set Source to **Deploy from a branch**, branch **main**, folder **/ (root)**, and save.
5. Wait a minute or two, then visit **https://yourusername.github.io/neeko**. The default password is **`changeme`**.


## Make it yours

Open `_config.yml` on GitHub (click it, then the ✏️ pencil) and change `title`, `greeting`, `tagline` and `author`. Edit `about.md` for the About page. Colours live at the top of `assets/style.css`.

## Change (or turn off) the password

1. On your computer, double-click `tools/make-password.html`. It opens in your browser.
2. Type your new password and click **Copy code**.
3. In `_config.yml`, replace the long code after `password_hash:` with yours (keep the quotes). Commit.

Everyone, including you, will need the new password the next time they visit. To turn the lock off, delete the `password_hash:` line. The 🔒 button at the bottom of every page locks the site again on that device.

**Important:** this lock keeps casual visitors out, but it is not real security. On a free GitHub account the repository has to be public, so anyone who finds `github.com/yourusername/neeko` can read your reviews there. Someone who knows web code can also get past the password screen. Don't put anything truly secret on the site.

## Add a review

1. Open the `_reviews` folder and click **Add file → Create new file**.
2. Name it something like `the-last-of-us.md`.
3. Paste in the contents of `REVIEW_TEMPLATE.md`, fill in the top section, and write your review underneath.
4. Click **Commit changes**. The site updates in about a minute.

The top section (between the `---` lines) controls how it's shown:

| Field | What it does |
|---|---|
| `title` | Name of the thing |
| `type` | `book`, `game`, `movie`, `show`, `anime` or `music` |
| `creator` | Author, studio, director, artist… |
| `year` | Release year |
| `date` | When you wrote the review (sets the order on the front page) |
| `rating` | 0–5, halves allowed (`3.5`). Delete the line for no stars |
| `verdict` | One-liner shown on the card |
| `tags` | Optional, e.g. `[horror, rewatch]` |
| `status` | Optional, e.g. `reading`, `playing`, `watching`. Puts it on the "Currently into" shelf. Delete it when you're done |
| `cover` | Optional picture for the card and the top of the review |
| `gallery` | Optional list of pictures shown at the bottom (screenshots, photos…) |

No cover? The card gets a cute coloured tile with an emoji instead.

## Adding pictures

1. Open the `assets/images` folder on GitHub. Click **Add file → Upload files**, drag your pictures in, and commit.
   *Tip: use simple names with no spaces, like `dune-cover.jpg`. Keep pictures under ~1 MB so the site stays fast.*
2. Use them in a review:

**As the cover:**
```
cover: /assets/images/dune-cover.jpg
```

**As a gallery at the bottom:**
```
gallery:
  - image: /assets/images/dune-1.jpg
    caption: "my favourite scene"
  - /assets/images/dune-2.jpg
```

**In the middle of your writing** (the italic line right under it becomes a caption):
```
![describe the picture](/assets/images/dune-1.jpg)
*a little caption*
```

Visitors can click any picture to see it bigger. Thoughts posts and the About page can have a `cover:` too, which shows as a banner.

## Add a "thought" (blog post)

Create a file in `_posts` named **`YEAR-MONTH-DAY-some-title.md`** (e.g. `2026-12-31-my-year-in-games.md`) starting with:

```
---
title: "My year in games"
tags: [roundup]
---

Write here…
```

## Long reviews

Add `subtitle: "..."` to the top section for a second title line. To add a clickable contents list, paste this where you want it:

```
<details class="toc" markdown="1">
<summary>Contents</summary>

* TOC
{:toc}

</details>
```

## Add a new media type

Add an entry under `media_types` in `_config.yml` (e.g. `id: podcast`, `label: Podcasts`, `emoji: "🎙️"`). To give it its own colour, add a `--podcast` colour at the top of `assets/style.css` and copy the `-book` rules (`.chip-book`, `.tile-book`, `.pill-book`, `.review-book`) for it.
