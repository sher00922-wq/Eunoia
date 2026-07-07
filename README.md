# Eunoia Praxis — static site

Six standalone pages, ready to deploy on Netlify. No Wix, no iframes.

## Files
- `index.html` — Home
- `services.html` — Services
- `assessments.html` — Assessments
- `treatment.html` — Treatment
- `contact.html` — Contact (with working form)
- `privacy.html` — Privacy & Confidentiality

All internal links are relative, every page shares the same navbar and footer, and the
iframe-only hacks (`<base target="_top">`, the `postMessage` form bridge) are gone.

## Deploy
You're already on Netlify, so just publish this folder:
- Drag the whole folder onto the Netlify "Deploys" area, **or**
- Push it to the connected Git repo and let Netlify build.

`index.html` is the home page automatically. Links like `services.html` also work as
`/services` once deployed (Netlify serves clean URLs).

## Make the contact form email you
The form already uses **Netlify Forms** (`name="contact"`, `data-netlify="true"`, a hidden
`form-name` field, and a spam honeypot). Netlify detects it automatically on the first deploy.

To get the emails:
1. Deploy the site once.
2. In Netlify: **Forms** (you'll see a "contact" form listed after the first submission) →
   **Settings & usage** / **Form notifications** → **Add notification** → **Email notification**.
3. Set the recipient to **info@eunoiapraxis.com**. Save.

That's it — submissions show in Netlify's dashboard AND get emailed to you. The page still
shows the inline "Thank you" message without reloading.

## Two things to fix before launch
1. **Services page images are placeholders.** `services.html` references 6 images from
   `skgtrhqvvgnmc.kimi.page` (a temporary host) — these will not load. Replace them with your
   own photos, or tell me and I'll strip the image blocks so nothing looks broken.
2. **Logo + icons load from Wix's CDN** (`static.wixstatic.com`). They work today, but if you
   delete the Wix site they may stop. Safest is to download them into an `images/` folder and
   update the `src` paths. I can do that rewrite for you once you have the files.
