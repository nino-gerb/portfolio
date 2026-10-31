# ninogerber.ch

Static portfolio site: plain HTML and CSS, no build step.

## Edit content

Everything is in `index.html`:

- **Theses** — the bachelor's thesis block is a placeholder (`[...]`). Replace the text and remove `placeholder` from its `class`.
- **Projects** — copy one `<article class="card">` block per project. Put images in `assets/img/` and replace `<div class="card-img">` with `<img src="assets/img/name.jpg" alt="..." loading="lazy">`.
- **PDFs** — put them in `assets/docs/` and uncomment the `links` block under the thesis. Check first that you are allowed to publish an industry thesis.
- **Contact** — email button in the contact section; add LinkedIn or GitHub buttons there when ready.

Preview locally:

```bash
python3 -m http.server 8090
```

## Deploy (GitHub Pages, free)

1. Create a public repo on GitHub (for example `portfolio`) and push this folder to it.
2. In the repo: **Settings → Pages → Source: Deploy from a branch → `main` / root**.
3. Under **Custom domain**, enter `ninogerber.ch` (the `CNAME` file already contains it).

## Point the domain at it (GoDaddy DNS)

In GoDaddy → **My Products → ninogerber.ch → DNS**:

1. Delete the existing `A` record for `@` that points to Website Builder.
2. Add four `A` records for `@`:
   `185.199.108.153`, `185.199.109.153`, `185.199.110.153`, `185.199.111.153`
3. Set the `CNAME` record for `www` to `<your-github-username>.github.io`.
4. Wait for DNS to update (minutes to a few hours), then tick **Enforce HTTPS** in the GitHub Pages settings.

Once the new site is live, you can cancel the GoDaddy Website Builder plan. Keep the domain registration itself.

GitHub's reference: https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site
