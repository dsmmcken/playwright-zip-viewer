# Playwright ZIP Viewer

A web-based viewer for Playwright HTML reports from ZIP files.

**Live Demo:** https://dsmmcken.github.io/playwright-zip-viewer/

## Why?

Playwright HTML reports include trace files that require being served over HTTPS to function properly. Opening `index.html` directly via `file://` protocol won't work for traces - they need a proper web server.

This viewer makes it easy to view any Playwright report without setting up a local server. Just drop your ZIP file or provide a URL.

## Features

- **Drag & Drop** - Drop a Playwright report ZIP directly onto the page
- **URL Loading** - Enter a URL to fetch a remote ZIP file
- **URL Parameter** - Use `?url=` parameter for direct linking
- **GitHub Artifact Support** - Automatically transforms GitHub artifact URLs to use nightly.link for CORS bypass
- **Privacy Focused** - All processing happens locally in your browser. No data is uploaded.

## Usage

### Option 1: Drag & Drop
1. Generate your Playwright report: `npx playwright test --reporter=html`
2. ZIP the `playwright-report` folder
3. Drop the ZIP onto the viewer

### Option 2: URL
1. Host your ZIP file somewhere accessible (with CORS headers if cross-origin)
2. Enter the URL in the input field, or
3. Use the URL parameter: `https://dsmmcken.github.io/playwright-zip-viewer/?url=YOUR_ZIP_URL`

### Option 3: GitHub Actions Artifacts
For GitHub Actions artifacts, the viewer automatically converts URLs to use nightly.link for CORS bypass.

## Self-Hosting

The viewer is a simple static site with no build step:

```bash
git clone https://github.com/dsmmcken/playwright-zip-viewer.git
cd playwright-zip-viewer
# Serve with any static file server
python -m http.server 8080
```

## License

MIT
