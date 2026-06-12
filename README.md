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
  launchNote:    "...",
  story:         [ "paragraph 1", "paragraph 2" ], // one string per paragraph
};
```

To add photos to the **Meet the Herd** section, replace the `📷` tiles in the
`.herd` grid with `<img>` tags.

## Viewing locally

Just open the file in a browser:

```bash
open index.html
```

## Deploying (GitHub Pages)

The site is one static file, so GitHub Pages serves it directly from `main`:

1. Push to GitHub.
2. Repo **Settings → Pages → Build and deployment**: Source = *Deploy from a branch*, Branch = `main` / `/ (root)`.
3. Live at `https://eric-d-ferguson.github.io/ferg-solar-bees/` (a custom domain can be added later without code changes).
