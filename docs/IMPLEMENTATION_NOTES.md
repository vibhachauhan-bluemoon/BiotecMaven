# BiotecMaven implementation notes

## Repository

`C:\Users\vibha\Claude\Artifacts\biotecmaven-site`

This is a static artifact repository now connected locally to the GitHub remote `https://github.com/vibhachauhan-bluemoon/BiotecMaven.git`. The remote `main` branch contains `CNAME` (`biotecmaven.com`) and `.nojekyll`, so the deployment method is GitHub Pages from `main` / repository root. There is no Wix/Velo source in this repository. The prior homepage is preserved at `versions/index.pre-codex-redesign-20260901.html` and the final pre-deploy checkpoint is under `versions/final-pre-deploy-20260901/`.

## Included in this pass

- `index.html`: conversion-focused homepage with the three customer-facing doors, managed external execution language, decision pathway, engagement models, and CTA event hooks (`window.dataLayer`).
- `difficult-biologics.html`: future landing page for difficult biologics and protein-expression troubleshooting.
- `_redirects`: permanent redirect rule for hosts that support Netlify-style redirects.
- `strategic-services.html`: static fallback that immediately redirects old traffic to the homepage when a host does not process `_redirects`.

## Manual deployment / Wix handoff

1. Commit and push the approved root files to the existing GitHub `main` branch. GitHub Pages will publish from the repository root; the existing `CNAME` keeps `biotecmaven.com` attached.
2. Configure a true 301 from `/strategic-services` to `/` in the hosting or Wix redirect manager if the domain still resolves to Wix. The repository includes `_redirects` for redirect-capable static hosts plus a fallback `strategic-services.html`; GitHub Pages itself does not process `_redirects` as a server-side 301.
3. Keep the blog out of primary navigation for now. Review generic or obsolete posts before deleting anything; no posts were deleted in this pass.
4. Connect the CTA `dataLayer` events to the site's GA4/GTM container after the measurement ID is known. No analytics property or ad campaign was created here.
5. Request Google Search Console recrawl after the redirect and homepage deployment.
