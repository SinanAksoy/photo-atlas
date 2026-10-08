# PhotoAtlas

A standalone HTML photo map for phones and desktop browsers. Add original camera images, automatically extract embedded GPS when available, and place missing photos by tapping the map, entering coordinates, or searching for an area before pinning.

## Use

- Open the published GitHub Pages website and choose photos.
- **Automatic:** EXIF GPS coordinates from original JPEGs are read by a built-in parser; exifr supports additional HEIC/HEIF, PNG, and other image formats (internet needed to load the library).
- **Manual:** press **Tap map to pin** on a photo, zoom/pan, then tap the map. Alternatively enter decimal coordinates. Pin markers are draggable.
- **Find an area:** use the place search (OpenStreetMap Nominatim, submitted only when you click Find), and then tap the exact pin location.
- **If the map has missing tiles:** switch between **Street map** (CARTO Voyager) and **OSM alternative** under map provider settings.
- **Local storage:** IndexedDB keeps photos in the current browser only. Export GeoJSON, or use full photo backup/restore to change devices.

### Samsung Gallery caveat

The Gallery application may show a human-readable address derived from location services or the phone's database. The address displayed in the app is **not equivalent to embedded GPS** in the file that a web page can access. Select the **original** photo from **My Files → Internal storage → DCIM → Camera**; media shared via apps or modified copies may lose metadata. This website never accesses the Samsung Gallery internal database.

### Google Maps

Google Maps is **optional** and requires a personal **Google Maps JavaScript API key**, an enabled billing account, and a permitted HTTPS referrer. Keys used in browsers should be **HTTP-referrer restricted**, for example `https://sinanaksoy.github.io/*`, and restricted to the Maps JavaScript API. The default free OpenStreetMap/CARTO-based map needs no Google API key. API keys are not committed to the repository.

## Hosting

GitHub Pages uses the `Deploy PhotoAtlas to GitHub Pages` workflow at `.github/workflows/deploy.yml`. In **Settings → Pages**, choose **GitHub Actions** as source. Commits to `main` update the site.

This is a static website; photographs are not uploaded to GitHub or any server by PhotoAtlas. It uses third-party CDN scripts, map tiles, and manually invoked place searches, requiring internet access for those features.