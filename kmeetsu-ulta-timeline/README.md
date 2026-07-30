# K-Beauty Week presented by KMEETSU — Annual Integrated Program

Interactive proposal dashboard for the Ulta Beauty × Goodai Global USA partnership, covering **October 2026 – December 2027**.

> **Internal — meeting use.** Unreleased proposal, partner-specific asks and mockup creative. Keep the repository private and treat the published URL as unlisted. See [Hosting](#hosting).

---

## What this is

A single self-contained HTML page. No build step, no dependencies, no server-side code — open `index.html` and it runs.

| Section | Contents |
|---|---|
| **Cover** | Ulta Beauty × KMEETSU lockup, the four annual moments |
| **01 · Program at a Glance** | All 24 initiatives × 3 intensities, with Ulta / Goodai ownership markers |
| **02 · Annual Operating Timeline** | 15-month grid on Ulta fiscal weeks — tentpoles, the four moments, an activity ribbon, and six lanes with an always-on flow bar. Collapsed to 6 lanes by default, expandable to all 24 |
| **03 · Inside a K-Beauty Week** | Visual board of every initiative with its creative, and the specific ask of Ulta under each card. Four intensity tabs |
| **04 · What We Are Asking Ulta For** *(folded)* | The 15 consolidated asks split by budget / slot / resource, each with a decision date |
| **Appendix** *(folded)* | How the two light moments differ — offline May vs online Oct/Nov |

**Interactions:** hover a timeline node for the creative · click a lane circle for that lane's brief · click a moment banner for the full week brief · toggle density and Ulta-only filtering.

---

## Repository structure

```
.
├── index.html                  the entire dashboard — markup, styles, data and logic
├── .nojekyll                   tells GitHub Pages to serve files as-is
├── images/
│   ├── KMEETSU_Logo.png        brand wordmark (cover)
│   ├── UB_Logo_Orange_NoBkgd.png
│   └── timeline/
│       └── IMG-01.jpg … IMG-26.jpg
└── docs/
    └── IMAGE-BRIEF.md          spec for every image asset
```

---

## Hosting

**Locally** — open `index.html` in any modern browser. No build step, no server. This is all that is needed to present it.

**GitHub Pages** — Settings → Pages → Source: *Deploy from a branch* → `main` / `/ (root)`. Live at `https://<org>.github.io/<repo>/` in a minute or two. `.nojekyll` keeps the asset paths intact.

One thing worth knowing: **a private repository does not produce a private site.** Unless the organisation is on GitHub Enterprise Cloud, a Pages site published from a private repo is reachable by anyone who has the URL — the source stays private, the page does not. For a meeting link that is usually fine, and this repo already ships `noindex` plus a `robots.txt` so it stays out of search results. Just treat the URL as unlisted rather than secret.

If access control is genuinely required, the options are Enterprise Cloud private Pages (viewers need repo read access), a password-protected host such as Netlify, or skipping hosting altogether — print to PDF at A3 landscape, the print stylesheet is included.

---

## Editing the content

Everything lives in the `<script>` block at the bottom of `index.html`. There is no data file to sync.

| To change… | Edit |
|---|---|
| An initiative, its copy or its image | `const TRACKS` — one object per initiative, with `e1`–`e4` for the four moments |
| The ask attached to an initiative | `const REQ` — keyed by initiative name |
| Always-on wording | `const REG` |
| Image specs and file mapping | `const IMG` and `const HAVE` |
| Moment dates, names and briefs | `const EV` and `const BRIEF` |
| Ulta's own tentpole calendar | `const TENT` |
| The consolidated ask list | `const ASKS` |

**Adding an image:** drop `IMG-NN.jpg` into `images/timeline/`, add `NN` to the `HAVE` set, and add an entry to `IMG`. Portrait frames must also be listed in `TALL` so they are letterboxed rather than cropped.

**Image conventions:** longest edge 1200px, JPEG quality 80, progressive. Keep the originals elsewhere; this folder holds the web-optimised copies only (~4 MB total).

---

## Data provenance

Read this before quoting anything from the dashboard.

**Sourced.** The 24 initiatives, their three intensity levels and the Ulta / Goodai ownership markers come from the *KMU IMC Plan — Program at a Glance*. Fiscal weeks and month placement are calculated from the Ulta FY2026 grid (FW36 = week of 4 Oct 2026; FY2027 FW1 = week of 31 Jan 2027).

**Goodai Global USA's recommendation, not agreed with Ulta.** The moment dates, the shopper-journey narrative, the timing rationale, the decision deadlines and the wording of each ask. Ulta's FY2027 tentpole calendar is projected from the FY2026 pattern and is marked *to confirm* in the interface.

**Deliberately excluded.** All budget figures. The dashboard argues structure and commitment, not cost.

---

## Notes on the creative

- Every image is a **mockup**. Nothing here has been produced, approved or published by Ulta Beauty.
- The Ulta logo appears in a partnership working context, not under a licence for public distribution.
- Brand names in the mockups (TIRTIR, ma:nyo, numbuz:n, MEDIHEAL, medicube, Anua, COSRX, fwee, VT, Beauty of Joseon and others) belong to their owners.
- Do not make the repository public without sign-off from the Ulta partnership lead.

---

## Status

Draft v1 · prepared for Ulta Beauty leadership review
Goodai Global USA Inc. — KMEETSU Integrated Retail Program
