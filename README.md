# gatekeep-legal

Static pages for Gatekeep's Privacy Policy and Terms of Service.

## Deploy to GitHub Pages (5 minutes)

```bash
cd ~/gatekeep-legal
git init
git add .
git commit -m "Initial legal pages"
gh repo create gatekeep-legal --public --source=. --remote=origin --push
```

Then enable Pages:

```bash
gh api -X POST /repos/thegalateacompany-hash/gatekeep-legal/pages -f 'source[branch]=main' -f 'source[path]=/' -f 'build_type=legacy'
```

(Or via the web UI: github.com/thegalateacompany-hash/gatekeep-legal → Settings → Pages → Source = Deploy from a branch → Branch = main, root → Save.)

Wait ~1 minute for the first build. Your URLs will be:

- Index: `https://thegalateacompany-hash.github.io/gatekeep-legal/`
- Privacy: `https://thegalateacompany-hash.github.io/gatekeep-legal/privacy.html`
- Terms: `https://thegalateacompany-hash.github.io/gatekeep-legal/terms.html`

## Use in App Store Connect

- **Privacy Policy URL**: `https://thegalateacompany-hash.github.io/gatekeep-legal/privacy.html`
- **Terms of Use / EULA URL** (optional but recommended): `https://thegalateacompany-hash.github.io/gatekeep-legal/terms.html`

## Use in app

Add these URLs to the in-app About/Settings screen so users can read them from inside Gatekeep.

## Updating

Edit `privacy.html` or `terms.html`, bump the "Last updated" date at the top, then:

```bash
git commit -am "Update privacy/terms YYYY-MM-DD"
git push
```

Pages re-deploys in ~30s.

## When you form your LLC

Find/replace "Jesiah Coates" with the LLC name across `privacy.html` and `terms.html`, bump the dates, push.
