# Redis Radar — Private Preview Portal

GitHub Pages site that gates access to Radar preview artifacts behind a Terms & Conditions agreement and email registration.

**Live URL:** https://redislabsdev.github.io/radar-private-preview/

---

## Adding Artifacts

Place artifact files in the `downloads/` directory and commit them:

```bash
cp /path/to/radar-preview.zip downloads/
git add downloads/radar-preview.zip
git commit -m "Add Radar vX.Y preview artifact"
git push
```

The download button in `index.html` is pre-configured to serve `./downloads/radar-preview.zip`.  
To change the filename, update these two lines at the top of the `<script>` block in `index.html`:

```js
const DOWNLOAD_URL = './downloads/your-filename.zip';
const DOWNLOAD_FILENAME = 'your-filename.zip';
```

---

## Email Tracking Setup (optional)

Submissions are tracked via [Formspree](https://formspree.io) (free tier: 50/month, paid for more).

1. Create a free account at formspree.io
2. Create a new form — copy the endpoint URL (e.g. `https://formspree.io/f/xpwzabcd`)
3. In `index.html`, set:
   ```js
   const TRACKING_ENDPOINT = 'https://formspree.io/f/xpwzabcd';
   ```
4. Responses appear in your Formspree dashboard and can be forwarded to any email.

---

## Updating the Terms & Conditions

Replace the placeholder T&C text inside the `<div id="tncBox">` element in `index.html` with your actual legal terms.

---

## GitHub Pages Setup

Pages is enabled on the `main` branch root. The site rebuilds automatically on every push to `main`.
