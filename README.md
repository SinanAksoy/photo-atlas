# PhotoAtlas

A single-page browser app for plotting photo GPS EXIF positions on an interactive map and manually placing photos that have no coordinates.

## GitHub Pages

1. In this repository, open **Settings → Pages**, and choose **GitHub Actions** for the publishing source.
2. The `Deploy PhotoAtlas to GitHub Pages` workflow publishes `index.html` from `main` on each push. If you enabled Pages after the first push, run the workflow manually from **Actions**.
3. Your public URL should be `https://<your-account>.github.io/<repository>/` after a successful deployment.

Photos and location data are processed in the browser and stored locally in IndexedDB; the public site does not upload images to GitHub. Leaflet tiles and metadata parsing libraries require internet access. To use the optional Google Maps view, you must provide your own Google Maps JavaScript API key, restricted for your site's domain.