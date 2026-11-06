# Bulk URL Shortener

A static web app you can host on **GitHub Pages** for bulk URL shortening.

Paste ~1000 URLs → get back a list of short links like:

```
https://<your-username>.github.io/Ab3xY9
```

When someone visits that short link, GitHub Pages serves `404.html`, which looks up the code in `shortcodes.json` and redirects to the original long URL.

## Files

| File | Purpose |
|---|---|
| `index.html` | The bulk shortener app (paste URLs, get short links, copy/download) |
| `404.html` | Redirect handler for short links (`/<CODE>`) |
| `shortcodes.json` | Mapping of short code → original long URL (e.g. `{ "Ab3xY9": "https://example.com/very/long-url" }`) |

## Deploy to GitHub Pages

1. Create a new repository named `<your-username>.github.io` (for a user/organization site), or use any existing repo and enable GitHub Pages.
2. Place `index.html`, `404.html`, and `shortcodes.json` in the **root** of the repo.
3. Push to the `main` branch.
4. Go to **Settings → Pages** and set Source to **Deploy from a branch → main / (root)**.
5. Wait a minute and visit `https://<your-username>.github.io`.

## Usage

1. Open your new GitHub Pages site.
2. Paste up to ~1000 URLs into the textarea (one per line, or comma/space separated).
3. Click **⚡ Shorten URLs**.
4. Copy individual short links, copy all, or download `shortcodes.json`.
5. **Commit the downloaded `shortcodes.json`** to the root of your repo so redirects resolve for everyone.

## Short link format

```
https://<your-username>.github.io/<CODE>
```

Codes are 6-character mixed-case alphanumeric (base58-ish alphabet, excludes ambiguous characters like `0/O`, `1/I/l`).
