# Listenara Website

Static GitHub Pages site for `https://listenara.com`.

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
- `support.html`
- `install.html`
- `terms.html`
- `download.html`
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

## Porkbun DNS Later

Do not point DNS at GitHub Pages until the GitHub Pages site has the custom domain configured.

When ready, use Porkbun DNS records like this:

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

After DNS resolves in GitHub Pages, enable HTTPS.

## Still Pending

- Upload `Listenara-v1.0.0.dmg` and `Listenara-v1.0.0.dmg.sha256` to the public website repo's GitHub Releases.
- Replace the disabled PayPal checkout button in `download.html` with the live US$29 PayPal checkout URL.
- First release screenshot or app preview image.
