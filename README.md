# Swipe Dash website

Static public site with the pages the stores ask for, hosted on GitHub Pages. Every page carries its own styles and
icon, so a page works even when uploaded on its own; only `index.html` also needs `assets/` (`hero.jpg` and `shots/`).
GitHub Pages serves `terms.html` at `/terms` as well.

| Page | URL | Used for |
| --- | --- | --- |
| `index.html` | `/` | Landing page. Play Console *Website*, App Store *Marketing URL* |
| `privacy-policy.html` | `/privacy-policy` | Privacy policy: Play Console, App Store Connect, Microsoft Store; link from the game |
| `terms.html` | `/terms` | Terms of Service / EULA: Play Console *Terms of Service*, App Store Connect *License Agreement* (custom EULA; includes Apple's required terms) |
| `support.html` | `/support` | Support URL (required by App Store Connect), FAQ and contact |
| `delete-account.html` | `/delete-account` | Account deletion URL (required by Play Console for apps with accounts) |
| `credits.html` | `/credits` | Third-party art, font and service credits |
| `404.html` | any missing path | Not-found page |
| `app-ads.txt` | `/app-ads.txt` | AdMob seller verification; must be at the root of the domain set as *Website* in both stores |

## Details used

NADESOFT · contact@nadesoft.bd · Nowhata Bazar, Paba, Rajshahi, Bangladesh · Terms governed by the law of Bangladesh.
Microsoft Store: https://apps.microsoft.com/detail/9p6rdr6mfp29

When the App Store listing exists, add a "Download on the App Store" button next to the Google Play one in
`index.html`, plus `<meta name="apple-itunes-app" content="app-id=<numeric id>">` in its head.

## Deploy (GitHub Pages)

Copy everything in this folder except this README into the Pages repo, keeping `assets/` next to `index.html`.
`app-ads.txt` only works at the root of a domain (`https://yourdomain/app-ads.txt` or `https://<user>.github.io/`),
not under a project path like `https://<user>.github.io/<repo>/`; set that domain as *Website* in both stores.
Change the effective date at the top of `privacy-policy.html` or `terms.html` whenever their content changes.
