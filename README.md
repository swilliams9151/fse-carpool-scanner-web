# Carpool Scanner — Browser Camera Frontend

Public, **scanner-only** hosting for the carpool application. This repository contains **no Google Apps Script backend, tag registry, Google Sheet, Drive photos, passwords, or student lists**.

## Pages

Publish from `main` / `/(root)` in **Settings → Pages**.

When GitHub Pages is active:

- Standard continuous QR scanner: `https://swilliams9151.github.io/fse-carpool-scanner-web/`
- AprilTag multi-scanner: `https://swilliams9151.github.io/fse-carpool-scanner-web/multi.html`
- Printable test markers: `https://swilliams9151.github.io/fse-carpool-scanner-web/markers.html`

The scanners are launched **from the Carpool Queue app**, which supplies an ephemeral bridge nonce, the trusted opener origin, and (for multi-scanning) the current permitted tag lookup snapshot. Opening `multi.html` by itself intentionally reports "Open from FSE Queue."

## Detector

AprilTag family: `tagStandard41h12`, IDs 0–2114. The detector runs in a browser Web Worker; the WASM binary is loaded from a pinned upstream jsDelivr release. The QR scanner uses a pinned `html5-qrcode` CDN release. Camera access requires HTTPS.

## Security

Authorization and queue changes are enforced by the **private Google Apps Script backend**. This public repository must never include student records, names, tag-to-family mappings, private API credentials, or backend code.

License and attribution for the AprilTag browser dependency appear in `APRILTAG-LICENSE` and `APRILTAG-NOTICE`.
