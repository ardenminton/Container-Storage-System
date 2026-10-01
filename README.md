# EXODUS // Container Control

A local-first static web app for moving/storage inventory.

## Features
- Generate unique permanent container IDs (example `EX-7K4M2Q`)
- Render scannable Code 128 labels without external libraries
- Scan Code 128 with the device camera when `BarcodeDetector` is supported
- Search contents, item names, rooms, notes, and container IDs
- Priority 1 / 2 / 3 and handling flags
- Move Mode for rapid Loaded / Arrived / Unpacked updates
- JSON backup/import and CSV export
- Local browser storage
- Installable/offline PWA when hosted

## Quick use
1. Open the app and choose **Generate labels**.
2. Print the labels and attach one to each box.
3. Pack a box and write its room, priority, contents, and handling marks on the physical label.
4. Scan the Code 128 barcode and enter the same details digitally.
5. Search the app later to find any item.

## Camera scanning
Browsers only allow camera access from a secure context. For scanning, serve the folder from **HTTPS** or **localhost**. Opening `index.html` directly still supports inventory, search, label generation, printing, and manual code entry, but camera scanning may be blocked.

For a quick desktop test from this folder:

```bash
python -m http.server 8080
```

Then open `http://localhost:8080`.

To use it on a phone as an installable app, publish the folder to any static HTTPS host (for example GitHub Pages, Cloudflare Pages, Netlify, or your own web server), then use **Add to Home screen / Install app**.

## Storage / privacy
Container data stays in that browser's local storage unless you export it. Use **Backup → Export JSON backup** periodically, especially before clearing browser data or changing phones.
