# Student Counselling Docket: Play Store package

Developed by Dr. H. S. Khalsa. This folder is the standalone, installable version of the app.

## What is in this folder

| File | What it is |
| --- | --- |
| `index.html` | The whole app: both dockets and both career tests. Works offline after the first visit. |
| `manifest.webmanifest` | App name, colours and icons, so phones can install it as an app. |
| `sw.js` | Offline support. Change `VERSION` (for example to `scd-v2`) every time you upload new files. |
| `icons/` | App icons (192 and 512 pixels, plus a "maskable" one for Android's round and square icon shapes). |
| `privacy-policy.html` | The privacy policy Google Play asks for. **Replace `[your contact email]` before uploading.** |
| `store/` | Play Store graphics: the 1024 x 500 feature graphic and four 1080 x 1920 phone screenshots. |
| `store-listing.txt` | Ready-to-paste app name, short description and full description. |

The 512-pixel icon in `icons/` is also the "App icon" Google Play asks for in the store listing.

## Step 1. Put the folder on a free website

**GitHub Pages**
1. Create a free account at github.com and a new public repository, for example `counselling-docket`.
2. Upload every file and folder from this folder (keep the same names and structure).
3. In the repository, open Settings > Pages, choose "Deploy from a branch", branch `main`, folder `/ (root)`, and save.
4. After a minute the app is live at `https://YOUR-NAME.github.io/counselling-docket/`. Open it on your phone to check.

Netlify works too: sign in at netlify.com and drag this whole folder onto the "Deploy manually" area.

## Step 2. Make the Android package

1. Open pwabuilder.com, paste your website address and press Start.
2. Choose Package for Stores > Android > Generate. Use a package ID such as `com.hskhalsa.counsellingdocket` (it can never be changed later).
3. Download the zip. It contains the `.aab` file for Google Play, a signing key, and a file called `assetlinks.json`.
4. Keep the signing key and its passwords somewhere safe. You need them for every future update.
5. Upload `assetlinks.json` to your website inside a folder named `.well-known` (so it opens at `https://YOUR-SITE/.well-known/assetlinks.json`). This removes the browser address bar from the installed app. On GitHub Pages, also add an empty file named `.nojekyll` at the top level so the `.well-known` folder is published.

## Step 3. Publish on Google Play

1. Create a developer account at play.google.com/console (one-time registration fee; identity check required).
2. Create the app, then fill in the store listing from `store-listing.txt` and the graphics in `store/` and `icons/`.
3. Privacy policy: use the address of `privacy-policy.html` on your website.
4. Data safety: the app collects and shares no data.
5. Target audience: 13 and above (Class 10 and Class 12 students, with parents and counsellors).
6. Upload the `.aab` to a closed test and invite at least 12 testers who stay opted in for 14 days in a row. After that, apply for production access.

## Updating the app later

Upload changed files to the same website and change `VERSION` in `sw.js`. Installed apps pick up the new content the next time they open with internet. You only need a new Play Store upload if the app name, icon or package changes.
