# Listenara Website

Static GitHub Pages site for `https://listenara.com`.

## Current Status

- Public website repo: `Avenrow/listenara.com`.
- Custom domain: `listenara.com` is configured in GitHub Pages.
- Porkbun DNS: apex `A` records and `www` CNAME are pointed to GitHub Pages.
- HTTP: `http://listenara.com` is serving from GitHub Pages.
- HTTPS: pending GitHub Pages certificate provisioning; enable HTTPS after GitHub stops returning `The certificate does not exist yet`.
- Final public history cleanup: defer deleting/recreating the public website repo until final icon, payment, download, and launch assets are approved.

## Publish Source

Recommended setup:

- Keep the Listenara app source private.
- Create a separate public website repository, for example `Avenrow/listenara.com`.
- Copy only this `site/` folder's contents into that public repository.

The folder includes:

- `CNAME` with `listenara.com`
- `.nojekyll`
- `index.html`
- `privacy.html`
- `ai.html`
- `support.html`
- `install.html`
- `terms.html`
- `download.html`
- `latest.json`
- `404.html`
- `assets/listenara-icon.png`

From the private app repo, export only the public website files:

```bash
scripts/export-public-site.sh ../listenara.com
```

Then review the destination before publishing:

```bash
cd ../listenara.com
git status --short
```

## Porkbun DNS

The current Porkbun DNS should use records like this:

```text
Type   Host   Answer
A      @      185.199.108.153
A      @      185.199.109.153
A      @      185.199.110.153
A      @      185.199.111.153
CNAME  www    avenrow.github.io
```

Optional IPv6 records:

```text
Type   Host   Answer
AAAA   @      2606:50c0:8000::153
AAAA   @      2606:50c0:8001::153
AAAA   @      2606:50c0:8002::153
AAAA   @      2606:50c0:8003::153
```

After GitHub Pages provisions the certificate, enable HTTPS enforcement.

## Still Pending

- Deploy the updated PayPal checkout Worker/site flow and run one end-to-end purchase test.
- First release screenshot or app preview image.
- Upload the public AI skills ZIP after review if advertising AI integration at launch.
- Enable HTTPS after the GitHub Pages certificate is ready.
