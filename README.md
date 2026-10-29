# UFFG Construction — website

Static site. No builds, no plugins, no monthly cost. Open `index.html` in a browser to preview it locally.

Pages: Home · Services · Projects · About · Request a Quote (+ thank-you and 404)

---

## 1. Fill in the placeholders

Every placeholder shows up on the site with a **yellow highlight** so you can't miss it. Open each file in Notepad (or any text editor) and use Find & Replace.

| Find this | Replace with | Files |
|---|---|---|
| `(713) 000-0000` | real phone | all `.html` |
| `tel:+17130000000` | `tel:+1` + the 10 digits, no spaces | all `.html` |
| `info@uffgconstruction.com` | real email | all `.html` |
| `uffgconstruction.com` | real domain (once you have one) | `contact.html`, `sitemap.xml`, `robots.txt` |
| `Mon&ndash;Fri, 7am&ndash;5pm` | real hours | `contact.html` |

Two numbers on the home page stat bar also need real values — in `index.html`, search for `XX` and `XXX`:

- `XX+ Years building in Houston`
- `XXX Structures completed`

If you'd rather not claim a number, delete those two `<div class="stat">…</div>` blocks and the bar will show the remaining two centered.

**Last step:** once everything is filled in, delete the yellow highlight styling so the site looks finished. In `assets/css/site.css`, find the `.placeholder` block and change it to:

```css
.placeholder{background:none;border:0;color:inherit;padding:0;font-weight:inherit}
```

---

## 2. Make the quote form actually send

The form uses **FormSubmit** — free, no account, no limits worth worrying about.

1. Replace `info@uffgconstruction.com` in `contact.html` with the real email (step 1 above covers this).
2. Publish the site (step 3).
3. Go to the live site and submit the form **once** yourself.
4. FormSubmit emails that address a confirmation link. Click it.

That's it — every submission after that lands in the inbox. Until step 4 is done, nothing sends.

---

## 3. Publish free on GitHub Pages

No command line needed.

1. Make a free account at **github.com**.
2. Click **+** (top right) → **New repository**.
   - Name it `uffg-site`
   - Set it to **Public**
   - Click **Create repository**
3. On the next screen click **uploading an existing file**.
4. Open the `uffg-site` folder on your computer, select **everything inside it** (not the folder itself) and drag it into the browser window. Wait for all files to finish uploading.
   - If `.nojekyll` doesn't come along in the drag, upload it separately — it matters.
5. Click **Commit changes**.
6. Go to **Settings** → **Pages** (left sidebar).
   - Source: **Deploy from a branch**
   - Branch: **main** / folder: **/ (root)** → **Save**
7. Wait 1–2 minutes, refresh. The live address appears at the top:
   `https://YOUR-USERNAME.github.io/uffg-site/`

To update later: in the repo, click **Add file → Upload files**, drag the changed files in, commit. Live in about a minute.

### Custom domain (optional, ~$12/year for the domain only)

Buy the domain anywhere (Cloudflare and Namecheap are cheapest). Then in **Settings → Pages → Custom domain**, type it and save. GitHub shows you exactly which DNS records to add at the registrar. Hosting stays free; HTTPS turns on automatically — just tick **Enforce HTTPS** once it's available.

---

## 4. What's in here

```
index.html        Home
services.html     Services
projects.html     Projects gallery (click any photo to enlarge)
about.html        About / the UFFG name
contact.html      Quote request form
thank-you.html    Shown after the form submits
404.html          Shown for a bad link
assets/css/       One stylesheet
assets/js/        Mobile menu + photo lightbox
assets/img/       25 jobsite photos, web-optimized (full size + thumbnail)
assets/logo/      UFFG lockup and stamp, SVG, in green / cream / white / ink
sitemap.xml       For Google
robots.txt        For Google
.nojekyll         Tells GitHub Pages to serve the files as-is — don't delete
```

### Swapping a photo

Drop the new image into `assets/img/`, then edit the matching `<img src="...">` line. Keep images under ~400 KB and around 1600 px wide so pages stay fast.

---

## Brand reference

| | |
|---|---|
| Green | `#2E6B4F` |
| Warm neutral | `#EFEBE3` |
| Ink | `#15181C` |
| White | `#FFFFFF` |

Headlines are Source Serif 4, body is Inter (both loaded free from Google Fonts). The UFFG wordmark itself is vector artwork, not type — it will never substitute to a wrong font.

Navy `#1E2F45` is in the brand system but is deliberately **not used** on this site.
