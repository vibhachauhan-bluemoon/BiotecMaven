# BiotecMaven

The website for BiotecMaven — strategic biologics & computational biology consulting by Dr. Vibha Chauhan.

The site is a lightweight static page: **`index.html`** contains the layout, styling, and scripts, with the founder portrait served from **`assets/vibha-chauhan.jpg`**.

---

## Files in this repo

| File | Purpose |
|------|---------|
| `index.html` | The complete website. |
| `og-image.png` | Social-share preview card (shown when the link is posted on LinkedIn, etc.). Keep it in the repo root so `biotecmaven.com/og-image.png` resolves. |
| `CNAME` | Tells GitHub Pages to serve the site at `biotecmaven.com`. |
| `.nojekyll` | Tells GitHub Pages to serve the files as-is (skip Jekyll processing). |
| `README.md` | This file. |

---

## How to publish on GitHub Pages (free)

### 1. Create the repository
1. Sign in at [github.com](https://github.com) (create a free account if needed).
2. Click **New repository**, name it `biotecmaven`, set it to **Public**, and create it.

### 2. Upload these files
1. On the new repo page, click **Add file → Upload files**.
2. Drag in `index.html`, `CNAME`, `.nojekyll`, and `README.md`.
3. Click **Commit changes**.

### 3. Turn on GitHub Pages
1. Go to **Settings → Pages**.
2. Under **Build and deployment → Source**, choose **Deploy from a branch**.
3. Set the branch to **`main`** and the folder to **`/ (root)`**, then **Save**.
4. After a minute or two, your site is live at `https://<your-username>.github.io/biotecmaven/`.

### 4. Connect the custom domain (biotecmaven.com)
1. In **Settings → Pages → Custom domain**, enter `biotecmaven.com` and **Save**.
   (The included `CNAME` file already sets this, so it may be filled in for you.)
2. At your domain registrar — wherever biotecmaven.com is managed (this is currently Wix, so you may want to move DNS there or point it) — add these DNS records:

   **Four A records** for the apex domain `biotecmaven.com` (host `@`):
   ```
   185.199.108.153
   185.199.109.153
   185.199.110.153
   185.199.111.153
   ```

   *(Optional IPv6 — four AAAA records, same host `@`):*
   ```
   2606:50c0:8000::153
   2606:50c0:8001::153
   2606:50c0:8002::153
   2606:50c0:8003::153
   ```

   **One CNAME record** for `www`:
   ```
   Host: www   →   Value: <your-username>.github.io
   ```

3. DNS can take up to 24 hours to propagate. Once it has, return to **Settings → Pages** and tick **Enforce HTTPS**. GitHub issues the SSL certificate automatically.

---

## Moving off Wix

biotecmaven.com is currently pointed at Wix. To switch it to this site you have two options:

- **Keep the domain at Wix, repoint DNS** — in the Wix domain settings, replace the existing A/CNAME records with the GitHub Pages records above. (Some Wix plans restrict editing DNS records; if so, use the option below.)
- **Transfer the domain** to a registrar with full DNS control (e.g. Cloudflare, Namecheap, Google Domains successor), then add the records there.

Either way, once the records point at GitHub, the Wix site stops serving and this one takes over.

---

## Making edits later

Open `index.html`, change the text or styling, and commit the updated file back to the repo — GitHub Pages redeploys automatically within a minute. To swap the founder portrait, replace `assets/vibha-chauhan.jpg` and keep the image path in the "Meet the Expert" section.
