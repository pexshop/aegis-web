# AEGIS Web Privacy Vault

Standalone browser-based companion for the AEGIS project. This repository is independent of PEX, Cloudflare, and the native iOS repository.

## Features
- Browser Web Crypto API: PBKDF2-SHA-256 (310,000 iterations) derives an AES-256-GCM key.
- File bytes and file metadata (name, MIME type, size) are encrypted before being stored in IndexedDB.
- Encrypted JSON backup and restore.
- Manual lock, lock on page backgrounding, and five-minute timeout.
- Static offline shell through a service worker.
- Local privacy diagnostics page (`privacy-check.html`) for browser capabilities, secure-context status, storage estimates, service-worker status, and limited Permissions API queries.
- iPhone system self-check guide for iOS updates, VPN/device management profiles, Apple Account devices, Safety Check, app permissions, and App Privacy Report.
- Local JSON report export; no network upload or external analytics.

## Privacy diagnostics limitations
The diagnostics page is a browser-level check, not an iOS antivirus or forensic scanner. iOS Safari cannot let a normal website inspect other apps, system processes, SMS/call history, the complete installed-app list, system files, jailbreak state, all configuration profiles, or advanced spyware such as Pegasus. Unsupported or inaccessible checks are explicitly reported as such. A clean browser report does not prove that an iPhone is uncompromised.

## Deploy
This repository is intended for GitHub Pages. The workflow in `.github/workflows/pages.yml` publishes the repository root. Use HTTPS; Web Crypto is unavailable on ordinary insecure origins.

## iPhone
Open the deployed HTTPS address in Safari. Use Share → Add to Home Screen if you want an app-like shortcut. The privacy check is available from the vault landing page or directly at `/aegis-web/privacy-check.html`.

## Security limitations
- This is a personal-use browser tool, not an independently audited security product. It cannot protect against a compromised device, malicious browser extensions, keyloggers, or malicious code already running in the browser.
- Passwords are not stored. A forgotten password cannot be recovered.
- Clearing Safari website data may permanently delete the local IndexedDB vault. Keep encrypted backups in a separate safe location.
- Individual file export produces plaintext. Treat exported files as sensitive.
- The browser version does not provide the same security boundary as native iOS Keychain and Face ID.
- Public repository contains application source only. Never commit passwords, keys, personal files, or backups.
