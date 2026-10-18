# Airtable Hub

One static page (`index.html`, no build step) that bundles several Airtable interface pages behind a sidebar. On phones the sidebar becomes a tab strip. Each page has its own deep link (`/#requests`), and pages you've already opened stay loaded, so switching back is instant.

## Add an interface page

1. In Airtable, open the interface → **Share interface** → **Share to web**, pick the page and turn it on.
2. Click **Embed** and copy the link or the whole `<iframe>` code.
3. Add an entry to `SITE.interfaces` near the bottom of `index.html`:

   ```js
   { name: "Requests", description: "Open intake requests", url: "https://airtable.com/appXXX/shrXXX" },
   ```

Every page is shared on its own, so each page in the hub needs its own Share to web link. Anyone with the hub URL can see whatever those pages show. If you regenerate a share link in Airtable, the old embed stops working, so paste the new one here.

## Preview locally

```bash
python3 -m http.server 8138 --directory .
```

## Publish

GitHub Pages, Netlify Drop (drag the folder onto app.netlify.com/drop) or any static host works. You only need to upload `index.html`.
