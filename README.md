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
  story:         [ "paragraph 1", "paragraph 2" ], // one string per paragraph
};
```

To add photos to the **Meet the Herd** section, replace the `📷` tiles in the
`.herd` grid with `<img>` tags.

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
