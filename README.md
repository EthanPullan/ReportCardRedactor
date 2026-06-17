# Report Card Redactor

A single-page, **fully offline** tool for stripping student names, ID numbers,
and other identifying details out of exported HTML report cards. All processing
happens in your browser — the file you load never leaves your device, nothing is
uploaded, and nothing is stored.

**Live app:** https://ethanpullan.github.io/ReportCardRedactor/

## What it does

- **Load** a report card by drag-and-drop, file picker, or pasted HTML.
- **Build a redaction list** — type terms, import a `.txt`/`.csv`, or highlight
  text directly in the preview to add it.
- **Auto-suggest teacher names** written in `Last, First` format.
- **Blank fixed-length numbers** (for example, 9-digit student IDs).
- **Choose the replacement** style: `[REDACTED]`, `[NAME]`, `[STUDENT]`, a solid
  black bar, stars, or your own custom text.
- **Preview** original vs. redacted, then **download** or **copy** a clean copy.

## Privacy

Everything runs locally in JavaScript — you can disconnect from the internet and
the app still works. The document preview is rendered with scripts stripped out
and inside a sandboxed `<iframe>`, so loaded report cards can't run code.

## Development

The whole app is one self-contained file, [`index.html`](index.html) — no build
step and no dependencies. Open it directly in a browser to run it locally.

## Deployment

The site is published to GitHub Pages by
[`.github/workflows/deploy-pages.yml`](.github/workflows/deploy-pages.yml) on
every push to `main`.

**One-time setup:** in the repository's **Settings → Pages → Build and
deployment**, set **Source** to **GitHub Actions**. GitHub does not allow the
workflow's token to enable Pages on its own, so this switch has to be flipped
once by a repo admin. After that, every push to `main` redeploys automatically.
