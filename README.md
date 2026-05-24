# jontycollins.com

Single-page personal site. No build step — it's one `index.html`.

## Files
- `index.html` — the site
- `headshot.jpg` — your photo (you add this; see below)
- `CNAME` — tells GitHub Pages to serve the site at jontycollins.com
- `README.md` — this file

---

## 1. Add your headshot
Save your photo into this folder named exactly **`headshot.jpg`** (all lowercase, .jpg).
- Crop it close to roughly a 4:5 portrait (e.g. 800×1000px) so it sits nicely in the frame.
- It appears in grayscale and warms to full colour on hover — that's intentional.
- Until the file exists, the site shows a "JC" placeholder, so it never looks broken.

## 2. Put it on GitHub
1. Create a new repository (e.g. `jontycollins-site`). Public is simplest; **private repos need a paid GitHub plan to publish Pages.**
2. Upload `index.html`, `headshot.jpg`, and `CNAME` to the repo root (drag-and-drop in the GitHub web UI is fine).

## 3. Turn on GitHub Pages
1. Repo → **Settings → Pages**.
2. Under "Build and deployment", Source = **Deploy from a branch**.
3. Branch = `main`, folder = `/ (root)`. Save.
4. Wait ~1 minute — your site goes live at `https://<username>.github.io/<repo>/`.

## 4. Point jontycollins.com at it
In your domain registrar's DNS settings, add these records:

**Apex domain (jontycollins.com)** — four A records:
```
A   @   185.199.108.153
A   @   185.199.109.153
A   @   185.199.110.153
A   @   185.199.111.153
```
**www subdomain:**
```
CNAME   www   <username>.github.io
```
Then in **Settings → Pages → Custom domain**, enter `jontycollins.com` and save. Tick **Enforce HTTPS** once it's available (can take up to ~24h for the certificate). The `CNAME` file in this repo handles the rest.

DNS can take anywhere from a few minutes to a few hours to propagate.

## 5. When you're ready to be found on Google
The `<head>` has a `<meta name="robots" content="noindex" />` line that keeps the site out of search results. Delete that one line and re-upload `index.html` when you want it indexed.

---

## Updating the demo link
The "Check-in Co-Pilot" project links to `…workers.dev/?k=demo`. That public `demo` key only works once you've added it to the Worker (it's covered in `Check-in-Copilot-1pct-fixes-PROMPT.md`). Until then, either implement that key or swap the link for your private one (note: your private key would then be public, so prefer the demo key).
