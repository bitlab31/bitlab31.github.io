# bitlab31.github.io

Personal "about me" page of Martin Dimitrov, served at <https://lab31.eu> via GitHub Pages.

## What this is

A fork of `gh-aboutme`, a customizable GitHub "About Me" page. The repository contains only the **compiled Angular build**, not the Angular source. Changes are made directly to the built files.

The page shows a profile card: avatar, name, nickname, bio, location, company and social icon links (email, LinkedIn, GitHub).

## How content is configured

Content is controlled by `config.js`, which is loaded at runtime:

- `githubUsername` - profile used to fetch data from the public GitHub API (`api.github.com`) in the visitor's browser.
- `name`, `nickname`, `bio`, `avatarUrl`, `location`, `company` - `null`/`true` uses the GitHub value, `false` hides the field, a string overrides it.
- `socialIcons` - list of icons (`EMAIL`, `LINKEDIN`, `GITHUB`, ...), each with optional `text` and `link`.

Editing `config.js` and pushing to the default branch is enough to update the site.

## Files

| File | Purpose |
|---|---|
| `index.html` | Entry point, loads the bundles |
| `config.js` | Site content (see above) |
| `main.*.bundle.js`, `vendor.*.bundle.js`, `inline.*.bundle.js` | Compiled Angular app, including component styles |
| `styles.*.bundle.css` | Global styles (body font, base sizes, tooltip) and Font Awesome 4.7 |
| `fontawesome-webfont.*` | Font Awesome icon fonts |
| `roboto-latin.woff2` | Self-hosted Roboto (variable, weights 100-900, latin subset); no third-party font requests |
| `CNAME` | Custom domain (`lab31.eu`) |

## Typography

Sizes use `rem`, so they follow the browser's font-size setting: name 1.75rem (28px), body/nickname/bio 1.125rem (18px), location/company and tooltip 0.875rem (14px). Font stack: Roboto (self-hosted), then system fonts.

## Deployment

Pushing to the default branch publishes the site through GitHub Pages. Changes can take a few minutes to appear because of caching; hard-refresh if needed.

## Local preview

```sh
python3 -m http.server 8000
```

Open <http://localhost:8000>. The page still fetches profile data from `api.github.com`, so it needs internet access.

## Licenses

Font Awesome 4.7: SIL OFL 1.1 (fonts), MIT (CSS). Roboto: Apache 2.0.
