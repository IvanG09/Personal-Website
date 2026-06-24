# Ivan Gajić — Personal Website

A single-file personal site (HTML + CSS + JavaScript). No build step, no dependencies — just `index.html`.

## Run it locally
Double-click `index.html`, or open it in any browser. That's it.

---

## Put it online with GitHub Pages (free)

### 1. Create the repository
1. Sign in at https://github.com and click **New repository**.
2. Name it `ivangajic-website` (any name works). Set it to **Public**.
3. Create the repo. On the next page, choose **uploading an existing file** and drag in `index.html` (and this `README.md`). Commit.

> Prefer the command line? From the folder containing `index.html`:
> ```bash
> git init
> git add index.html README.md
> git commit -m "Initial site"
> git branch -M main
> git remote add origin https://github.com/YOUR-USERNAME/ivangajic-website.git
> git push -u origin main
> ```

### 2. Turn on Pages
1. In the repo, go to **Settings → Pages**.
2. Under **Build and deployment → Source**, choose **Deploy from a branch**.
3. Branch: **main**, folder: **/ (root)**. Save.
4. Wait ~1 minute. Your site goes live at:
   `https://YOUR-USERNAME.github.io/ivangajic-website/`

To update the site later, just edit `index.html` and commit/push again — Pages redeploys automatically.

---

## Use your own domain (e.g. ivangajic.ch)

### 1. Buy a domain
From any registrar (Infomaniak, Hostpoint and Gandi are good for `.ch`; Namecheap/Cloudflare for `.com`).

### 2. Add the domain in GitHub
Repo → **Settings → Pages → Custom domain** → type your domain (e.g. `ivangajic.ch`) → **Save**.
This creates a `CNAME` file in your repo automatically — leave it there.

### 3. Point DNS at GitHub (at your registrar's DNS settings)

**Apex / root domain** (`ivangajic.ch`) — create four **A records**, all with host `@`:
```
185.199.108.153
185.199.109.153
185.199.110.153
185.199.111.153
```
(Optional, for IPv6, add four **AAAA records**, host `@`:)
```
2606:50c0:8000::153
2606:50c0:8001::153
2606:50c0:8002::153
2606:50c0:8003::153
```

**www subdomain** (`www.ivangajic.ch`) — create one **CNAME record**:
```
Host:  www
Value: YOUR-USERNAME.github.io
```

### 4. Finish
- DNS can take anywhere from a few minutes to 24 hours to propagate.
- Back in **Settings → Pages**, tick **Enforce HTTPS** once it becomes available (gives you the padlock / secure connection).

Source for the IPs above: GitHub Docs — "Managing a custom domain for your GitHub Pages site."

---

## Switching hosts later
Because this is plain HTML, the exact same `index.html` works on **Cloudflare Pages**, **Netlify**, **Vercel**, or any static host. Nothing is locked to GitHub.
