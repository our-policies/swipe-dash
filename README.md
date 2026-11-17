# Swipe Dash website

Static public site with the pages the stores ask for. Firebase Hosting serves it (`firebase.json` → `hosting`)
with clean URLs, so `terms.html` is served at `/terms`. This README is not deployed.

| Page | URL | Used for |
| --- | --- | --- |
| `index.html` | `/` | Landing page. Play Console *Website*, App Store *Marketing URL* |
| `privacy.html` | `/privacy` | Privacy policy: Play Console, App Store Connect, Microsoft Store; link from the game |
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

## Deploy

```sh
firebase emulators:start --only hosting   # preview at http://localhost:5000
firebase deploy --only hosting
```

Firebase gives `https://<project-id>.web.app` with SSL; a custom domain can be added in the Firebase console.
After a custom domain is live, update the *Website* field in both stores so AdMob finds `app-ads.txt`.
Change the effective date at the top of `privacy.html` or `terms.html` whenever their content changes.
