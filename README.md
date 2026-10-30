# ok

A static recreation of the public page at [ok.fs.kg](https://ok.fs.kg/) (also branded [ok.no.kg](https://ok.no.kg/)), prepared so you can host the same page yourself. The original site stays at those addresses. This repository is an open recreation of that public page: the same layout and cat paintings, with fonts and images served from here, and with no trackers.

Layout, bilingual copy, and the cat paintings come from that public page. Fonts and images are self-hosted in this repo. The portrait hero (`img/assets/hero-tall.webp`) is the same file the live page requests for narrow portrait screens; it was saved from the public site along with the other assets.

## Preview locally

From this directory:

```bash
python3 -m http.server 8787
```

Open [http://127.0.0.1:8787/](http://127.0.0.1:8787/). Opening `index.html` directly also works; a local server is closer to how Cloudflare Pages serves it.

## Deploy to Cloudflare Pages

The site is a single static page. Cloudflare Pages can publish the repository root directly.

**Git**

1. In the Cloudflare dashboard, go to **Workers & Pages → Create → Pages → Connect to Git**.
2. Choose this repository.
3. Leave the build command empty.
4. Set the output directory to `/` (the repository root).

**Wrangler**

```bash
npx wrangler pages deploy . --project-name ok
```

After deploy, the page, favicon (`img/assets/favicon.png`), and social image (`img/assets/og.jpg`) are all served from your project. Fonts and pictures are not loaded from a third-party CDN.
