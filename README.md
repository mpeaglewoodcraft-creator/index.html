# MP Eagle Wood Craft — static site

Visitors see whatever is in `data/catalog.json` and the linked assets. There is no server database: after you edit content in **`admin.html`**, you export JSON and replace the file in this repo, then deploy.

## Replace product images

1. Add your photos under `assets/products/` (for example `assets/products/my-stand.jpg`).
2. In **Admin → Products**, set each product’s **Image** field to that path (or use a full `https://…` URL).
3. **Export JSON**, replace `data/catalog.json`, redeploy.
4. The starter files in `assets/products/*.svg` are placeholders only; swap them for real `.jpg` / `.webp` as you like.

Optional hero texture: the public stylesheet references `assets/images/wood-hero.svg` (included). You may replace it with a high-resolution photo and update `url(...)` in `css/styles.css` if you rename or relocate the file.

## Publish workflow (admin → live site)

1. Open `admin.html` locally or on your host (keep the URL private; it is not linked from the public navigation).
2. Set a stronger PIN in `js/config.js` (`ADMIN_PIN`) before any real deploy.
3. Edit **Categories**, **Products**, **Reviews**, and **Site settings** as needed.
4. Click **Export JSON** and save the downloaded file.
5. Overwrite `data/catalog.json` in this project with the exported file (same structure).
6. Deploy the site folder to Netlify, GitHub Pages, or any static host so `index.html` and `data/catalog.json` are served together.

Instagram links use `INSTAGRAM_URL` in `js/config.js`. Contact copy on the homepage also reads email, phone, handle, and “show unavailable products” from the catalog `site` object after load.

## Local preview

Open `index.html` in a browser from a local server (some browsers block `fetch` to JSON from `file://`). For example, from this folder:

`npx --yes serve .`

Then visit the URL shown (often [http://localhost:3000](http://localhost:3000)).
