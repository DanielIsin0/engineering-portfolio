# Daniel Isin — engineering portfolio

A lightweight, responsive, single-page portfolio built with plain HTML, CSS, and a small JavaScript enhancement. No package manager, build step, or paid service is required.

## Edit the site

- Edit `index.html` for the introduction, education, skills, contact details, and project cards.
- Edit `styles.css` for layout, colors, and typography. The main design tokens are at the top of the file.
- Replace the clearly marked project placeholders only with verified details. Add real schematics, plots, and photographs under `assets/`, give informative images useful `alt` text, and add GitHub links to the relevant project cards when available.
- Update `assets/og.svg` if the social sharing artwork or site title changes. Update `sitemap.xml`, `robots.txt`, the canonical URL, and Open Graph URL in `index.html` if the domain changes.
- `script.js` only updates the copyright year. The page works without JavaScript.

To preview locally, run `python3 -m http.server 8000` in the repository directory and open `http://localhost:8000/`.

## Deploy with Cloudflare Pages

1. In Cloudflare, open **Workers & Pages**, create an application, choose **Pages**, and select **Connect to Git**.
2. Authorize the GitHub integration for `DanielIsin0/engineering-portfolio` and select that repository. Choose `main` as the production branch.
3. Configure the build: **Framework preset:** None; **Build command:** leave blank; **Build output directory:** `.` (repository root); **Root directory:** leave at the repository root. No environment variables are needed.
4. Save and deploy. Cloudflare will provide a `*.pages.dev` URL. New commits to `main` will trigger production deployments; pull requests can receive preview deployments.
5. In the Pages project, open **Custom domains** and add `danielisin.engineer`. Follow Cloudflare's DNS prompts. For an apex domain, the DNS zone must be managed by Cloudflare in the same account; if the domain uses another DNS provider, move its nameservers to Cloudflare first. Allow DNS propagation and certificate issuance, then confirm `https://danielisin.engineer/` loads over HTTPS.

The site includes `_headers` for basic response headers, plus `robots.txt` and `sitemap.xml`. No Cloudflare API credentials belong in this repository.
