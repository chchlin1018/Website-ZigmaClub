# Website-ZigmaClub

Public marketing + trial-request site for **ZXBuilder** — a bidirectional OpenUSD ↔ Autodesk Revit
plugin for semiconductor fabs and industrial digital twins.

> **Naming**: `ZXBuilder` is the external product name; `Zigma` remains the internal codename.
> Repository names, branches and release filenames are deliberately **not** renamed.

## Live

- Site: <https://www.zigma.club>
- Hosting: GitHub Pages (CNAME → `www.zigma.club`)
- Latest release: see [releases](https://github.com/chchlin1018/Website-ZigmaClub/releases)

## Relationship to zxbuilder.club

`zigma.club` and `zxbuilder.club` run **in parallel** (both live, no redirect between them).
Release assets are served from a single source — **this repository's releases** — so the download /
update-check chain used by existing installations stays unchanged.

| Site | Owner | Publish path |
|---|---|---|
| `zigma.club` | plugin mesh | `tools\ship-zigmaclub.ps1` (automated) |
| `zxbuilder.club` | RM Office | manual commit + push to `Website-ZXBuilder` |

## Structure

- `index.html` — single-page site (HTML + inline CSS + inline JS · ~58 KB · **4-language i18n**:
  EN / 繁體中文 / 日本語 / 한국어)
- `version.json` — version + download endpoints consumed by the in-product update check
- `sitemap.xml` — single-URL sitemap (root only)
- `robots.txt` — allow all crawlers
- `CNAME` — `www.zigma.club`
- `img/` — `rmai-lockup.png`, `zxbuilder-lockup.png`, `step1-ribbon.jpg`, `step2-about.jpg`
- `public/downloads/` — legacy archives (v5.5.x); not linked from the current page
- `.github/workflows/pages.yml` — Pages deployment

## Code signing

From **v5.7.8.5** onward the released MSI is digitally signed with an **EV code-signing
certificate** issued to *Reality Matrix AI Inc.* Windows shows Reality Matrix AI Inc. as the
verified publisher.

Consequences for this site — already applied:

- The "MSI is not yet code-signed / SmartScreen Unknown Publisher" banner is **removed** in all four
  languages and replaced with the signed-publisher notice.
- The **Diagnostic Toolkit** download is **removed** — it existed to troubleshoot install failures
  caused by the unsigned installer.
- The **ZIP alternative is kept**, but re-framed: it is for users whose *corporate IT policy* blocks
  `.msi` downloads, not for working around Microsoft/SmartScreen.

⚠️ The `README.txt` install guide shipped as a **release asset** is produced by the plugin build, not
by this repository. It still contains SmartScreen instructions and must be regenerated on the plugin
side for v5.7.8.5.

## Pre-Beta

Trial users access via the **Download Trial** button which links to the latest GitHub Release MSI on
this repository. Trial license keys are issued individually by **Reality Matrix AI Inc.** after a form
submission with the user's Machine Code (NDA-bound).

## Contact

- Sales: `sales@realitymatrixai.com`
- Support: `support@realitymatrixai.com`
- Pre-Beta access: `michael.lin@realitymatrixai.com`

© 2026 Reality Matrix AI Inc. (實矩科技股份有限公司). All rights reserved.
