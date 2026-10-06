# Spindle website handoff

Public product page only. Windows and mobile source stay in their private repos. This file is the site handoff. Do not add application source here.

**Live:** https://jon1969edwards.github.io/spindle/  
**Repo:** https://github.com/Jon1969Edwards/spindle (`main`, GitHub Pages, legacy, path `/`)  
**Local:** `F:\Dev\spindle`

## What is live

A one-page product site plus a privacy page.

| File | Role |
|------|------|
| `index.html` | Header, hero, three Windows feature blocks, Android phone section, Free vs Pro, download band, footer |
| `privacy.html` | Public privacy policy. Same header and footer. |
| `styles.css` | Layout and color |
| `version.json` | Update manifest the Windows app fetches |
| `.nojekyll` | Pages serves files as-is |

Copy on the page: Discogs collection sorted for real shelves, TXT/CSV/JSON export, Android companion with shelf / scan / wishlist on the same Pro key, Free up to 100 records, Pro **$24** once. Discogs disclaimer is in the hero and the footer. Support is `jon1969edwards@gmail.com`.

Checkout is not open. The Pro card says so. Windows and Android downloads are “Coming soon” placeholders (not linked to empty GitHub Releases). Flip them back to real release URLs when the first builds ship. There is no Play Store listing yet.

## Who depends on this site

- Windows update check reads `UPDATE_MANIFEST_URL` in `discogs-vinyl-sorter-windows/core/version.py`: `https://jon1969edwards.github.io/spindle/version.json`
- `version.json` shape: `version`, `download_url`, `release_notes`. `download_url` is the public Releases page above.
- Mobile `WINDOWS_DOWNLOAD_URL` in `src/constants/version.ts` points at that same Releases URL. Buy Pro stays hidden while checkout equals that URL.
- Discogs commercial email and Windows support docs point here, not at the private repos.

When a signed `Spindle-Setup-1.0.0.exe` exists, upload it as a Release on **this** public repo. Then copy `release/version.json` from the Windows repo onto `version.json` here if the notes or download URL changed. Pushing `main` publishes the site. Pages can take a minute. Hard-refresh to bypass cache.

## Current look

Dark navy page matching the Windows app (`#0a0e1a`, purple `#6c63ff`, gold labels `#c9943a`). The header uses `assets/logo-mark.png` (navy field, red record grooves). The hero is the Windows cabinet screenshot beside the phone Kallax cabinet (`assets/phone-cabinet.png`). Screenshots open a larger view on click. The feature blocks use the collection list, the export filenames, and the album detail with real marketplace prices.

The `#phone` section sits between the Windows features and pricing. It shows three tall phone frames (`assets/phone-cabinet.png`, `assets/phone-scan.png`, `assets/phone-wishlist.png`) on the phone ground `#1a1a2e` with gold captions. Android download is in the hero and the download band, same public Releases URL as Windows.

## Next change

Play Store listing link when the Android build ships. Custom domain can point at this Pages site later.
