# 🐝 Ferg's Solar Bees

An "under construction" website for **Mike Ferguson's** backyard apiary in New Haven, MO — raw, local honey.

Built as a single, self-contained `index.html` (no build step, no dependencies). A honey/bee theme with a solar-sunrise hero, in keeping with the *Solar Bees* name.

## Editing

Everything you'd want to change lives in one `SITE` config block near the top of `index.html`:

```js
const SITE = {
  beekeeperName: "Mike Ferguson",
  apiaryName:    "Ferg's Solar Bees",
  tagline:       "...",
  town:          "New Haven, MO",
  email:         "beekprnh@gmail.com",
  phone:         "",          // leave "" to hide the phone row
  venmoHandle:   "@BeekeeperNH", // leave "" to hide the Venmo row
  launchNote:    "...",
  honeyForSale:  [ { size: "½ lb jar", price: "$7" }, ... ], // one entry per size
  honeyDescription: "...",
  saleNotes:     [ "line 1", "line 2" ], // "Get in touch" in a note links to the contact card
  story:         [ "paragraph 1", "paragraph 2" ], // one string per paragraph
};
```

To change prices, edit the `price` values in `honeyForSale`.

## Photos

Published photos live in `images/`, shrunk to web size (a few hundred KB each)
with all metadata stripped:

| File | Used for |
|---|---|
| `hive-yard.jpg` | Meet the Herd — wide banner (2:1) |
| `swarm.jpg`, `capped-frame.jpg` | Meet the Herd — square tiles |
| `jars.jpg` | Honey for Sale card |
| `share-preview.jpg` | Link-preview image (1200×630) when the site is texted or posted |

Full-size originals go in `photos/`, which is git-ignored. **Don't commit phone
photos straight from the camera**: they're several MB each and usually carry GPS
coordinates of where they were taken. Resize and strip metadata first
(re-saving with Pillow without `exif=` does both).

The link-preview text (`og:` tags in the `<head>`) is written out by hand
rather than read from `SITE`, because Facebook, iMessage and similar sites
don't run the page's JavaScript. If the name or tagline changes, update both.

The only other files are the site icons — `favicon.svg` (used by modern browsers
and as the Apple touch icon) and `favicon.ico` (the legacy fallback). Both are
referenced from the `<link>` tags in the `<head>`.

## Viewing locally

Just open the file in a browser:

```bash
open index.html
```

## Deploying (GitHub Pages)

The site is one static file, so GitHub Pages serves it directly from `master`:

1. Push to GitHub.
2. Repo **Settings → Pages → Build and deployment**: Source = *Deploy from a branch*, Branch = `master` / `/ (root)`.
3. Live at **<https://fergssolarbees.com>** (GitHub also serves it at
   `https://eric-d-ferguson.github.io/ferg-solar-bees/`).

The custom domain is configured by the `CNAME` file in the repo root — it is not
just documentation. Deleting or renaming it drops `fergssolarbees.com` on the
next deploy, so leave it in place.

Because Pages deploys from `master`, **pushing to `master` publishes the site.**
For anything you want to review first, work on a branch and merge when it looks
right.
